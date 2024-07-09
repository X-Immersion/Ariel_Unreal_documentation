# API Reference

**[← Table of contents](/README.md)**

### On this page

[Ariel Text-To-Speech](#ariel-text-to-speech)<br/>
[On Ariel Response](#on-ariel-response)<br/>
[Audio wav bytes to SoundWave](#audio-wav-bytes-to-soundwave)<br/>
#### [Utilities](#utilities-1)
    [Get available Speakers](#get-available-speakers-pure) <b style="color:red">\*</b> <br/>
    [Get available Speakers (filtered)](#get-available-speakers-filtered-pure) <b style="color: red">\*</b><br/>
    [Scheme filename](TODO)<br/>

#### [Editor-only](TODO)
    [Get Documentation URL](TODO) <b style="color: red">\*</b><br/>
    [Show folder selection dialog](TODO)<br/>
    [Save bytes to file](TODO)<br/>
#### [Structures](TODO)
    [Ariel Speaker](TODO)<br/>
#### [Enumerations](TODO)
    [Ariel Audio Format](TODO)<br/>
    [Ariel Audio Effect](TODO)<br/>
*<b style="color:red">\*</b>Pure functions*

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
| Audio Format      | const EArielAudioFormat | `wav`    | The audio format of the generated file. See [Ariel Audio Effect](TODO). |
| Volume            | const int      | `0`dB             | Amplify or reduce the volume specified in dB. |
| High Framerate    | const bool     | `false`           | Generate an audio with a frame rate of 44.1KHz instead of 22.05KHz. |
| Semitones         | const int      | `+0`st            | Shifts the sound by the given semitones. **Can be positive or negative**. |
| Speed             | const float    | x`1.0`            | Increase or decrease the sound speed. **Must be greater than 0**. |
| Audio Effects     | const TArray\<EArielAudioEffect\>& | *empty array* (no effects) | List of all audio effects who will be applied to the audio. See [🎶 Audio effects](/doc/Features.md#-audio-effects) and [Ariel Audio Effect](TODO). |
| Logs              | const bool     | `false`           | Indicate if logs should be printed to the console. |
| On Response       | FOnArielResponse | -               | The event called when a response was received. See [On Ariel Response](#on-ariel-response). |

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

## Audio wav bytes to SoundWave

C++ Function: `UArielBPLibrary::WavBytesToSoundWave`

Create a new SoundWave object from the generated audio wav file byte array. See [Ariel Text-To-Speech](#ariel-text-to-speech) and [On Ariel Response](#on-ariel-response) for more details on how to generate the audio bytes.

![Audio wav bytes to SoundWave node](/res/audio_wav_bytes_to_soundwave.png)

### Parameters

| Name        | Type                 | Default value | Description |
| ----------- | -------------------- | ------------- | ----------- |
| Audio Bytes | const TArray\<uint8\>& | *empty array* | The wav file bytes. **Warning:** Must be PCM-16 for Unreal Engine! |

### Return values

| Name         | Type        | Description |
| ------------ | ----------- | ----------- |
| Success      | bool&       | Indicate if the SoundWave object have been successfully created. |
| Out Reason   | FString&    | The SoundWave creation error message. |
| Return Value | USoundWave* | The created SoundWave Asset, or `nullptr` if the Asset couldn't be created. |

# Utilities

The following nodes have been created to help the usage of the Ariel plugin, but they are not part of the main plugin usage. The nodes below can be used in runtime and packaged projects, unlike the nodes described in the [Editor](#editor-only-1) section.

## Get available Speakers (pure)

C++ Function: `UArielBPLibrary::GetSpeakersFromSettings`

Get the available speakers list from the project settings.

![Get available Speakers node](/res/get_available_speakers.png)

### Return values

| Name         | Type                    | Description |
| ------------ | ----------------------- | ----------- |
| Return value | TArray\<FArielSpeaker\> | The list of available speakers. See [Ariel Speaker](TODO) |

## Get available Speakers (filtered) (pure)

C++ Function: `UArielBPLibrary::GetSpeakersFiltered`

Get available Ariel speakers that correspond to the desired gender and language.

![Get available Speakers filtered node](/res/get_available_speakers_filtered.png)

### Parameters

| Name        | Type                 | Default value | Description |
| ----------- | -------------------- | ------------- | ----------- |
