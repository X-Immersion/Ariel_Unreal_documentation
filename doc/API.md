# API Reference

**[← Table of contents](/README.md#table-of-contents)**

### On this page

[Ariel Text-To-Speech](#ariel-text-to-speech)<br/>
[Ariel Text-To-Speech Local](#ariel-text-to-speech-local)<br/>
[Audio WAV bytes to SoundWave](#audio-wav-bytes-to-soundwave)<br/>
[Start Local Ariel](#start-local-ariel)<br/>
[Stop Local Ariel](#stop-local-ariel)<br/>
#### [Delegates (Events)](#delegates-events-1)
    [On Ariel Response](#on-ariel-response)<br/>
    [On Ariel Speakers Available](#on-ariel-speakers-available)<br/>
    [On Ariel Initialized](#on-ariel-initialized)<br/>
    [On Check Ariel Available Response](#on-check-ariel-available-response)<br/>
#### [Utilities](#utilities-1)
    [Get Ariel Local Executable Status](#get-ariel-local-executable-status-pure)<br/>
    [Get available Speakers](#get-available-speakers)<br/>
    [Get Number Channels From SoundWave](#get-number-channels-from-soundwave-pure)<br/>
    [Get Sample Rate From SoundWave](#get-sample-rate-from-soundwave-pure)<br/>
    [Is Connected to Internet](#is-connected-to-internet)<br/>
    [Scheme filename](#scheme-filename)<br/>
#### [Editor only](#editor-only-1)
    [Show folder selection dialog](#show-folder-selection-dialog)<br/>
    [Save bytes to file](#save-bytes-to-file)<br/>
    [Get Documentation URL](#get-documentation-url-pure)<br/>
#### [Structures](#structures-1)
    [Ariel Speaker](#ariel-speaker-farielspeaker)<br/>
#### [Enumerations](#enumerations-1)
    [Ariel Audio Format](#ariel-audio-format-earielaudioformat)<br/> 
    [Ariel Audio Effect](#ariel-audio-effect-earielaudioeffect)<br/> 
    [Ariel Local Executable Status](#ariel-local-executable-status-earielsubsystemstatus)<br/>


<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Ariel Text-To-Speech

C++ Function: 
```cpp
static void UArielBPLibrary::ArielTTS()
```

This node calls the Ariel Remote *(online)* API using **HTTPS** request with all defined parameters (speaker, sentence, format, effects, …). The response is sent through a multicast delegate event, [On Ariel Response](#on-ariel-response).

| Compact | Expanded |
| ------- | -------- |
| ![Ariel Text-To-Speech compact node](/res/ariel_text_to_speech_short.png) | ![Ariel Text-To-Speech node](/res/ariel_text_to_speech.png) |


### Parameters

| Name              | Type           | Default value     | Description |
| ----------------- | -------------- | ----------------- | ----------- |
| Speaker           | const FString& | *empty string*    | The speaker used to generate the speech. See [available speakers](/README.md#speakers). |
| Sentence          | const FString& | *empty string*    | The sentence of the speech. |
| Language          | const FString& | *empty string*    | The speaker language used to generate the speech. Leave empty to select the default language associated with the speaker. |
| Voice Adjustments | const bool     | `false`           | Try to enhance the generated audio with AI. It sometimes can lead to unwanted sounds, but in general improves quality. |
| High Framerate    | const bool     | `false`           | Generate an audio with a frame rate of 44.1KHz instead of 22.05KHz. |
| Stereo            | const bool     | `false`           | Generate using two channels, or duplicate the mono channel if the speaker voice does not support stereo generation. |
| Volume            | const int      | `0`dB             | Amplify or reduce the volume specified in dB. **Can be positive or negative**. |
| Semitones         | const int      | `+0`st            | Shifts the sound by the given semitones. **Can be positive or negative**. |
| Speed             | const float    | x`1.0`            | Increase or decrease the sound speed. **Must be greater than 0**. |
| Audio Format      | const [EArielAudioFormat](#ariel-audio-format-earielaudioformat) | `wav`    | The audio format of the generated file. |
| Audio Effects     | const TArray\<[EArielAudioEffect](#ariel-audio-effect-earielaudioeffect)\>& | *empty array* (no effects) | List of all audio effects who will be applied to the audio.<br/> See [🎚️ Audio effects](/doc/Features.md#-audio-effects). |
| Temperature       | const float    | `0.0`             | Adjust the temperature for the model generation. A higher temperature will allow the model to be more creative and free for the generation, while a lower temperature will 'force' the model to generate a speech close to the original trained data. **Must be between 0.0 and 1.0**, otherwise the generation will fail. |
| Fast Generation   | const bool     | `true`            | Use a faster model for voice generation, slightly impacting the voice quality. This parameter is only relevant on some speakers. |
| Static Save       | const bool     | `true`            | Store the generated speech and the associated the request parameters in our server for 30 days. If the same request with the same parameter is made, directly return the saved audio speech instead of regenerating the speech with the model again. |
| Logs              | const bool     | `true`           | Indicate if logs should be printed to the console. |
| On Response       | [FOnArielResponse](#on-ariel-response) | -               | The event called when a response was received. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Ariel Text-To-Speech Local

C++ Function: 
```cpp
static void UArielBPLibrary::ArielTTSLocal()
```

This node calls the Ariel Local *(offline)* API using **HTTP** request with all defined parameters (model name, sentence, semitones, …). The response is sent through a multicast delegate event, [On Ariel Response](#on-ariel-response).

>[!IMPORTANT]
> You must have called the node [START ARIEL LOCAL](#start-ariel-local) before in order for the local requests to be processed. You only need to call this node once (i.e.: when the game starts).

![Ariel Text-To-Speech local node](/res/ariel_text_to_speech_local.png) |


### Parameters

| Name              | Type           | Default value     | Description |
| ----------------- | -------------- | ----------------- | ----------- |
| Model Name        | const FString& | *empty string*    | The model name used for generation. The model must have been installed locally. See *[Add local voice](/doc/Local.md#add-local-voice)* for more details. |
| Sentence          | const FString& | *empty string*    | The sentence of the speech. |
| High Framerate    | const bool     | `false`           | Generate an audio with a frame rate of 44.1KHz instead of 22.05KHz. |
| Stereo            | const bool     | `false`           | Duplicate the mono channels into stereo channels. <span style="color: red;">**WARNING:**</span> This feature is currently not working as expected and will result as a slowed and pitched down speech. Do not use it until the issue is resolved. |
| Volume            | const int      | `0`dB             | Amplify or reduce the volume specified in dB. **Can be positive or negative**. |
| Semitones         | const int      | `+0`st            | Shifts the sound by the given semitones. **Can be positive or negative**. |
| Speed             | const float    | x`1.0`            | Increase or decrease the sound speed. **Must be greater than 0**. |
| Logs              | const bool     | `true`           | Indicate if logs should be printed to the console. |
| On Response       | [FOnArielResponse](#on-ariel-response) | -               | The event called when a response was received. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Audio WAV bytes to SoundWave

C++ Function: 
```cpp
static USoundWave* UArielBPLibrary::WavBytesToSoundWave()
```

Create a new SoundWave object from the generated audio WAV file byte array. See [Ariel Text-To-Speech](#ariel-text-to-speech) and [On Ariel Response](#on-ariel-response) for more details on how to generate the audio bytes.

![Audio WAV bytes to SoundWave node](/res/audio_wav_bytes_to_soundwave.png)

### Parameters

| Name        | Type                   | Default value | Description |
| ----------- | ---------------------- | ------------- | ----------- |
| Audio Bytes | const TArray\<uint8\>& | -             | The WAV file bytes. **Warning:** Must be PCM-16 for Unreal Engine! |
| Logs        | const bool             | `true`       | Indicate if logs should be printed to the console. |

### Return values

| Name         | Type        | Description |
| ------------ | ----------- | ----------- |
| Success      | bool&       | Indicate if the SoundWave object have been successfully created. |
| Out Reason   | FString&    | The SoundWave creation error message. |
| Return Value | USoundWave* | The created SoundWave Asset, or `nullptr` if the Asset couldn't be created. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Start Local Ariel

C++ Function:
```cpp
static void UArielBPLibrary::StartLocalExecutable()
```

Start the ariel local executable API, managed by the Subsystem. Calling this node while the executable was already running does nothing. You can change the local port used in the [Plugin project settings](/doc/Others.md#plugin-project-settings). The port must not be already used by an other process.

![Start local ariel node](/res/start_ariel_subsystem.png)

### Parameters

| Name           | Type                   | Default value | Description |
| -------------- | ---------------------- | ------------- | ----------- |
| On Initialized | [FOnArielInitialized](#on-ariel-initialized) | - | The event called when the local executable is ready, or if an error occured during startup. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Stop Local Ariel

C++ Function:
```cpp
static void UArielBPLibrary::StopLocalExecutable()
```

Stop the ariel local executable API, managed by the Subsystem. Calling this node will also remove all remaining local entries in the queue. See *[Local executable lifecycle](/doc/Local.md#local-executable-lifecycle)* for more details.

![Stop local ariel node](/res/stop_ariel_subsystem.png)

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

---

<br/><br/>

# Delegates (Events)

## On Ariel Response

C++ Declaration: `FOnArielResponse`

Use the nodes *Add Custom Event...* or *Create Event* to bind the [Ariel Text-To-Speech](#ariel-text-to-speech) and [Ariel Text-To-Speech Local](#ariel-text-to-speech-local) *"On Response"* delegate to a Blueprint Event or Function.

![On ariel response node](/res/on_ariel_response_1.png)<br/>
![On ariel response 2 node](/res/on_ariel_response_2.png)

### Return values

| Name              | Type                  | Description |
| ----------------- | --------------------- | ----------- |
| Success           | bool                  | Indicate if the response audio bytes have successfully been downloaded. |
| File Bytes        | const TArray\<uint8\>&  | The generated audio file bytes array, if the request was successful. |
| Error Message     | const FString&        | The error message, if the request was not successful. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## On Ariel Speakers Available

C++ Declaration: `FOnArielSpeakersAvailable`

Use the nodes *Add Custom Event...* or *Create Event* to bind the [Get available Speakers](#get-available-speakers) *"On Speakers Available"* delegate to a Blueprint Event or Function.

![On ariel speakers available node](/res/on_speakers_available_1.png)<br/>
![On ariel speakers available 2 node](/res/on_speakers_available_2.png)<br/>

### Return values

| Name     | Type                  | Description |
| -------- | --------------------- | ----------- |
| Speakers | TArray\<[FArielSpeaker](#ariel-speaker-farielspeaker)\> | The list of available speakers. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## On Ariel Initialized

C++ Declaration: `FOnArielInitialized`

Use the nodes *Add Custom Event...* or *Create Event* to bind the [Start Local Ariel](#start-local-ariel) *"On Initialized"* delegate to a Blueprint Event or Function.

![On ariel initialized node](/res/on_ariel_initialized_1.png)<br/>
![On ariel initialized 2 node](/res/on_ariel_initialized_2.png)<br/>

### Return values

| Name    | Type | Description |
| ------- | ---- | ----------- |
| Success | bool | Indicate if the Ariel local executable have been successfully started. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## On Check Ariel Available Response

C++ Declaration: `FOnCheckArielAvailableResponse`

Use the nodes *Add Custom Event...* or *Create Event* to bind the [Is Connected to Internet](#is-connected-to-internet) *"On Response"* delegate to a Blueprint Event or Function.

![On ariel connected node](/res/on_ariel_connected_1.png)<br/>
![On ariel connected 2 node](/res/on_ariel_connected_2.png)<br/>

### Return values

| Name    | Type | Description |
| ------- | ---- | ----------- |
| Success | bool | Indicate if the connection to Ariel remote API is successful. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

---

<br/><br/>

# Utilities

The following nodes have been created to help the usage of the Ariel plugin, but they are not part of the main plugin usage. The nodes below can be used in runtime and packaged projects, unlike the nodes described in the [Editor](#editor-only-1) section.

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Get Ariel Local Executable Status (Pure)

C++ Function:
```cpp
static EArielSubsystemStatus UArielBPLibrary::GetSubsystemStatus()
```

Get the current local executable status. See [Ariel Local Executable Status](#ariel-local-executable-status-earielsubsystemstatus).

![get ariel local executable status node](/res/get_local_executable_status.png)

### Return values

| Name         | Type | Description |
| ------------ | ---- | ----------- |
| Return Value | [EArielSubsystemStatus](#ariel-local-executable-status-earielsubsystemstatus) | The current local executable status. |


## Get available Speakers

C++ Function: 
```cpp
static void UArielBPLibrary::GetAvailableSpeakers()
```

Get the available speakers list. For remote speakers, it use the Api-Key provided in Ariel [Plugin project settings](/doc/Others.md#plugin-project-settings) to retrieve all remote speakers. For local speakers, it checks the model files installed in `Plugins/Ariel/Local/models`. See [On Ariel Speakers Available](#on-ariel-speakers-available).

![Get available Speakers node](/res/get_available_speakers.png)

### Parameters

| Name                  | Type       | Default Value | Description |
| --------------------- | ---------- | ------------- | ----------- |
| Get Local Speakers    | const bool | `true`        | Indicate if it should scan and include local speakers models. |
| Get Remote Speakers   | const bool | `true`        | Indicate if it should request and include remote speakers. |
| Logs                  | const bool | `true`       | Indicate if logs should be printed to the console. |
| On Speakers Available | [FOnArielSpeakersAvailable](#on-ariel-speakers-available) | - | The event called when a response was recived. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Get Number Channels From SoundWave (Pure)

C++ Function:
```cpp
static int UArielBPLibrary::GetNumChannels() 
```

Get the number of channels from the SoundWave.

![Get channels SoundWave](/res/get_channels_soundwave.png)

### Parameters

| Name       | Type          | Default Value | Description |
| ---------- | ------------- | ------------- | ----------- |
| Sound Wave | *USoundWave** | -             | The SoundWave to get number of channels. |

### Return values

| Name         | Type | Description |
| ------------ | ---- | ----------- |
| Return Value | int  | The number of channels of the SoundWave. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Get Sample Rate From SoundWave (Pure)

C++ Function:
```cpp
static int UArielBPLibrary::GetSampleRate() 
```

Get the sample rate from the SoundWave based on the current platform.

![Get samplerate SoundWave](/res/get_samplerate_soundwave.png)

### Parameters

| Name       | Type          | Default Value | Description |
| ---------- | ------------- | ------------- | ----------- |
| Sound Wave | *USoundWave** | -             | The SoundWave to get sample rate. |

### Return values

| Name         | Type | Description |
| ------------ | ---- | ----------- |
| Return Value | int  | The sample rate of the SoundWave. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Is Connected to Internet

C++ Function:
```cpp
static void UArielBPLibrary::IsConnectedToInternet() 
```

Check if the ariel online (remote) API can be reached. See [On Check Ariel Available Response](#on-check-ariel-available-response).

![is connected to internet node](/res/is_connected_to_internet.png)

### Parameters

| Name        | Type          | Default Value | Description |
| ----------- | ------------- | ------------- | ----------- |
| Logs        | const bool    | `true`       | Indicate if logs should be printed to the console. |
| On Response | [FOnCheckArielAvailableResponse](#on-check-ariel-available-response) | - | The event called when a response was received. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Scheme filename

C++ Function: 
```cpp
static FString UArielBPLibrary::SchemeFilename()
```

Replace shamed templates with the actual value for the Ariel filename.

You can use the schemes below to customize the name of the generated audio:

* `{speaker}` The name of the speaker.
* `{date}` The current date (from OS).
* `{time}` The current time (from OS).
* `{datetime}` The current date time (from OS).
* `{uuid}` The UUID (or GUID).
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
<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

---

<br/><br/>

# Editor only

The following nodes can **ONLY** be used when the Unreal Editor is running. The nodes won't be compiled on packaged projects and will result as a crash if they are called anyway. Please be careful when using these nodes.

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Show folder selection dialog

C++ Function: 
```cpp
static bool UArielEditorLibrary::ShowFolderSelectionDialog()
```

Open the Operating System folder selection dialog. This allows to select a folder located **outside** the project.

![Show folder selection dialog node](/res/show_folder_selection_dialog.png)

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Selected Dir | FString& | The absolute directory path (Unix style, with `/`). |
| Return value | bool     | True if a folder was selected by the user, false otherwise. |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Save bytes to file

C++ Function: 
```cpp
static bool UArielEditorLibrary::SaveToFile()
```

Write the given bytes to a file. If the file already exists, it will be overwritten. You can use this function to write other file than Ariel audio files. In this case, do not forget to put the file extension with the filename. 

![Save bytes to file node](/res/save_bytes_to_file.png)

### Parameters

| Name          | Type                  | Default value  | Description |
| ------------- | --------------------- | -------------- | ----------- |
| Bytes         | const TArray\<uni8\>& | -              | The bytes to write in the file. |
| Filename      | const FString&        | `ArielAudio`   | The file name. You can specify the file extension as well (i.e: 'ArielAudio.ogg'). |
| DirectoryPath | const FDirectoryPath& | -              | The directory where the file will be written. Can be inside or outside the project directory. |
| Format        | const [EArielAudioFormat](#ariel-audio-format-earielaudioformat) | `wav`| The audio format used for file extension (if not already provided with the filename). |
| Logs          | const bool            | `true`         | Indicate if logs should be printed to the console. |

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Out Path     | FString& | The absolute file path (Unix style, with `/`), fully qualified. |
| Return value | bool     | True if the file was (over)written, false otherwise (like an invalid path or a permission error). |

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Get Documentation URL (Pure)

C++ Function:
```cpp
static FString UArielEditorLibrary::GetDocumentationURL()
```

Get the current Ariel plugin documentation URL.

![Get documentation URL node](/res/get_documentation_url.png)

### Return values

| Name         | Type     | Description |
| ------------ | -------- | ----------- |
| Return value | FString  | The documentation URL (static, inline). Use it with the Unreal node *Launch URL*. |

<!------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

---

<br/>

# Structures

C++ and Blueprint structs defined by the Ariel plugin.

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Ariel Speaker *(FArielSpeaker)*

C++ Declaration: `FArielSpeaker`

The JSON structure of a speaker returned by the Ariel API. You can find the speakers list with all details [here](/README.md#speakers). The Speaker list can vary depending on your API key inside [Project settings](/doc/Others.md#plugin-project-settings) and the local model [voices installed](/doc/Local.md#add-local-voice). See [Get available Speakers](#get-available-speakers).

![Ariel speaker break node](/res/ariel_speaker.png)

### Variables

| Name      | Type              | Editor           | Blueprint | Description |
| --------- | ----------------- | ---------------- | --------- | ----------- |
| ID        | int               | Visible Anywhere | Read-only | The Ariel Speaker identifier. |
| Name      | FString           | Visible Anywhere | Read-only | The Ariel Speaker name. |
| Gender    | FString           | Visible Anywhere | Read-only | The Ariel Speaker gender. Gender is currently not in use. |
| Languages | TArray\<FString\> | Visible Anywhere | Read-only | The Ariel Speaker supported language(s). |
| Emotions  | TArray\<FString\> | Visible Anywhere | Read-only | The Ariel Speaker supported emotion(s). Emotions are currently not in use. |
| Local Execution | bool        | Visible Anywhere | Read-only | If an available speaker can be used for local or remote execution. |

<!------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

---

<br/><br/>

# Enumerations

C++ and Blueprint enumerations defined by the Ariel plugin.

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Ariel Audio Effect *(EArielAudioEffect)*

C++ Declaration: `EArielAudioEffect`

This enum contains all Ariel audio effects available. See [🎚️ Audio effects](/doc/Features.md#-audio-effects) for more details.

![Ariel audio effect make node](/res/ariel_audio_effect.png)<br/>
*Hover the cursor on a value to see more details about it.*

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

<!------------------------------------------------------------------------------------------------------------------------------->
<br/>

## Ariel Audio Format *(EArielAudioFormat)*

C++ Declaration: `EArielAudioFormat`

This enum contains all supported ariel audio file formats.

![Ariel audio format make node](/res/ariel_audio_format.png)<br/>
*Hover the cursor on a value to see more details about it.*

### Values

| Name | Description |
| ---- | ----------- |
| WAV  | PCM-16 RIFF Waveform audio file. |
| MP3  | MPEG-1/2 audio file. |

## Ariel Local Executable Status

C++ Declaration: `EArielSubsystemStatus`

This enum contains all possible status for the local executable. See [Get Ariel Local Executable Status](#get-ariel-local-executable-status-pure).

![ariel subsystem status make node](/res/ariel_subsystem_status.png)<br/>

### Values

| Name     | Description |
| -------- | ----------- |
| None     | No status was found by the subsystem thread. This should only happens before the plugin was loaded and after it was destroyed. |
| Idle     | The subsystem thread is not doing anything. The local executable is not started. |
| Starting | The subsystem thread is starting the local executable. |
| Running  | The subsystem thread is running the local executable. |
| Error    | There was an error during the subsystem startup or generation. If the error occurs during generation and an other request is performed, then the status can change to `Running` again. |
