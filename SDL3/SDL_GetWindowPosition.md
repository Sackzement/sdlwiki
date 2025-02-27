###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_GetWindowPosition

Get the position of a window.

## Header File

Defined in [<SDL3/SDL_video.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_video.h)

## Syntax

```c
bool SDL_GetWindowPosition(SDL_Window *window, int *x, int *y);
```

## Function Parameters

|                            |            |                                                                     |
| -------------------------- | ---------- | ------------------------------------------------------------------- |
| [SDL_Window](SDL_Window) * | **window** | the window to query.                                                |
| int *                      | **x**      | a pointer filled in with the x position of the window, may be NULL. |
| int *                      | **y**      | a pointer filled in with the y position of the window, may be NULL. |

## Return Value

(bool) Returns true on success or false on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Remarks

This is the current position of the window as last reported by the
windowing system.

If you do not need the value for one of the positions a NULL may be passed
in the `x` or `y` parameter.

## Version

This function is available since SDL 3.0.0.

## See Also

- [SDL_SetWindowPosition](SDL_SetWindowPosition)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryVideo](CategoryVideo)

