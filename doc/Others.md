# Others

**[← Table of contents](/README.md)**

### On this page

[Plugin project settings](#plugin-project-settings)<br/>
[Package a project](#package-a-project)<br/>
    *[No runtime generated sentences](#no-runtime-generated-sentences)*<br/>
    *[Blueprint only pojects](#blueprint-only-pojects)*<br/>

## Plugin project settings

Some parameters, such as the API Endpoint URL and the API key used to authenticate the request, are stored in the project settings. You cand find and edit those values under **Edit** > **Project settings...** > **Plugins** > **Ariel**: 

![Ariel project settings](/res/ariel_project_settings.png)

### Settings

| Name              | Default value     | Description |
| ----------------- | ----------------- | ----------- |
| API Endpoint      | https://ariel-api.xandimmersion.com/ | The URL of Ariel API. <br/>*→ If you are a Business customer and use dedicaced servers, paste here your API Endpoint.* |
| API Key           | XXXXXXXXXXXXXXXXX | The API Key used with Ariel for authentication. Some API key have access to more voices than the one listed. The speakers list is automatically changed every time the API key is changed (you must have an internet access to retrieve the API key speakers list).<br/> *→ If you are a Business customer, paste here your API Key.* |
| Speakers (R/O)    | *empty array*     | The list of allowed [FArielSpeaker](/doc/API.md#ariel-speaker-farielspeaker) for this API Key. The list is automatically updated from the API server each time the API key is modified (you must have an internet access to update the speakers list). |

You can retrieve these informations at runtime by using the node `Get Class Defaults` and then choose the class `ArielPluginSettings` :

![Get class defaults node](/res/get_class_defaults.png)

## Package a project

The Ariel plugin works on packaged projects for Windows, Mac and Linux. Other operating systems may works as well, but we do not oficially support them.

### No runtime generated sentences

If your project does **not** use runtime generated sentences, meaning all speech are pre-generated and the nodes *[Ariel Text-To-Speech](/doc/API.md#ariel-text-to-speech)* and *[Audio wav bytes to SoundWave](/doc/API.md#audio-wav-bytes-to-soundwave)* are never used outside of the editor, then you can disable the Ariel plugin before packaging the project.

Go to **Edit** > **Plugins** > search **Ariel** > <ins>uncheck</ins> the checkbox (you need to restart the engine):

![enable plugin](/res/enable_plugin.png)

> [!CAUTION]
> If you try to package a project that use Ariel nodes at runtime, the build package will fail.

### Blueprint only pojects

If you have a Blueprint project with **no** C++ classes, the packaged game will crash at startup with the following error message:

![modue missing bug](/res/ariel_module_not_found.png)

This is a known bug since UE4.24. A temporary workaround is add a 'dummy' C++ class to your project. You must have the Unreal C++ Build tools installed, for more informations see [prerequisites](/doc/Setup.md#prerequisites) section.

0. Go to **Tools** > **New C++ Class...**<br/>
![create new cpp class](/res/new_cpp_class.png)

1. Choose a class type, name and location (you can use default parameters), then hit 'Create Class':<br/>
![create cpp class](/res/create_class.png)

2. If the message *Project now includes sources, please close the editor and build from your IDE.* appears, close and restart the project. If not, ensure that the C++ Build tools are correctly installed (see [prerequisites](/doc/Setup.md#prerequisites)).<br/>
![cpp message](/res/cpp_message.png)

3. If a message appears asking you if you want to open the file with your IDE, choose ***No*** unless you want to add additionnal C++ code. Then, restart your project. The following message should appear (the name of the modules can be different):<br/>
![compile module message](/res/uncompiled_module_message.png)

4. Choose "**Yes**" and wait for the Editor to open. 

> [!NOTE]
> The editor can take up to 5 minutes to compile the missing plugins and starts. While compiling, no window are displayed and it seems like the project didn't open. **Do not panik** and **do not try to re-open the project**, just wait for eighter Unreal Editor to open.

<br/>

> [!WARNING]
> If an error message occurs, ensure that the C++ Build tools are correctly installed (see [prerequisites](/doc/Setup.md#prerequisites)) and that the code can compile (if you didn't change the C++ file yourself it should be compilable by default).

