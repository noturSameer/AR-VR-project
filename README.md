# AR Interior Design System

A smartphone augmented-reality (AR) application that lets users place and interact with virtual furniture in a real room.

## Team members and roles

| Member | Student ID | Role |
|---|---|---|
| Abror Jo'raboyev | 230363 | AR / Unity development: AR session, camera, plane (surface) detection, Unity project setup |
| Mirjalol Abdujalilov | 220564 | 3D models and UI: furniture models and prefabs, furniture selection panel, control buttons |
| Samandar Mirxosilov | 230146 | Interaction, testing and documentation: place / move / rotate / resize / delete, Android testing, report and README |

## Problem and use case

**Problem.** When people furnish or redesign a room they have to guess: will this sofa fit, does the color match, is there enough space to walk around it? Measuring and imagining the result is slow and error-prone, and a wrong purchase is expensive.

**Use case.** The user points the phone at the floor, chooses a piece of furniture from a catalog, and sees it in real size, in their own room, in real time. They can then move, rotate, resize or delete it until it fits.

**Who benefits.** Home owners and renters planning a room, and furniture shops that want customers to preview products before buying.

## Technology

- **Unity** - 3D engine and Android build pipeline
- **C#** - application scripts
- **AR Foundation** - Unity's cross-platform AR framework (plane detection, raycasting)
- **ARCore** (Google ARCore XR Plugin) - motion tracking and environment understanding on Android

Data flow: phone camera -> ARCore (tracking, surfaces) -> AR Foundation -> Unity scene and C# scripts -> furniture prefabs and UI.

## How to build and run

### Requirements

- Unity Hub and a Unity Editor version with **Android Build Support** (OpenJDK, Android SDK & NDK) installed. Use the version recorded in `ProjectSettings/ProjectVersion.txt`.
- Unity packages (Package Manager): **AR Foundation** and **Google ARCore XR Plugin** (normally already listed in `Packages/manifest.json`).
- An **ARCore-supported Android phone** (Android 7.0 / API 24 or higher) with Developer options and **USB debugging** enabled, and **Google Play Services for AR** installed (the Play Store installs it on first launch if missing).
- A USB cable.

> AR does not work in the Unity editor's Play mode: it needs a real camera, motion sensors and ARCore, so always test on the phone.

### Using the app

1. Start the app and allow camera access.
2. Move the phone slowly over the floor or a table until surfaces are detected.
3. Choose a piece of furniture from the selection panel at the bottom of the screen.
4. Tap a detected surface to place it.
5. Drag to move it, and use the control buttons to rotate, scale up / down, or delete the selected furniture.

## Current features

- Camera feed and AR session setup
- Real-surface (plane) detection with ARCore
- Furniture selection panel (catalog of 3D models)
- Furniture placement on detected surfaces via raycast
- Move, rotate and resize placed furniture (one selected object at a time)
- Delete furniture
- On-screen control buttons and hints
- Tested on an Android phone

## Known limitations

- Detection needs reasonable lighting and surfaces with visible texture.
- Small furniture catalog.
- Android only (ARCore).

## Possible future work

- Larger catalog, color and material options
- Save and load room layouts
- Realistic lighting and shadows
- iOS support through ARKit
- Room measuring and "does it fit" warnings

## Project structure

```
Assets/
  Scenes/      AR scene(s)
  Scripts/     C# scripts (AR placement, interaction, UI)
  Prefabs/     Furniture prefabs
  Models/      3D furniture models and textures
  UI/          UI sprites and layouts
Packages/      Unity package manifest (AR Foundation, ARCore XR Plugin)
ProjectSettings/
```


## License and credits

Developed as a university course project. Third-party 3D models and assets belong to their respective authors; list sources and licenses here.
