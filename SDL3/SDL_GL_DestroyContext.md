###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_GL_DestroyContext

Delete an OpenGL context.

## Header File

Defined in [<SDL3/SDL_video.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_video.h)

## Syntax

```c
bool SDL_GL_DestroyContext(SDL_GLContext context);
```

## Function Parameters

|                                |             |                                   |
| ------------------------------ | ----------- | --------------------------------- |
| [SDL_GLContext](SDL_GLContext) | **context** | the OpenGL context to be deleted. |

## Return Value

(bool) Returns true on success or false on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Version

This function is available since SDL 3.0.0.

## See Also

- [SDL_GL_CreateContext](SDL_GL_CreateContext)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryVideo](CategoryVideo)

