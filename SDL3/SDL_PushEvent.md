###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_PushEvent

Add an event to the event queue.

## Header File

Defined in [<SDL3/SDL_events.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_events.h)

## Syntax

```c
bool SDL_PushEvent(SDL_Event *event);
```

## Function Parameters

|                          |           |                                                      |
| ------------------------ | --------- | ---------------------------------------------------- |
| [SDL_Event](SDL_Event) * | **event** | the [SDL_Event](SDL_Event) to be added to the queue. |

## Return Value

(bool) Returns true on success, false if the event was filtered or on
failure; call [SDL_GetError](SDL_GetError)() for more information. A common
reason for error is the event queue being full.

## Remarks

The event queue can actually be used as a two way communication channel.
Not only can events be read from the queue, but the user can also push
their own events onto it. `event` is a pointer to the event structure you
wish to push onto the queue. The event is copied into the queue, and the
caller may dispose of the memory pointed to after
[SDL_PushEvent](SDL_PushEvent)() returns.

Note: Pushing device input events onto the queue doesn't modify the state
of the device within SDL.

This function is thread-safe, and can be called from other threads safely.

Note: Events pushed onto the queue with [SDL_PushEvent](SDL_PushEvent)()
get passed through the event filter but events added with
[SDL_PeepEvents](SDL_PeepEvents)() do not.

For pushing application-specific events, please use
[SDL_RegisterEvents](SDL_RegisterEvents)() to get an event type that does
not conflict with other code that also wants its own custom event types.

## Version

This function is available since SDL 3.0.0.

## Code Examples

```c
SDL_Event sdlevent;
SDL_zero(sdlevent);
sdlevent.type = SDL_EVENT_KEY_DOWN;
sdlevent.key.key = SDLK_1;

SDL_PushEvent(&sdlevent);
```

## See Also

- [SDL_PeepEvents](SDL_PeepEvents)
- [SDL_PollEvent](SDL_PollEvent)
- [SDL_RegisterEvents](SDL_RegisterEvents)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryEvents](CategoryEvents)

