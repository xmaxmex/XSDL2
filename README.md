# XSDL2
XSDL2 - Is a Win32 DLL Wrapper for SDL2 with exports in stdcall.

# Requires
The DLL name is XSDL2.dll, and depends on SDL2.dll and the others DLL for the dependencies, like SDL2_image.dll and zlib1.dll.
The SDL2.dll, is statically linked.

# DLL Exports
Use the tool dumpbin.exe form Visual Studio to see the exports, example:

c:\tools\dumpbin.exe /exports c:\download\XSDL2.dll

# Visual Basic 6
## cSDL2
Is a VB6 Class with Modules for this DLL usage, with Samples and some functions.

# About the Wrapper
The wrapper provides bindings for the following libraries:
- SDL2 (2.0.12)
- SDL2_image (2.0.5)

*All Functions have a "x" on its begin, example: SDL_Init, became xSDL_Init and SDL_BlitSurface is xSDL_BlitSurface.*

# Note
Please, Note that XSDL2 will not provide every single SDL2 function. This is due to limitations in the VB6 language that would cause major conflicts with the native SDL2 library and its extensions.

## Function Status 
# Basics
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
|   | SDL_Quit  | y  |
|   | SDL_WasInit  | n  |
| SDL_hints.h  | SDL_GetHint  | n  |
| SDL_error.h  | SDL_GetError  | y  |
|   | SDL_ClearError  | y  |
| SDL_log.h  |   |   |
| SDL_assert.h  |   |   |
| SDL_version.h  | SDL_GetVersion   | y  |
|   | SDL_GetRevision  | y  |
# Video
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL_video.h  | SDL_CreateWindow  | y  |
|   | SDL_CreateWindowAndRenderer  | y  |
|   | SDL_DestroyWindow  | y  |
|   | SDL_DisableScreenSaver  | y  |
|   | SDL_EnableScreenSaver  | y  |
|   | SDL_EnableScreenSaver  | y  |
# Input Events
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Force Feedback
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Audio
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Threads
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Timers
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# File Abstraction
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Shared Object Support
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Platform and CPU Information
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# Power Management
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL_power.h  | SDL_GetPowerInfo  | n  |
# Additional Functionality
| Header  | Function  | Wrapper  |
| ------------ | ------------ | ------------ |
| SDL.h  | SDL_Init  | y  |
# VB6 New Functions
| DLL  | Function  | Info |
| ------------ | ------------ | ------------ |
| XSDL2.dll  | SDL_InitALL  | SDL_Init(SDL_INIT_EVERYTHING) |


# SDL2 VB6 HelloWorld
```vb6
Public SDL2 As New cSDL2

Sub main()

    Dim window As Long
    Dim surface As Long
    Dim screen As Long
    
    Debug.Print "Platform: " & SDL2.GetPlataform
    Debug.Print "SDL2 Version: " & SDL2.GetVersion
    
    If SDL2.Init2(SDL_INIT_VIDEO) > 0 Then
        MsgBox "Error on SDL_Init: " & SDL2.GetError
    End If

    window = SDL2.CreateWindowx2("SDL2 on VB6 Win32", 640, 480)
    
    SDL2.Delay 2000
    
    surface = SDL2.LoadBMP2(App.Path & "\hello_world.bmp")
    If surface = 0 Then
        Debug.Print "surface Error: " & SDL2.GetError
    End If

    screen = SDL2.GetWindowSurface(window)
    If screen = 0 Then
        Debug.Print "screen Error: " & SDL2.GetError
    End If
    
    SDL2.BlitSurface surface, 0, screen, 0
    
    SDL2.UpdateWindowSurface window
    
    SDL2.Delay 5000
    
    SDL2.SetWindowTitle window, "SDL2 with surface bmp loaded"
    
    SDL2.Delay 2000
    
    SDL2.DestroyWindow window

    SDL2.Quit

End Sub

```

## Author

Claudemir P. da Luz Jr <xmaxmex@gmail.com>


Enjoy!


[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/claudemirdaluz/
