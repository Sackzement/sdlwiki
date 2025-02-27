###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_GetRenderLogicalPresentation

Get device independent resolution and presentation mode for rendering.

## Header File

Defined in [<SDL3/SDL_render.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_render.h)

## Syntax

```c
bool SDL_GetRenderLogicalPresentation(SDL_Renderer *renderer, int *w, int *h, SDL_RendererLogicalPresentation *mode);
```

## Function Parameters

|                                                                      |              |                                      |
| -------------------------------------------------------------------- | ------------ | ------------------------------------ |
| [SDL_Renderer](SDL_Renderer) *                                       | **renderer** | the rendering context.               |
| int *                                                                | **w**        | an int to be filled with the width.  |
| int *                                                                | **h**        | an int to be filled with the height. |
| [SDL_RendererLogicalPresentation](SDL_RendererLogicalPresentation) * | **mode**     | the presentation mode used.          |

## Return Value

(bool) Returns true on success or false on failure; call
[SDL_GetError](SDL_GetError)() for more information.

## Remarks

This function gets the width and height of the logical rendering output, or
the output size in pixels if a logical resolution is not enabled.

## Thread Safety

You may only call this function from the main thread.

## Version

This function is available since SDL 3.0.0.

## See Also

- [SDL_SetRenderLogicalPresentation](SDL_SetRenderLogicalPresentation)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryRender](CategoryRender)

