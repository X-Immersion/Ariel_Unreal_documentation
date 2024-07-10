# Ariel Plugin for Unreal Engine - Documentation


![ariel thumbnail](/res/ariel_thumbnail.png)

**→ Buy the Ariel plugin from the Unreal marketplace here:** https://www.unrealengine.com/marketplace/en-US/product/ariel-voice-generation

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
    [🎶 Audio effects](/doc/Features.md#Audio%20effects)<br/>
    [📝 Tags](/doc/Features.md#Tags)<br/>

### [API Reference](/doc/API.md)
    [Ariel Text-To-Speech](/doc/API.md#ariel-text-to-speech)<br/>
    [On Ariel Response](/doc/API.md#on-ariel-response)<br/>
    [Audio wav bytes to SoundWave](/doc/API.md#audio-wav-bytes-to-soundwave)<br/>
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
    [Developers settings](TODO)<br/>
    [Package a project](TODO)<br/>

<br/>

If you have any question, do not hesitate to contact us through our [Discord server](https://discord.gg/qDMwNCDE8X) or by mail at [contact@xandimmersion.com](mailto:contact@xandimmersion.com)

## Speakers

| **Name**      | Type      | Gender            | Language(s) |
| ------------- | --------- | ----------------- | ------------ |
| **Sophia**    | Premium   | female (child)    | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Oriane**    | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Dulhan**    | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Alioth**    | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Zenaya**    | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Socrates**  | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **David**     | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Tom**       | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Baldur**    | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Elizabeth** | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Elen**      | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Riley**     | Premium   | neutral           | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Orc**       | Premium   | neutral           | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Urukhai**   | Premium   | neutral           | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **HighElve**  | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **DarkElve**  | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **HalfElve**  | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **WoodElve**  | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Dis**       | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Dwarf**     | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Nordman**   | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Duergar**   | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Mike**      | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Yorgon**    | Premium   | male              | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Xalith**    | Premium   | female            | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Zephyr**    | Premium   | neutral           | english, spanish, french, german, italian, portuguese, polish, turkish, russian, dutch, czech, classic arabic, chinese, japanese, korean |
| **Farah**     |  Standard | female            | classic arabic |
| **Daiyu**     |  Standard | female            | chinese       |
| **Emma**      |  Standard | female            | danish        |
| **Oscar**     |  Standard | male              | danish        |
| **Anke**      |  Standard | female            | dutch         |
| **Adriaan**   |  Standard | male              | dutch         |
| **Mia**       |  Standard | female            | english       |
| **Grace**     |  Standard | female            | english       |
| **Jack**      |  Standard | male              | english       |
| **Charlotte** |  Standard | female            | english       |
| **Elijah**    |  Standard | male              | english       |
| **Advika**    |  Standard | female            | english       |
| **Onkar**     |  Standard | female            | english       |
| **Elna**      |  Standard | female            | english       |
| **Mary**      |  Standard | female (child)    | english       |
| **Linda**     |  Standard | female            | english       |
| **Patricia**  |  Standard | female            | english       |
| **Barbara**   |  Standard | female            | english       |
| **Susan**     |  Standard | female            | english       |
| **Paul**      |  Standard | male              | english       |
| **Michael**   |  Standard | male (child)      | english       |
| **William**   |  Standard | male (child)      | english       |
| **Thomas**    |  Standard | male              | english       |
| **Aeron**     |  Standard | male              | english       |
| **Capucine**  |  Standard | female            | french        |
| **Alix**      |  Standard | female            | french        |
| **Arnaud**    |  Standard | male              | french        |
| **Stephanie** |  Standard | female            | french        |
| **Celine**    |  Standard | female            | french        |
| **Maria**     |  Standard | female            | german        |
| **Theresa**   |  Standard | female            | german        |
| **Felix**     |  Standard | male              | german        |
| **Anna**      |  Standard | female            | Icelandic     |
| **Sigriour**  |  Standard | male              | Icelandic     |
| **Gabriella** |  Standard | female            | italian       |
| **Lorenzo**   |  Standard | male              | italian       |
| **Rika**      |  Standard | female            | japanese      |
| **Tanaka**    |  Standard | male              | japanese      |
| **Ji**-Ho     |  Standard | female            | korean        |
| **Camilla**   |  Standard | female            | Norwegian     |
| **Katarzyna** |  Standard | female            | polish        |
| **Malgorzata** | Standard | female            | polish        |
| **Piotr**     |  Standard | male              | polish        |
| **Jan**       |  Standard | male              | polish        |
| **Tabata**    |  Standard | female            | portuguese    |
| **Juliana**   |  Standard | female            | portuguese    |
| **Pedro**     |  Standard | male              | portuguese    |
| **Pati**      |  Standard | female            | portuguese    |
| **Adriano**   |  Standard | male              | portuguese    |
| **Alexandra** |  Standard | female            | romanian      |
| **Inessa**    |  Standard | female            | russian       |
| **Viktor**    |  Standard | male              | russian       |
| **Francisca** |  Standard | female            | spanish       |
| **Margarita** |  Standard | female            | spanish       |
| **Mateo**     |  Standard | male              | spanish       |
| **Leticia**   |  Standard | female            | spanish       |
| **Josefina**  |  Standard | female            | spanish       |
| **Rosa**      |  Standard | female            | spanish       |
| **Miguel**    |  Standard | male              | spanish       |
| **Eva**       |  Standard | female            | swedish       |
| **Mesut**     |  Standard | female            | turkish       |
| **Angharad**  |  Standard | female            | welsh         |
