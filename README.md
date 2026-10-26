# Capto

**English** · [Français](README.fr.md)

Capto is a screen-capture tool for Windows 10 and 11: grab a region, a window or a screen from any application, annotate it, then paste, save or find it again later in the history. It also records the screen as a video, with sound, that you can trim or turn into an animated GIF.

- **One keystroke away.** Global shortcuts work from any application; Capto waits in the notification area.
- **Paste right away.** By default, every capture is in the clipboard as soon as it is taken.
- **Nothing is lost.** Every capture and every video is kept in a searchable history, with its annotations.
- **Everything stays on your PC.** No account, no cloud, no telemetry. The only network access is the update check against this repository.

![The Capto main window: the capture buttons, the history and an annotated capture](docs/images/en/main.png)

This repository holds the installers, the update packages and the release notes of Capto. The source code is not public.

## Contents

- [Install](#install)
- [Getting started](#getting-started)
- [Capturing](#capturing)
- [Recording a video](#recording-a-video)
- [The history](#the-history)
- [The annotation editor](#the-annotation-editor)
- [Trimming a video and exporting a GIF](#trimming-a-video-and-exporting-a-gif)
- [Settings](#settings)
- [Keyboard shortcuts](#keyboard-shortcuts)
- [Updates](#updates)
- [Where your data is](#where-your-data-is)
- [Uninstall](#uninstall)
- [Troubleshooting](#troubleshooting)

## Install

1. Download `Capto-win-Setup.exe` from the [latest release](https://github.com/gaetanthouvenin/Capto-releases/releases/latest).
2. Run it. The installer is not signed yet, so Windows SmartScreen warns about an "unknown publisher": click **More info**, then **Run anyway**.
3. Capto installs for the current user only (no administrator rights needed), under `%LocalAppData%\CaptoApp`, adds a Start menu shortcut and starts.

`Capto-win-Portable.zip` is the same application without installation: unzip it anywhere and run `Capto.exe`.

## Getting started

Capto opens its main window: a toolbar with the capture buttons, the history on the left and the selected capture on the right. Its icon also appears in the notification area, next to the clock; right-click it for the capture commands, the settings and **Quit**.

The quickest way to use it:

1. Press **Ctrl+Shift+C** from any application.
2. Drag over the part of the screen you want.
3. Paste (**Ctrl+V**) in your chat, email or document.

Closing the main window keeps Capto running in the notification area (this can be changed in the settings), so the shortcuts stay available. Turn on **Start with Windows** in the settings to have Capto ready after every sign-in.

## Capturing

| Capture | Shortcut | What it does |
|---|---|---|
| Region | Ctrl+Shift+C | Drag a rectangle over the screen. |
| Window | Ctrl+Shift+W | Hover a window and click it. |
| Screen | Ctrl+Shift+F | Captures the screen under the mouse pointer. |
| All screens | Ctrl+Shift+Alt+F | Captures every monitor in one image. |
| Repeat last region | Ctrl+Shift+Alt+C | Captures the same rectangle as the last region capture, without selecting it again. |
| Delayed region | Ctrl+Shift+D | Waits a few seconds, then opens the region selection. |

The same commands are in the toolbar of the main window (the less common ones under **More captures**) and in the menu of the notification-area icon.

![The More captures menu: repeat last region and the delayed captures](docs/images/en/more.png)

### Selecting a region or a window

When you start a region or window capture, the screen freezes: what you select is exactly what was on screen when you pressed the shortcut, even if a menu or a tooltip closes in the meantime.

- **Region:** drag to draw the rectangle; its size in pixels is shown next to it.
- **Window:** hover a window to highlight it, then click. **Tab** moves to the next window, which helps with windows hidden behind others. The window is captured on its own, even where other windows cover it.
- **W** switches to window selection, **R** back to region selection.
- **Esc** cancels.

The bar at the top of the screen recalls the mode and the keys; the size of the rectangle is shown at its corner.

<img src="docs/images/en/overlay-region.png" width="720" alt="Selecting a region: the rest of the screen is dimmed and the size of the selection is shown">



### Region formats

The region selection can follow a format instead of a free rectangle:

- **Aspect ratios** (16:9, 4:3, 1:1): the rectangle keeps its proportions while you drag.
- **Fixed sizes** (1280 × 720, 1920 × 1080, 800 × 600): a frame of that size follows the mouse; click to place it.

In the region selection, **C** cycles through the formats, **1** to **9** pick one directly and **0** goes back to **Free**. Capto remembers the last format you used. You can add up to 8 formats of your own in **Settings › Region formats**.

<img src="docs/images/en/overlay-ratio.png" width="720" alt="Selecting a region in 16:9: the format is shown next to the size">


### Delayed capture

A delayed capture shows a small countdown in a corner of the screen (3, 5 or 10 seconds, 5 by default; it never appears in the image) before capturing, which leaves time to open a menu or hover an element. **Esc** cancels the countdown. The delayed entries are under **More captures** in the main window and **Delayed capture** in the notification-area menu; the delay is set in **Settings › Capture**.

### After a capture

By default the capture is copied to the clipboard and added to the history. Depending on the settings, Capto can also play a sound, open the editor, show a notification (only while the main window is hidden) and draw the mouse pointer into the image.

## Recording a video

Capto records a region, a window or a whole screen to an MP4 video (H.264), with the sound of the computer and, if you want, your microphone.

1. Press **Ctrl+Shift+Alt+R**, click **Video** in the toolbar of the main window, or choose **Record a video** in the notification-area menu.
2. Select what to record, as for a capture: drag a region, click a window, or press **S** and click a screen. **W** and **R** switch to window and region selection, and the region formats work too.
3. A 3-second countdown starts, then the recording.
4. Press **Ctrl+Shift+Alt+R** again, or click **Stop** in the recording toolbar: the video is added to the history.

While selecting, the chips at the top of the screen show which sounds will be recorded: **A** turns the system sound on or off, **M** the microphone, for this recording only.

During the recording, a small toolbar shows the elapsed time, with **Pause** / **Resume**, **Stop**, a button to discard the recording, and a button to mute each sound source with its level meter. Drag it by its grip to move it. Neither the toolbar nor the frame around the recorded area appears in the video. The same commands are in the notification-area menu.

- A window video follows the window when you move it, but menus and tooltips do not appear in it: record a region to show them.
- The recording stops by itself, and keeps the video, when it reaches the maximum duration (60 minutes by default), when the recorded window closes or when the disk is almost full.
- If Capto or Windows stops during a recording, the video is recovered at the next start.
- Video recording needs Windows 10 version 2004 or later. On an N edition of Windows, install the Media Feature Pack first.

## The history

Every capture and every video is kept in the history of the main window, newest first. Select a video to play it in the detail pane (**Space** plays and pauses); its details show its length, size and recorded sounds.

- **Search** (**Ctrl+F**) by name, window title or date.
- **Copy** (**Ctrl+C**) puts the capture, with its annotations, back in the clipboard. For a video, it copies the file, ready to paste into a folder or a chat.
- **Save** (**Ctrl+S**) writes it to the default export folder, **Save as** (**Ctrl+Shift+S**) asks where; PNG or JPEG for a capture, MP4 for a video.
- **Drag** a capture from the history into another application (an email, a chat, a folder) to drop the image there.
- **Annotate** (**Enter**) opens the editor.
- **Rename** (**F2**) gives the capture a name that the search finds.
- **Open file** and **Show in folder** give access to the image file.
- **Delete** (**Del**) moves the capture to the Windows Recycle Bin, from which it can be restored. Several captures can be selected and deleted at once.

The history can clean itself up: in **Settings › Storage**, set how many days to keep the captures and how many captures to keep at most (0 means no limit). Older captures go to the Recycle Bin. Videos have their own limit, a total size set in **Settings › Recording** (20 GB by default).

## The annotation editor

Open it with **Annotate** (or **Enter**) on a capture, or automatically after every capture if you turn on **Open the editor after the capture**.

![The annotation editor: the tools on the left, the properties of the arrow tool at the top, a capture with a highlight, a frame, an arrow, a text and two numbered badges](docs/images/en/editor.png)

| Tool | Key | Use |
|---|---|---|
| Select | V | Select, move, resize, duplicate (Ctrl+D) or delete (Del) an annotation. |
| Arrow | A | Point at something. |
| Rectangle | R | Frame an area, with or without fill. |
| Text | T | Write a note, optionally in a framed box that stays readable over a busy image. |
| Number | N | Place numbered badges (1, 2, 3…) for step-by-step instructions; deleting one renumbers the others. |
| Highlighter | H | Highlight text like a marker pen. |
| Blur | B | Hide passwords, names or emails, by pixelating or blurring an area. |
| Crop | C | Keep only part of the image. |
| Cut out | X | Remove a horizontal or vertical band and join the two edges (straight, zigzag or torn edge), for example to shorten a long page. |

- Colour, thickness and size are in the properties bar of the selected tool. Hold **Shift** while drawing to constrain the shape (straight arrows, squares).
- **Ctrl+Z** / **Ctrl+Y** undo and redo, **Ctrl+S** saves the annotations, **Ctrl+C** copies the annotated image, **Ctrl+Enter** saves, copies and closes the editor.
- Zoom with **Ctrl+-** / **Ctrl++**, **Ctrl+0** fits the image to the window, **Ctrl+1** shows it at actual size.
- Annotations stay editable: the original image is never modified, and crop and cut-out can be reset at any time. Copies, saved files and drags always contain the annotated image, and the blur is applied for good in them.

## Trimming a video and exporting a GIF

Select a video in the history, then click **Trim** to keep only part of it. A strip of frames shows the video, with a handle for the start and one for the end of the clip.

<img src="docs/images/en/trim.png" width="720" alt="Trim mode: the video, the strip of frames with the chosen clip framed in orange, the start, end and length of the clip">

- Drag the handles, or move frame by frame with **←** / **→** (**Shift** jumps one second) and set the start and the end at the current frame with **I** / **O**. **Home** / **End** go to the start and the end.
- **Space** plays the clip. While paused, the picture is exactly the frame that will be cut.
- **Trim** (**Enter**) creates the clip as a new item of the history, cut to the exact frame, with its sound. The original stays as it is, unless you tick **Move the original to the Recycle Bin**.
- **Export as MP4…** asks where to save the clip as a file, without adding it to the history. **Esc** leaves without trimming.

**Export as GIF**, on a video or from the trim mode for the chosen clip, makes an animated GIF: 10, 15 or 20 frames per second (15 by default), a width of 640, 800 (default) or 1280 pixels or the original size, a palette per frame or global, looping and dithering. The estimated size updates as you change the options. **Also copy the file** puts the GIF in the clipboard, to paste into Teams, Slack or Outlook. **Export** writes it to the default export folder, **Save as…** asks where. A GIF lasts at most 60 seconds: for a longer video, Capto opens the trim mode on its first minute so you can choose the clip.

<img src="docs/images/en/gif-export.png" width="460" alt="The Export as GIF dialog: frames per second, width, palette, loop, dithering, copy the file and the estimated size">

## Settings

Open them with **Ctrl+,** in the main window or from the notification-area menu. Changes apply when you click **Save**.

### General

Start with Windows, start minimized, close to the notification area, notification after a capture, update check, theme (system, light or dark) and language. Capto follows the Windows language by default and is available in English, French, German, Spanish, Italian, Portuguese, Dutch, Chinese, Japanese and Korean; a language change applies at the next start.

<img src="docs/images/en/settings-general.png" width="620" alt="General settings">

### Capture

Copy to the clipboard, also copy the file (useful for Outlook attachments), open the editor after the capture, play a sound, include the mouse pointer, delay of delayed captures, and the capture engine: Capto uses Windows Graphics Capture, which also captures covered windows; **Use the GDI capture engine** switches to the older engine, to try if captures come out black or incomplete. **About Capto** shows the engine in use.

<img src="docs/images/en/settings-capture.png" width="620" alt="Capture settings">

### Region formats

The built-in formats, with the number key that picks each one during a selection, and up to 8 aspect ratios or fixed sizes of your own.

<img src="docs/images/en/settings-formats.png" width="620" alt="Region format settings">

### Recording

Frames per second (15, 30 or 60; 30 by default), quality (low, standard or high), include the cursor, highlight mouse clicks with a yellow ring, 3-second countdown, maximum duration (60 minutes by default), maximum total size of the videos (20 GB by default; beyond it, the oldest go to the Recycle Bin) and the videos folder. The page also says whether a hardware (GPU) encoder is available; without one, the software encoder may miss frames at high resolutions.

**Sound:** the system sound (what the computer plays) is recorded by default, the microphone is off by default and only opened during a recording. Choose the output and input devices (the Windows default unless you pick one) and the gain of each source. With speakers, the microphone also picks up the system sound: use a headset.

<img src="docs/images/en/settings-recording.png" width="620" alt="Recording settings">

### Storage

History folder, retention, default export folder, file-name pattern, format (PNG or JPEG) and JPEG quality. The file-name pattern accepts `{date}`, `{time}`, `{kind}`, `{width}`, `{height}` and `{index}`; the default is `Capto_{date}_{time}`.

<img src="docs/images/en/settings-storage.png" width="620" alt="Storage settings">

### Shortcuts

Click a shortcut, then press the new key combination; **Backspace** clears the optional ones (delayed region, repeat last region, pause a recording).

<img src="docs/images/en/settings-hotkeys.png" width="620" alt="Shortcut settings">

## Keyboard shortcuts

**From any application** (can be changed in the settings; **Suspend shortcuts** in the notification-area menu turns them off temporarily, for example when another application needs the same keys):

| Shortcut | Action |
|---|---|
| Ctrl+Shift+C | Capture a region |
| Ctrl+Shift+W | Capture a window |
| Ctrl+Shift+F | Capture the screen under the pointer |
| Ctrl+Shift+Alt+F | Capture all screens |
| Ctrl+Shift+Alt+C | Repeat last region |
| Ctrl+Shift+D | Delayed region capture |
| Ctrl+Shift+Alt+R | Start or stop a recording |
| (none by default) | Pause or resume a recording |

**During a selection:** Esc cancels, W / R switch between window and region, Tab moves to the next window, C changes the region format, 0 to 9 pick a format. For a video, also S for a whole screen, A for the system sound and M for the microphone.

**In the main window:** Ctrl+F search, Ctrl+C copy, Ctrl+S save, Ctrl+Shift+S save as, Enter annotate, F2 rename, Del delete, Ctrl+, settings. On a video, Space plays and pauses.

**In the editor:** V A R T N H B C X tools, Ctrl+Z undo, Ctrl+Y redo, Ctrl+S save, Ctrl+C copy, Ctrl+Enter copy and close, Ctrl+D duplicate, Del delete, Ctrl+0 fit, Ctrl+1 actual size.

**When trimming a video:** ← / → one frame (Shift: one second), I / O set the start / end, Home / End go to the start / end, Space plays the clip, Enter trims, Esc leaves.

## Updates

The installed version checks this repository at startup, then once a day (this can be turned off in **Settings › General**). When a new version is available, **Update to x.y.z** appears in the menu of the notification-area icon: click it, Capto downloads the update and restarts. Only stable releases are offered, never pre-releases. **About Capto**, in the same menu, shows the installed version.

The changes of each version are listed in its [release notes](https://github.com/gaetanthouvenin/Capto-releases/releases).

## Where your data is

| What | Where |
|---|---|
| Captures and their annotations | `%LocalAppData%\Capto\captures` (can be changed in **Settings › Storage**) |
| Videos | the `recordings` folder inside the captures folder |
| Settings | `%AppData%\Capto\settings.json` |
| Last region and other state of this PC | `%LocalAppData%\Capto\state.json` |
| Saved and exported images | `Pictures\Capto` by default |
| The application itself | `%LocalAppData%\CaptoApp` |

## Uninstall

Uninstall Capto from **Windows Settings › Apps › Installed apps**. Your captures and settings are kept, so a reinstall finds them again; delete the `%LocalAppData%\Capto` and `%AppData%\Capto` folders to remove them as well.

## Troubleshooting

- **A shortcut does nothing:** another application already uses it, and Capto says so in its status bar at startup. Choose another combination in **Settings › Shortcuts**.
- **The capture is not in the clipboard:** check **Copy to the clipboard** in **Settings › Capture**; the capture is in the history anyway.
- **Word inserts a link instead of the image:** turn off **Also copy the file** in **Settings › Capture**.
- **A capture is black or incomplete:** turn on **Use the GDI capture engine** in **Settings › Capture**.
- **No H.264 video encoder is available:** on an N edition of Windows, install the Media Feature Pack from **Windows Settings › Apps › Optional features**.
- **Windows blocks the microphone:** allow desktop apps to use the microphone in **Windows Settings › Privacy & security › Microphone**; Capto offers to open that page, or to record without the microphone.
- **The microphone sounds like a phone call:** a Bluetooth headset switches to phone quality while its microphone is in use; use a wired microphone or record without it.

---

Releases are published automatically by the release workflow of the source repository. This README, its translation and their images are the only files maintained by hand.
