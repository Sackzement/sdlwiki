###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_HasSSE42

Determine whether the CPU has SSE4.2 features.

## Header File

Defined in [<SDL3/SDL_cpuinfo.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_cpuinfo.h)

## Syntax

```c
bool SDL_HasSSE42(void);
```

## Return Value

(bool) Returns true if the CPU has SSE4.2 features or false if not.

## Remarks

This always returns false on CPUs that aren't using Intel instruction sets.

## Version

This function is available since SDL 3.0.0.

## See Also

- [SDL_HasSSE](SDL_HasSSE)
- [SDL_HasSSE2](SDL_HasSSE2)
- [SDL_HasSSE3](SDL_HasSSE3)
- [SDL_HasSSE41](SDL_HasSSE41)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryCPUInfo](CategoryCPUInfo)

