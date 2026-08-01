## 🧩 Basic FreeRTOS (Native API's)
Implemented and tested core FreeRTOS features on STM32 using **manually written FreeRTOS APIs (without the CMSIS-RTOS abstraction layer)**. Each concept was developed and debugged as a standalone project to build a clear understanding of RTOS workflow and kernel behavior.

---

## ✨ Topics Covered

- Task Management
- Queue
- Binary Semaphore
- Mutex
- Event Groups
- Stream Buffer
- Message Buffer
- Direct-to-Task Notification
- Software Timers
- ISR Synchronization

---
## 🐞 Debugging & Validation

### Task Management

Observed task scheduling, priority-based preemption, and task state transitions while debugging. Monitored individual task stack usage using `uxTaskGetStackHighWaterMark()`.

### Queue

Debugged queue send/receive operations, blocking timeouts, and data transfer between producer and consumer tasks.

### Binary Semaphore

Experienced task synchronization between multiple tasks and ISR-to-task signaling using binary semaphores.

### Mutex

Debugged shared resource protection and observed priority inheritance to prevent priority inversion.

### Event Groups

Tracked event bit setting, clearing, and synchronization of multiple tasks waiting on common events.

### Stream Buffer

Observed continuous byte-stream transfer between tasks and debugged buffer availability during runtime.

### Message Buffer

Debugged variable-length message transfers and validated complete message delivery between tasks.

### Direct-to-Task Notification

Experienced lightweight task signaling as an alternative to semaphores and observed notification handling during task execution.

### Software Timers

Debugged one-shot and auto-reload timer callbacks, timer expiration, and callback execution timing.

### ISR Synchronization

Implemented ISR-safe native APIs and observed immediate task wake-up using `portYIELD_FROM_ISR()`.

### Memory Management

Monitored task stack consumption using `uxTaskGetStackHighWaterMark()` and analyzed runtime heap usage with `xPortGetFreeHeapSize()` and `xPortGetMinimumEverFreeHeapSize()`.


