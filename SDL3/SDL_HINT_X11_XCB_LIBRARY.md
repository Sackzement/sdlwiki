###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_HINT_X11_XCB_LIBRARY

Specify the XCB library to load for the X11 driver.

## Header File

Defined in [<SDL3/SDL_hints.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_hints.h)

## Syntax

```c
#define SDL_HINT_X11_XCB_LIBRARY "SDL_X11_XCB_LIBRARY"
```

## Remarks

The default is platform-specific, often "libX11-xcb.so.1".

This hint should be set before initializing the video subsystem.

## Version

This hint is available since SDL 3.0.0.

----
[CategoryAPI](CategoryAPI), [CategoryAPIMacro](CategoryAPIMacro), [CategoryHints](CategoryHints)

