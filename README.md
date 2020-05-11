# XSDL2
XSDL2 - VB6 Wrapper for SDL2

# About VB6 Wrapper
The wrapper provides bindings for the following libraries:
- SDL2 (2.0.12)
- SDL2_image (2.0.5)

# Note
Please, Note that XSDL2 will not provide every single SDL2 function. This is due to limitations in the VB6 language that would cause major conflicts with the native SDL2 library and its extensions.

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
