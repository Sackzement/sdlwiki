###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_FlushIO

Flush any buffered data in the stream.

## Header File

Defined in [<SDL3/SDL_iostream.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_iostream.h)

## Syntax

```c
bool SDL_FlushIO(SDL_IOStream *context);
```

## Function Parameters

|                                |             |                                                  |
| ------------------------------ | ----------- | ------------------------------------------------ |
| [SDL_IOStream](SDL_IOStream) * | **context** | [SDL_IOStream](SDL_IOStream) structure to flush. |

## Return Value

(bool) Returns true on success or false on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Remarks

This function makes sure that any buffered data is written to the stream.
Normally this isn't necessary but if the stream is a pipe or socket it
guarantees that any pending data is sent.

## Version

This function is available since SDL 3.0.0.

## See Also

- [SDL_OpenIO](SDL_OpenIO)
- [SDL_WriteIO](SDL_WriteIO)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryIOStream](CategoryIOStream)

