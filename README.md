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
    [⚙️ Local executable](/doc/Local.md)<br/>

### [Features](/doc/Features.md) *(Remote only)*
    [🎚️ Audio effects](/doc/Features.md#Audio%20effects)<br/>
    [📝 Tags](/doc/Features.md#Tags)<br/>

### [API Reference](/doc/API.md)
    [Ariel Text-To-Speech](/doc/API.md#ariel-text-to-speech)<br/>
    [Ariel Text-To-Speech Local](/doc/API.md#ariel-text-to-speech-local)<br/>
    [Audio WAV bytes to SoundWave](/doc/API.md#audio-wav-bytes-to-soundwave)<br/>
    [Start Local Ariel](/doc/API.md#start-local-ariel)<br/>
    [Stop Local Ariel](/doc/API.md#stop-local-ariel)<br/>
####     [Delegates (Events)](/doc/API.md#delegates-events-1)
        [On Ariel Response](/doc/API.md#on-ariel-response)<br/>
        [On Ariel Speakers Available](/doc/API.md#on-ariel-speakers-available)<br/>
        [On Ariel Initialized](/doc/API.md#on-ariel-initialized)<br/>
        [On Check Ariel Available Response](/doc/API.md#on-check-ariel-available-response)<br/>
####     [Utilities](/doc/API.md#utilities-1)
        [Get Ariel Local Executable Status](/doc/API.md#get-ariel-local-executable-status-pure) <b style="color: red">\*</b><br/>
        [Get available Speakers](/doc/API.md#get-available-speakers)<br/>
        [Get Number Channels From SoundWave](/doc/API.md#get-number-channels-from-soundwave-pure) <b style="color: red">\*</b><br/>
        [Get Sample Rate From SoundWave](/doc/API.md#get-sample-rate-from-soundwave-pure) <b style="color: red">\*</b><br/>
        [Is Connected to Internet](/doc/API.md#is-connected-to-internet)<br/>
        [Scheme filename](/doc/API.md#scheme-filename)<br/>
####     [Editor only](/doc/API.md#editor-only-1)
        [Show folder selection dialog](/doc/API.md#show-folder-selection-dialog)<br/>
        [Save bytes to file](/doc/API.md#save-bytes-to-file)<br/>
        [Get Documentation URL](/doc/API.md#get-documentation-url-pure) <b style="color: red">\*</b><br/>
####     [Structures](/doc/API.md#structures-1)
        [Ariel Speaker](/doc/API.md#ariel-speaker-farielspeaker)<br/>
####     [Enumerations](/doc/API.md#enumerations-1)
        [Ariel Audio Format](/doc/API.md#ariel-audio-format-earielaudioformat)<br/>
        [Ariel Audio Effect](/doc/API.md#ariel-audio-effect-earielaudioeffect)<br/>
        [Ariel Local Executable Status](/doc/API.md#ariel-local-executable-status-earielsubsystemstatus)<br/>

*<b style="color:red">\*</b>Pure functions*

### [Others](doc/Others.md)
    [Plugin project settings](/doc/Others.md#plugin-project-settings)<br/>
    [Package a project](/doc/Others.md#package-a-project)<br/>

<br/>

If you have any question, do not hesitate to contact us through our [Discord server](https://discord.gg/qDMwNCDE8X) or by mail at [support@xandimmersion.com](mailto:support@xandimmersion.com).

## Speakers

>[!NOTE]
The list of remote speakers available highly depends on the API key used. The list below contains all speakers available with the default API key. <br/>
Local speakers are not listed here, but all voice models that you have installed by following [this article](/doc/Local.md#add-local-voice) can be used.

>[!TIP]
> Voices included in the [**Fantasy** Pack](#fantasy-pack): *Orc, Urukhai, DarkElve, HalfElve, HighElve, WoodElve, Dis, Dwarf, Goblin, Nordman, Duergar*

>[!TIP]
> Voices included in the [**Alien & demon** Pack](#alien-and-demon-pack): *Xalith, Yorgon, Zephyr, Nefraxis, Vorgrim, Zaltharion*

### Base pack

| **Name**       | Gender | Age   | Language(s)                                                                                                                              |
| -------------- | ------ | ----- | -----------------------------------------------------------------------------------------------------------------------------------------|
| **Ada**        | Female | Adult | English, Bulgarian, Chinese, Classic arabic, Croatian, Czech, Danish, Dutch, Filipino, Finnish, French, German, Greek, Hindi, Indonesian, Italian, Japenese, Korean, Malay, Polish, Portugese, Romanian, Russian, Slovak, Spanish, Swedish, Tamil, Turkish, Ukrainian |
| **Alioth**     | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **David**      | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dulhan**     | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Elen**       | Female | Young | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Elizabeth**  | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Eve**        | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Henry**      | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Jake**       | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Jessy**      | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Mazarrin**   | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Michael**    | Male   | Kid   | English |
| **Ned**        | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Richard**    | Male   | Old   | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Riley**      | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Samantha**   | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Socrates**   | Male   | Old   | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Tom**        | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Triniac**    | Male   | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zenaya**     | Female | Adult | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |

### Fantasy pack

| **Name**       | Gender | Cat.  | Language(s)                                                                                                                              |
| -------------- | ------ | ----- | -----------------------------------------------------------------------------------------------------------------------------------------|
| **DarkElve**   | Male   | Elve  | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dis**        | Female | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Duergar**    | Male   | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Dwarf**      | Male   | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Goblin**     | Male   | Orc   | English, Bulgarian, Chinese, Classic arabic, Croatian, Czech, Danish, Dutch, Filipino, Finnish, French, German, Greek, Hindi, Indonesian, Italian, Japanese, Korean, Malay, Polish, Portuguese, Romanian, Russian, Slovak, Spanish, Swedish, Tamil, Turkish, Ukrainian |
| **HalfElve**   | Female | Elve  | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **HighElve**   | Male   | Elve  | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Nordman**    | Male   | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Orc**        | -      | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Urukhai**    | -      | Dwarf | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **WoodElve**   | Female | Elve  | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |


### Alien and demon pack

| **Name**       | Gender | Age   | Language(s)                                                                                                                              |
| -------------- | ------ | ----- | -----------------------------------------------------------------------------------------------------------------------------------------|
| **Nefraxis**   | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Vorgrim**    | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Xalith**     | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Yorgon**     | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zaltharion** | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Zephyr**     | -      | -     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |


### Old voices (not available anymore - please go to https://create.xandimmersion.com)

| **Name**       | Language(s)                                                                                                                              |
| -------------- | -----------------------------------------------------------------------------------------------------------------------------------------|
| **Adriaan**    | Dutch                                                                                                                                    |
| **Adriano**    | Portuguese                                                                                                                               |
| **Advika**     | English                                                                                                                                  |
| **Aeron**      | English                                                                                                                                  |
| **Alexandra**  | Romanian                                                                                                                                 |
| **Alix**       | French                                                                                                                                   |
| **Angharad**   | Welsh                                                                                                                                    |
| **Anke**       | Dutch                                                                                                                                    |
| **Anna**       | Icelandic                                                                                                                                |
| **Arnaud**     | French                                                                                                                                   |
| **Baldur**     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Barbara**    | English                                                                                                                                  |
| **Camilla**    | Norwegian                                                                                                                                |
| **Capucine**   | French                                                                                                                                   |
| **Celine**     | French                                                                                                                                   |
| **Charlotte**  | English                                                                                                                                  |
| **Daiyu**      | Chinese                                                                                                                                  |
| **Elijah**     | English                                                                                                                                  |
| **Elna**       | English                                                                                                                                  |
| **Emma**       | Danish                                                                                                                                   |
| **Eva**        | Swedish                                                                                                                                  |
| **Farah**      | Classic arabic                                                                                                                           |
| **Felix**      | German                                                                                                                                   |
| **Francisca**  | Spanish                                                                                                                                  |
| **Gabriella**  | Italian                                                                                                                                  |
| **Grace**      | English                                                                                                                                  |
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
| **Mike**       | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Onkar**      | English                                                                                                                                  |
| **Oriane**     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Oscar**      | Danish                                                                                                                                   |
| **Pati**       | Portuguese                                                                                                                               |
| **Patricia**   | English                                                                                                                                  |
| **Paul**       | English                                                                                                                                  |
| **Pedro**      | Portuguese                                                                                                                               |
| **Piotr**      | Polish                                                                                                                                   |
| **Rika**       | Japanese                                                                                                                                 |
| **Riley**      | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Rosa**       | Spanish                                                                                                                                  |
| **Sigriour**   | Icelandic                                                                                                                                |
| **Sophia**     | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Stephanie**  | French                                                                                                                                   |
| **Susan**      | English                                                                                                                                  |
| **Tabata**     | Portuguese                                                                                                                               |
| **Tanaka**     | Japanese                                                                                                                                 |
| **Theresa**    | German                                                                                                                                   |
| **Thomas**     | English                                                                                                                                  |
| **Tom**        | English, Chinese, Classic arabic, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish |
| **Viktor**     | Russian                                                                                                                                  |
| **William**    | English                                                                                                                                  |
