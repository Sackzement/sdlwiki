###### (This is the documentation for SDL3, which is under heavy development and the API is changing! [SDL2](https://wiki.libsdl.org/SDL2/) is the current stable version!)
# SDL_WaitSemaphoreTimeout

Wait until a semaphore has a positive value and then decrements it.

## Header File

Defined in [<SDL3/SDL_mutex.h>](https://github.com/libsdl-org/SDL/blob/main/include/SDL3/SDL_mutex.h)

## Syntax

```c
bool SDL_WaitSemaphoreTimeout(SDL_Semaphore *sem, Sint32 timeoutMS);
```

## Function Parameters

|                                  |               |                                                                         |
| -------------------------------- | ------------- | ----------------------------------------------------------------------- |
| [SDL_Semaphore](SDL_Semaphore) * | **sem**       | the semaphore to wait on.                                               |
| Sint32                           | **timeoutMS** | the length of the timeout, in milliseconds, or -1 to wait indefinitely. |

## Return Value

(bool) Returns true if the wait succeeds or false if the wait times out.

## Remarks

This function suspends the calling thread until either the semaphore
pointed to by `sem` has a positive value or the specified time has elapsed.
If the call is successful it will atomically decrement the semaphore value.

## Version

This function is available since SDL 3.0.0.

## Code Examples

```c
// BEWARE: This code example was migrated from the SDL2 Wiki, by only updating the names.

void add_data_to_queue(void);
void get_data_from_queue(void);
int data_available(void);
void wait_for_threads(void);

SDL_AtomicInt done;
SDL_Semaphore *sem;
SDL_SetAtomicInt(&done, 0);
sem = SDL_CreateSemaphore(0);

Thread_A:
    while (!SDL_GetAtomicInt(&done)) {
        add_data_to_queue();
        SDL_SignalSemaphore(sem);
    }
Thread_B:
    const Uint32 timeout = 1000; /* wake up every second */
    while (!SDL_GetAtomicInt(&done)) {
        if (SDL_WaitSemaphoreTimeout(sem, timeout) == 0 && data_available()) {
            get_data_from_queue();
        }
        /* ... do other processing */
    }

SDL_SetAtomicInt(&done, 1);
SDL_SignalSemaphore(sem);
wait_for_threads();
SDL_DestroySemaphore(sem);

```

## See Also

- [SDL_SignalSemaphore](SDL_SignalSemaphore)
- [SDL_TryWaitSemaphore](SDL_TryWaitSemaphore)
- [SDL_WaitSemaphore](SDL_WaitSemaphore)

----
[CategoryAPI](CategoryAPI), [CategoryAPIFunction](CategoryAPIFunction), [CategoryMutex](CategoryMutex)

