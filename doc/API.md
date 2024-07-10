# API Reference

**[← Table of contents](/README.md)**

### On this page

[Ariel Text-To-Speech](#ariel-text-to-speech)<br/>
[On Ariel Response](#on-ariel-response)<br/>
[Audio wav bytes to SoundWave](#audio-wav-bytes-to-soundwave)<br/>
#### [Utilities](#utilities-1)
    [Get available Speakers](#get-available-speakers-pure) <b style="color:red">\*</b> <br/>
    [Get available Speakers (filtered)](#get-available-speakers-filtered-pure) <b style="color: red">\*</b><br/>
    [Scheme filename](#scheme-filename)<br/>
#### [Editor only](#editor-only-1)
    [Show folder selection dialog](#show-folder-selection-dialog)<br/>
    [Save bytes to file](#save-bytes-to-file)<br/>
    [Get Documentation URL](#get-documentation-url) <b style="color: red">\*</b><br/>
#### [Structures](#structures-1)
    [Ariel Speaker](#ariel-speaker-farielspeaker)<br/>
#### [Enumerations](#enumerations-1)
    [Ariel Audio Format](#ariel-audio-format-earielaudioformat)<br/>
    [Ariel Audio Effect](#ariel-audio-effect-earielaudioeffect)<br/>

*<b style="color:red">\*</b>Pure functions*

<!------------------------------------------------------------------------------------------------------------------------------->

## Ariel Text-To-Speech

C++ Function: `UArielBPLibrary::ArielTTS`

This node calls the Ariel API using **HTTPS** request with all defined parameters (speaker, sentence, format, effects, …). The response is sent through a multicast delegate event, [On Ariel Response](#on-ariel-response).

![Ariel Text-To-Speech node](/res/ariel_text_to_speech.png)

### Parameters

| Name              | Type           | Default value     | Description |
| ----------------- | -------------- | ----------------- | ----------- |
| Speaker           | const FString& | *empty string*    | The speaker used to generate the speech. See [available speakers](/README.md#speakers). |
| Language          | const FString& | *empty string*    | The speaker language used to generate the speech. Leave empty to select the default language associated with the speaker. See [available speakers](/README.md#speakers). |
| Sentence          | const FString& | *empty string*    | The sentence of the speech. |
| Voice Adjustments | const bool     | `false`           | Analyze the generated audio file and try to enhance it with AI. It sometimes can lead to unwanted sounds, but in general improves audio. |
| Audio Format      | const [EArielAudioFormat](#ariel-audio-format-earielaudioformat) | `wav`    | The audio format of the generated file. |
| Volume            | const int      | `0`dB             | Amplify or reduce the volume specified in dB. |
| High Framerate    | const bool     | `false`           | Generate an audio with a frame rate of 44.1KHz instead of 22.05KHz. |
| Semitones         | const int      | `+0`st            | Shifts the sound by the given semitones. **Can be positive or negative**. |
| Speed             | const float    | x`1.0`            | Increase or decrease the sound speed. **Must be greater than 0**. |
| Audio Effects     | const TArray\<[EArielAudioEffect](#ariel-audio-effect-earielaudioeffect)\>& | *empty array* (no effects) | List of all audio effects who will be applied to the audio. See [🎶 Audio effects](/doc/Features.md#-audio-effects). |
| Logs              | const bool     | `false`           | Indicate if logs should be printed to the console. |
| On Response       | [FOnArielResponse](#on-ariel-response) | -               | The event called when a response was received. |

<!------------------------------------------------------------------------------------------------------------------------------->

## On Ariel Response

C++ Declaration: `FOnArielResponse`

Use the nodes *Add Custom Event...* or *Create Event* to bind the [Ariel Text-To-Speech](#ariel-text-to-speech) delegate to a Blueprint Event or function.

![On ariel response node](/res/on_ariel_response_1.png)<br/>
![On ariel response 2 node](/res/on_ariel_response_2.png)

### Return values

| Name              | Type                  | Description |
| ----------------- | --------------------- | ----------- |
| Success           | bool                  | Indicate if the response audio bytes have successfully been downloaded. |
| File Bytes        | const TArray\<uint8\>&  | The generated audio file bytes array, if the request was successful. |
| Error Message     | const FString&        | The error message, if the request was not successful. |

<!------------------------------------------------------------------------------------------------------------------------------->

## Audio wav bytes to SoundWave

C++ Function: `UArielBPLibrary::WavBytesToSoundWave`

Create a new SoundWave object from the generated audio wav file byte array. See [Ariel Text-To-Speech](#ariel-text-to-speech) and [On Ariel Response](#on-ariel-response) for more details on how to generate the audio bytes.

![Audio wav bytes to SoundWave node](/res/audio_wav_bytes_to_soundwave.png)

### Parameters

| Name        | Type                   | Default value | Description |
| ----------- | ---------------------- | ------------- | ----------- |
| Audio Bytes | const TArray\<uint8\>& | -             | The wav file bytes. **Warning:** Must be PCM-16 for Unreal Engine! |

### Return values

| Name         | Type        | Description |
| ------------ | ----------- | ----------- |
| Success      | bool&       | Indicate if the SoundWave object have been successfully created. |
| Out Reason   | FString&    | The SoundWave creation error message. |
| Return Value | USoundWave* | The created SoundWave Asset, or `nullptr` if the Asset couldn't be created. |

<!------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------->

# Utilities

The following nodes have been created to help the usage of the Ariel plugin, but they are not part of the main plugin usage. The nodes below can be used in runtime and packaged projects, unlike the nodes described in the [Editor](#editor-only-1) section.

<!------------------------------------------------------------------------------------------------------------------------------->

## Get available Speakers *(pure)*

C++ Function: `UArielBPLibrary::GetSpeakersFromSettings`

Get the available speakers list from the project settings.

![Get available Speakers node](/res/get_available_speakers.png)

### Return values

| Name         | Type                    | Description |
| ------------ | ----------------------- | ----------- |
| Return value | TArray\<[FArielSpeaker](#ariel-speaker-farielspeaker)\> | The list of available speakers. This is the same list as the documentation [speaker list](/README.md#speakers). |

<!------------------------------------------------------------------------------------------------------------------------------->

## Get available Speakers (filtered) *(pure)*

C++ Function: `UArielBPLibrary::GetSpeakersFiltered`

Get available Ariel speakers that correspond to the desired gender and language.

![Get available Speakers filtered node](/res/get_available_speakers_filtered.png)

### Parameters

| Name        | Type                 | Default value  | Description |
| ----------- | -------------------- | -------------- | ----------- |
| Language    | const FString&       | *empty string* | The desired language. Leave empty to allow all languages. |
| Gender      | const FString&       | *empty string* | The desired gender. Leave empty to allow all genders. |

### Return values

| Name         | Type                    | Description |
| ------------ | ----------------------- | ----------- |
| Return value | TArray\<[FArielSpeaker](#ariel-speaker-farielspeaker)\> | The filtered list of available speakers. |

<!------------------------------------------------------------------------------------------------------------------------------->

## Scheme filename

C++ Function: `UArielBPLibrary::SchemeFilename`

Replace shamed templates with the actual value for the Ariel filename.

You can use the schemes below to cusomise the name of the generated audio:

* `{speaker}` The name of the speaker.
* `{date}` The current date (from OS).
* `{time}` The current time (from OS).
* `{datetime}` The current date time (from OS).
* `{uuid}` The uuid (or guid).
* `{format}` The audio format.

Example:
> `TTS_{speaker}_{datetime}.{format}` will become `TTS_Oriane_2023-01-01_23-59-00.wav`

![Scheme filename node](/res/scheme_filename.png)

### Parameters

| Name        | Type                 | Default value  | Description |
| ----------- | -------------------- | -------------- | ----------- |
| Schemed Filename | const FString&  | *empty string* | The ariel filename with templates (like `{uuid}` or `{speaker}`). |
| Speaker     | const FString&       | *empty string* | The speaker name that will be used to replace `{speaker}` scheme. |
| Format      | [EArielAudioFormat](#ariel-audio-format-earielaudioformat) | `wav`     | The format that will be used to replace `{format}` scheme. |
| UUID        | const FString&       | *empty string* | The UUID (or GUID) that will be used to replace `{uuid}` scheme. |

### Return values

| Name         | Type    | Description |
| ------------ | ------- | ----------- |
| Return value | FString | The new Ariel filename with all schemes replaced. |

<!------------------------------------------------------------------------------------------------------------------------------->

# Editor only

The following nodes can **ONLY** be used when the Unreal Editor is running. The nodes won't be compiled on packaged projects and will result as a crash if they are called anyway. Please be careful when using these nodes.

## Show folder selection dialog

C++ Function: `UArielEditorLibrary::ShowFolderSelectionDialog`

Open the Operating System folder selection dialog. This allows to select a folder located **outside** the project.

![Show folder selection dialog node](/res/show_folder_selection_dialog.png)

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Selected Dir | FString& | The absolute directory path (unix style, with `/`). |
| Return value | bool     | True if a folder was selected by the user, false otherwise. |

<!------------------------------------------------------------------------------------------------------------------------------->

## Save bytes to file

C++ Function: `UArielEditorLibrary::SaveToFile`

Write the given bytes to a file. If the file already exists, it will be overwritten. You can use this function to write other file than Ariel audio files. In this case, do not forget to put the file extension with the filename. 

![Save bytes to file node](/res/save_bytes_to_file.png)

### Parameters

| Name          | Type                  | Default value  | Description |
| ------------- | --------------------- | -------------- | ----------- |
| Bytes         | const TArray\<uni8\>& | -              | The bytes to write in the file. |
| Filename      | const FString&        | ArielAudio     | The file name. You can specify the file extension as well (i.e: 'ArielAudio.ogg'). |
| DirectoryPath | const FDirectoryPath& | -              | The directory where the file will be written. Can be inside or outside the project directory. |
| Format        | const [EArielAudioFormat](#ariel-audio-format-earielaudioformat) | `wav`| The audio format used for file extension (if not already provided with the filename). |
| Logs          | const bool            | `true`         | Indicate if logs should be printed to the console. |

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Out Path     | FString& | The absolute file path (unix style, with `/`), fully qualified. |
| Return value | bool     | True if the file was (over)written, false otherwise (like an unvalid path or a permission error). |

<!------------------------------------------------------------------------------------------------------------------------------->

## Get Documentation URL

C++ Function: `UArielEditorLibrary::GetDocumentationURL`

Get the current Ariel plugin documentation URL.

![Get documentation URL node](/res/get_documentation_url.png)

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Return value | FString  | The documentation URL (static, inline). Use it with the Unreal node *Launch URL*. |

<!------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------->

# Structures

C++ and Blueprint structs defined by the Ariel plugin.

## Ariel Speaker *(FArielSpeaker)*

C++ Name: `FArielSpeaker`

The JSON structure of a speaker returned by the Ariel API. You can find the speakers list with all details [here](/README.md#speakers) or in Unreal [Developer settings](TODO).

![Ariel speaker break node](/res/ariel_speaker.png)

### Variables

| Name      | Type              | Editor           | Blueprint | Description |
| --------- | ----------------- | ---------------- | --------- | ----------- |
| ID        | int               | Visible Anywhere | Read-only | The Ariel Speaker identifier. |
| Name      | FString           | Visible Anywhere | Read-only | The Ariel Speaker name. |
| Gender    | Gender            | Visible Anywhere | Read-only | The Ariel Speaker gender. |
| Languages | TArray\<FString\> | Visible Anywhere | Read-only | The Ariel Speaker language(s). |

<!------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------->

# Enumerations

C++ and Blueprint enumerations defined by the Ariel plugin.

## Ariel Audio Effect *(EArielAudioEffect)*

C++ Name: `EArielAudioEffect`

This enum contains all Ariel audio effects available. See [🎶 Audio effects](/doc/Features.md#-audio-effects) for more details.

![Ariel audio effect make node](/res/ariel_audio_effect.png)<br/>
*Hover the cursor on an value to see more details about it.*

### Values

| Name              | Description |
| ----------------- | ----------- |
| **Telephone**     | The voice sounds like it's coming from a phone. |
| **Cave**          | The voice sounds like the speaker is in a cave. |
| **Small cave**    | The voice sounds like the speaker is in a small cave. |
| **Gas mask**      | The voice sounds like the speaker has a gas mask. |
| **Bad reception** | The voice sounds like it's coming from a phone with a bad reception. |
| **Next room**     | The voice sounds like the speaker is in the next room. |
| **Alien**         | An alien audio effect is added to the voice. |
| **Alien 2 (alt)** | An other alien audio effect (like in the space) is added to the voice. |
| **Stereo**        | The audio file have two channels (the mono channel is duplicated). |

<!------------------------------------------------------------------------------------------------------------------------------->

## Ariel Audio Format *(EArielAudioFormat)*

C++ Name: `EArielAudioFormat`

This enum contains all supported ariel audio file formats.

![Ariel audio format make node](/res/ariel_audio_format.png)<br/>
*Hover the cursor on an value to see more details about it.*

### Values

| Name | Description |
| ---- | ----------- |
| wav  | PCM-16 RIFF Waveform audio file. |
| mp3  | MPEG-1/2 audio file. |