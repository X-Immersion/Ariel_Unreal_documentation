# Local Executable

**[← Table of contents](/README.md#table-of-contents)**

### On this page

[Unreal Crash](#unreal-crash)<br/>
[Add local voice](#add-local-voice)<br/>
[Local executable lifecycle](#local-executable-lifecycle)<br/>

## Unreal Crash

>![CAUTION]
>The information below is valid for **both** editor mode and packaged projects!

If you encounter an Unreal crash while the local executable was running, please note that the local executable process **WILL NOT BE CLOSED automatically!**. This is because
the local executable is not executed on the same process as Unreal, and the crash does not let Unreal 'inform' the local executable that he needs to close. This is a feature we will work on in the next updates, but for now you must do the following:

0. Close all instances of Unreal Engine
1. Open the task manager. See [here](https://techcommunity.microsoft.com/discussions/windows11/how-to-run-task-manager-on-windows-11-6-ways/2701239) on how to open it.
2. On the search bar, type "*piper_server.exe*"
3. End all matching occurences by clicking *End task*. If there is no result, it means that the local executable is not running and you can safely go back to work.

![Kill local executable](/res/kill_executable.png)

## Add local voice

This feature is not available yet. In order to keep informed, we **strongly** recommand you to follow us on [Hugging Face](https://huggingface.co/X-Immersion) and visit [create.xandimmersion.com](https://create.xandimmersion.com/login). If you really need more local voices, please email us at [contact@xandimmersion.com](mailto:contact@xandimmersion.com).

## Local executable Lifecycle

>[!IMPORTANT]
> By default, the local executable is not running. Calling the node *[START ARIEL LOCAL](/doc/API.md#TODOTODO)* will start the local executable. You only need to call it once. It does persist even when switching levels.

>![NOTE]
> Each time the node *[Ariel Text-To-Speech Local](/doc/API.md#TODOTODO)* is invoked, all given parameters are saved and an entry is added to a local queue.

0. If the local executable, does nothing.
1. Try to dequeue the first local entry. If there is no entry in the queue, does nothing.
2. Check if the model name is the same as the previous request or if this is the first local request. In this case, directly skip to point (9.)
3. Restart the local executable. *\**
4. Wait unitl the local executable have restarted.
5. Prompt the model with the entry parameters.
6. Return the result using an event (Delegate)
7. Loop

*\* Restarting the executable is needed because the voice performances are drastically deteriorated if the model changes when the executable is running*

>![TIP]
> When the local executable is stopped using the node *[STOP ARIEL LOCAL](/doc/API.md#TODOTODO)*, all entries in the queue are removed.
