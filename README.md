# Ariel Plugin for Unreal Engine - Documentation


![ariel thumbnail](/res/ariel_thumbnail.png)

## Table of contents

→ If you are more comfortable with a video, please watch our [YouTube tutorial video](https://youtu.be/78WMagHKaow)!<br/>
**Note:** *The video was recorded with Ariel v.1.0.5. Some features might not be presented in the video,  while some other might have changed a bit.*

### [Setup](/doc/Setup.md)
    [Prerequisites](/doc/Setup.md#prerequisites)<br/>
    [Installation](/doc/Setup.md#installation)<br/>

### [Quickstart](/doc/Quickstart.md)

    [🎬 Editor pre-generation](/doc/Quickstart.md#-editor-pre-generation)<br/>
    [🎤 Runtime generation](/doc/Quickstart.md#-runtime-generation)<br/>

### [Features](/doc/Features.md) (Remote only)
    [🎚️ Audio effects](/doc/Features.md#Audio%20effects)<br/>
    [📝 Tags](/doc/Features.md#Tags)<br/>
    [⚙️ Local executable](/doc/Local.md)<br/>

### [API Reference](/doc/API.md)
    [Ariel Text-To-Speech](/doc/API.md#ariel-text-to-speech)<br/>
    [Ariel Text-To-Speech Local](/doc/API.md#ariel-text-to-speech-local)<br/>
    [Audio WAV bytes to SoundWave](/doc/API.md#audio-wav-bytes-to-soundwave)<br/>
    [Start Ariel Local](/doc/API.md#start-ariel-local)<br/>
    [Stop Ariel Local](/doc/API.md#stop-ariel-local)<br/>
####     [Delegates (Events)](/doc/API.md#delegates-events-1)
        [On Ariel Response](/doc/API.md#on-ariel-response)<br/>
        [On Ariel Speakers Available](/doc/API.md#on-ariel-speakers-available)<br/>
        [On Ariel Initialized](/doc/API.md#on-ariel-initialized)<br/>
        [On Check Ariel Available Response](/doc/API.md#on-check-ariel-available-response)<br/>
####     [Utilities](/doc/API.md#utilities-1)
        [Get Ariel Local Executable Status](/doc/API.md#get-ariel-local-executable-status-pure) <b style="color: red">\*</b><br/>
        [Get available Speakers](/doc/API.md#get-available-speakers)<br/>
        [Get Number Channels From SoundWave](/doc/API.md#get-number-channels-from-soundwave-pure) <b style="color: red">\*</b><br/>
        [Get Sample Rate From SoundWave](/doc/API.md#get-sample-rate-from-soundwave-pure) <b style="color: red">\*</b><br/>
        [Is Connected to Internet](/doc/API.md#is-connected-to-internet)<br/>
        [Scheme filename](/doc/API.md#scheme-filename)<br/>
####     [Editor only](/doc/API.md#editor-only-1)
        [Show folder selection dialog](/doc/API.md#show-folder-selection-dialog)<br/>
        [Save bytes to file](/doc/API.md#save-bytes-to-file)<br/>
        [Get Documentation URL](/doc/API.md#get-documentation-url-pure) <b style="color: red">\*</b><br/>
####     [Structures](/doc/API.md#structures-1)
        [Ariel Speaker](/doc/API.md#ariel-speaker-farielspeaker)<br/>
####     [Enumerations](/doc/API.md#enumerations-1)
        [Ariel Audio Format](/doc/API.md#ariel-audio-format-earielaudioformat)<br/>
        [Ariel Audio Effect](/doc/API.md#ariel-audio-effect-earielaudioeffect)<br/>
        [Ariel Local Executable Status](/doc/API.md#ariel-local-executable-status-earielsubsystemstatus)<br/>

*<b style="color:red">\*</b>Pure functions*

### [Others](doc/Others.md)
    [Plugin project settings](/doc/Others.md#plugin-project-settings)<br/>
    [Package a project](/doc/Others.md#package-a-project)<br/>

<br/>

If you have any question, do not hesitate to contact us through our [Discord server](https://discord.gg/qDMwNCDE8X) or by mail at [contact@xandimmersion.com](mailto:contact@xandimmersion.com)

## Speakers

>[!NOTE]
The list of remote speakers available highly depends on the API key used. The list below contains all speakers available with the default API key. <br/>
Local speakers are not listed here, but all voice models that you have installed by following [this article](/doc/Local.md#add-local-voice) can be used.

>[!TIP]
> Voices included in the **Fantasy** Pack: *Orc, Urukhai, DarkElve, HalfElve, HighElve, WoodElve, Dis, Dwarf, Goblin, Nordman*

>[!TIP]
> Voices included in the **Alien & demon** Pack: *Xalith, Yorgon, Zephyr, Nefraxis, Vorgrim, Zaltharion*

| **Name**       | Language(s)                                                                                                                              |
| -------------- | -----------------------------------------------------------------------------------------------------------------------------------------|
| **Adriaan**    | Dutch                                                                                                                                    |
| **Adriano**    | Portuguese                                                                                                                               |
| **Advika**     | English                                                                                                                                  |
| **Aeron**      | English                                                                                                                                  |
| **Alexandra**  | Romanian                                                                                                                                 |
| **Alioth**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Alix**       | French                                                                                                                                   |
| **Angharad**   | Welsh                                                                                                                                    |
| **Anke**       | Dutch                                                                                                                                    |
| **Anna**       | Icelandic                                                                                                                                |
| **Arnaud**     | French                                                                                                                                   |
| **Baldur**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Barbara**    | English                                                                                                                                  |
| **Camilla**    | Norwegian                                                                                                                                |
| **Capucine**   | French                                                                                                                                   |
| **Celine**     | French                                                                                                                                   |
| **Charlotte**  | English                                                                                                                                  |
| **Daiyu**      | Chinese                                                                                                                                  |
| **DarkElve**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **David**      | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dis**        | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Duergar**    | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dulhan**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dwarf**      | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Elen**       | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Elijah**     | English                                                                                                                                  |
| **Elizabeth**  | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Elna**       | English                                                                                                                                  |
| **Emma**       | Danish                                                                                                                                   |
| **Eva**        | Swedish                                                                                                                                  |
| **Farah**      | Classic arabic                                                                                                                           |
| **Felix**      | German                                                                                                                                   |
| **Francisca**  | Spanish                                                                                                                                  |
| **Gabriella**  | Italian                                                                                                                                  |
| **Goblin**     | Bulgarian, Chinese, Classic arabic, Croatian, Czech, Danish, Dutch, English, Filipino, Finnish, French, German, Greek, Hindi, Indonesian, Italian, Japanese, Korean, Malay, Polish, Portuguese, Romanian, Russian, Slovak, Spanish, Swedish, Tamil, Turkish, Ukrainian |
| **Grace**      | English                                                                                                                                  |
| **HalfElve**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **HighElve**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Inessa**     | Russian                                                                                                                                  |
| **Jack**       | English                                                                                                                                  |
| **Jan**        | Polish                                                                                                                                   |
| **Josefina**   | Spanish                                                                                                                                  |
| **Juliana**    | Portuguese                                                                                                                               |
| **Katarzyna**  | Polish                                                                                                                                   |
| **Leticia**    | Spanish                                                                                                                                  |
| **Linda**      | English                                                                                                                                  |
| **Lorenzo**    | Italian                                                                                                                                  |
| **Malgorzata** | Polish                                                                                                                                   |
| **Margarita**  | Spanish                                                                                                                                  |
| **Maria**      | German                                                                                                                                   |
| **Mary**       | English                                                                                                                                  |
| **Mateo**      | Spanish                                                                                                                                  |
| **Mesut**      | Turkish                                                                                                                                  |
| **Mia**        | English                                                                                                                                  |
| **Michael**    | English                                                                                                                                  |
| **Miguel**     | Spanish                                                                                                                                  |
| **Mike**       | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Nefraxis**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Nordman**    | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Onkar**      | English                                                                                                                                  |
| **Orc**        | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Oriane**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Oscar**      | Danish                                                                                                                                   |
| **Pati**       | Portuguese                                                                                                                               |
| **Patricia**   | English                                                                                                                                  |
| **Paul**       | English                                                                                                                                  |
| **Pedro**      | Portuguese                                                                                                                               |
| **Piotr**      | Polish                                                                                                                                   |
| **Rika**       | Japanese                                                                                                                                 |
| **Riley**      | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Rosa**       | Spanish                                                                                                                                  |
| **Sigriour**   | Icelandic                                                                                                                                |
| **Socrates**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Sophia**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Stephanie**  | French                                                                                                                                   |
| **Susan**      | English                                                                                                                                  |
| **Tabata**     | Portuguese                                                                                                                               |
| **Tanaka**     | Japanese                                                                                                                                 |
| **Theresa**    | German                                                                                                                                   |
| **Thomas**     | English                                                                                                                                  |
| **Tom**        | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Urukhai**    | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Viktor**     | Russian                                                                                                                                  |
| **Vorgrim**    | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **William**    | English                                                                                                                                  |
| **WoodElve**   | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Xalith**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Yorgon**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zaltharion** | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zenaya**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zephyr**     | Chinese, Classic arabic, Czech, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |

