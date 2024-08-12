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

### [Features](/doc/Features.md)
    [🎚️ Audio effects](/doc/Features.md#Audio%20effects)<br/>
    [📝 Tags](/doc/Features.md#Tags)<br/>

### [API Reference](/doc/API.md)
    [Ariel Text-To-Speech](/doc/API.md#ariel-text-to-speech)<br/>
    [On Ariel Response](/doc/API.md#on-ariel-response)<br/>
    [Audio WAV bytes to SoundWave](/doc/API.md#audio-wav-bytes-to-soundwave)<br/>
####     [Utilities](/doc/API.md#utilities-1)
        [Get available Speakers](/doc/API.md#get-available-speakers-pure) <b style="color:red">\*</b> <br/>
        [Get available Speakers (filtered)](/doc/API.md#get-available-speakers-filtered-pure) <b style="color: red">\*</b><br/>
        [Scheme filename](/doc/API.md#scheme-filename)<br/>
####     [Editor only](/doc/API.md#editor-only-1)
        [Show folder selection dialog](/doc/API.md#show-folder-selection-dialog)<br/>
        [Save bytes to file](/doc/API.md#save-bytes-to-file)<br/>
        [Get Documentation URL](/doc/API.md#get-documentation-url) <b style="color: red">\*</b><br/>
####     [Structures](/doc/API.md#structures-1)
        [Ariel Speaker](/doc/API.md#ariel-speaker-farielspeaker)<br/>
####     [Enumerations](/doc/API.md#enumerations-1)
        [Ariel Audio Format](/doc/API.md#ariel-audio-format-earielaudioformat)<br/>
        [Ariel Audio Effect](/doc/API.md#ariel-audio-effect-earielaudioeffect)<br/>
*<b style="color:red">\*</b>Pure functions*

### [Others](doc/Others.md)
    [Plugin project settings](/doc/Others.md#plugin-project-settings)<br/>
    [Package a project](/doc/Others.md#package-a-project)<br/>

<br/>

If you have any question, do not hesitate to contact us through our [Discord server](https://discord.gg/qDMwNCDE8X) or by mail at [contact@xandimmersion.com](mailto:contact@xandimmersion.com)

## Speakers

| **Name**      | Type      | Gender            | Language(s) |
| ------------- | --------- | ----------------- | ------------ |
| **Sophia**    | *Premium*   | female (child)    | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Oriane**    | *Premium*   | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Dulhan**    | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Alioth**    | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Zenaya**    | *Premium*   | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Socrates**  | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **David**     | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Tom**       | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Baldur**    | *Premium*   | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Elizabeth** | *Premium*   | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Elen**      | *Premium*   | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Riley**     | *Premium*   | neutral           | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Orc**       | *Premium*   | neutral           | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Urukhai**   |*Premium*    | neutral           | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **HighElve**  |*Premium*    | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **DarkElve**  |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **HalfElve**  |*Premium*    | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **WoodElve**  |*Premium*    | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Dis**       |*Premium*    | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Dwarf**     |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Nordman**   |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Duergar**   |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Mike**      |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Yorgon**    |*Premium*    | male              | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Xalith**    |*Premium*    | female            | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Zephyr**    |*Premium*    | neutral           | English, Spanish, French, German, Italian, Portuguese, Polish, Turkish, Russian, Dutch, Czech, classic Arabic, Chinese, Japanese, Korean |
| **Farah**     |  Standard | female            | classic Arabic |
| **Daiyu**     |  Standard | female            | Chinese       |
| **Emma**      |  Standard | female            | danish        |
| **Oscar**     |  Standard | male              | danish        |
| **Anke**      |  Standard | female            | Dutch         |
| **Adriaan**   |  Standard | male              | Dutch         |
| **Mia**       |  Standard | female            | English       |
| **Grace**     |  Standard | female            | English       |
| **Jack**      |  Standard | male              | English       |
| **Charlotte** |  Standard | female            | English       |
| **Elijah**    |  Standard | male              | English       |
| **Advika**    |  Standard | female            | English       |
| **Onkar**     |  Standard | female            | English       |
| **Elna**      |  Standard | female            | English       |
| **Mary**      |  Standard | female (child)    | English       |
| **Linda**     |  Standard | female            | English       |
| **Patricia**  |  Standard | female            | English       |
| **Barbara**   |  Standard | female            | English       |
| **Susan**     |  Standard | female            | English       |
| **Paul**      |  Standard | male              | English       |
| **Michael**   |  Standard | male (child)      | English       |
| **William**   |  Standard | male (child)      | English       |
| **Thomas**    |  Standard | male              | English       |
| **Aeron**     |  Standard | male              | English       |
| **Capucine**  |  Standard | female            | French        |
| **Alix**      |  Standard | female            | French        |
| **Arnaud**    |  Standard | male              | French        |
| **Stephanie** |  Standard | female            | French        |
| **Celine**    |  Standard | female            | French        |
| **Maria**     |  Standard | female            | German        |
| **Theresa**   |  Standard | female            | German        |
| **Felix**     |  Standard | male              | German        |
| **Anna**      |  Standard | female            | Icelandic     |
| **Sigriour**  |  Standard | male              | Icelandic     |
| **Gabriella** |  Standard | female            | Italian       |
| **Lorenzo**   |  Standard | male              | Italian       |
| **Rika**      |  Standard | female            | Japanese      |
| **Tanaka**    |  Standard | male              | Japanese      |
| **Ji**-Ho     |  Standard | female            | Korean        |
| **Camilla**   |  Standard | female            | Norwegian     |
| **Katarzyna** |  Standard | female            | Polish        |
| **Malgorzata** | Standard | female            | Polish        |
| **Piotr**     |  Standard | male              | Polish        |
| **Jan**       |  Standard | male              | Polish        |
| **Tabata**    |  Standard | female            | Portuguese    |
| **Juliana**   |  Standard | female            | Portuguese    |
| **Pedro**     |  Standard | male              | Portuguese    |
| **Pati**      |  Standard | female            | Portuguese    |
| **Adriano**   |  Standard | male              | Portuguese    |
| **Alexandra** |  Standard | female            | romanian      |
| **Inessa**    |  Standard | female            | Russian       |
| **Viktor**    |  Standard | male              | Russian       |
| **Francisca** |  Standard | female            | Spanish       |
| **Margarita** |  Standard | female            | Spanish       |
| **Mateo**     |  Standard | male              | Spanish       |
| **Leticia**   |  Standard | female            | Spanish       |
| **Josefina**  |  Standard | female            | Spanish       |
| **Rosa**      |  Standard | female            | Spanish       |
| **Miguel**    |  Standard | male              | Spanish       |
| **Eva**       |  Standard | female            | swedish       |
| **Mesut**     |  Standard | female            | Turkish       |
| **Angharad**  |  Standard | female            | welsh         |
