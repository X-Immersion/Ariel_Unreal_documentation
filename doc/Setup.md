# Setup

**[← Table of contents](/README.md#table-of-contents)**

### On this page

[Prerequisites](#prerequisites)<br/>
[Installation](#installation)<br/>

## Prerequisites

There are two different versions of the plugin:
* Compiled plugin (for Unreal Engine 5.2 - 5.4)
* Uncompiled plugin (for Unreal Engine 5.0+) *

* You must have installed the **C++ Build tools for Unreal Engine** in order to run uncompiled version of the plugin, or if the Unreal Engine version is not the same as the plugin Engine version. Please read [this article](https://dev.epicgames.com/documentation/unreal-engine/setting-up-visual-studio-development-environment-for-cplusplus-projects-in-unreal-engine) for more information on how to install Visual Studio C++ build tools. <ins>**Do not forget to select your Engine version on the left side first!**</ins>

![select unreal version](/res/select_unreal_version.png)

*To ensure that you have all build tools installed, try to create a new C++ Unreal Project and make sure that the Editor starts correctly. Once the editor is open, click on the compile button in the bottom right corner and ensure that the compilation succeeded:*

![verify c++](/res/verify_cpp.png)

## Installation

### From a ZIP archive (source code)

0. If not already done, create a new project with the Engine version of your choice and navigate to the project's root directory.
> [!CAUTION]
> Close the Unreal Project where you want Ariel to be installed first!

1. Extract the content from the ZIP archive to the root directory of your Unreal project:<br/>
![extract ZIP file content](/res/extract_zip_content.png)

2. Reopen your project.

3. Depending on the Engine plugin version and if the engine in the ZIP archive was compiled or not, you might need to compile the plugin. If the following message appears when you try to reopen you project after extracting the zip, the plugin must be compiled:<br/>
![missing modules message](/res/uncompiled_plugin_message.png)<br/>
> [!NOTE]
> You **must** have the C++ build tools for Unreal Engine to be able to compile the plugin. Please read [prerequisites](./Setup.md#prerequisites) for more details.

4. Navigate to **Edit** > **Plugins** > Search **"Ariel"** and enable the Ariel plugin (you may need to restart the Engine):
![enable plugin](/res/enable_plugin.png)

5. Navigate to **Edit** > **Project Settings** > Search **"Ariel"**. Fill the **API Key** and **API Endpoint** fields with the values provided to you. If you are a Business customer, you might have a dedicated API Endpoint and API Key. Please contact us if you have any question.
![project settings](/res/project_settings.png)