# Try Embedded Improvements

## Vision

Try Embedded should become the interview-first embedded systems platform:

> Wokwi-level simulation + structured learning + realistic debugging + interview assessment.

The learner journey should be:

**Learn -> Build -> Break -> Debug -> Explain -> Interview**

This document describes the improvements needed beyond the current SiliconLab
single-page Arduino simulator.

## Current baseline

The current prototype already provides:

- Arduino-style code editor, parser, compiler, and runtime
- Arduino Uno, Nano, and Mega targets
- Compile, run, pause, step, reset, and speed controls
- Interactive wiring canvas with pan, zoom, rotate, undo, and redo
- LED, button, potentiometer, servo, buzzer, TMP36, and seven-segment parts
- Digital I/O, analog input, PWM, timing, interrupts, tone, Servo, Serial, Wire,
  and SPI APIs
- Serial monitor, compiler diagnostics, pin states, and event timeline
- Starter projects, autosave, import/export, snapshots, and share links

This is a good Arduino learning foundation. It is not yet a complete simulator,
professional embedded workflow, or interview-preparation product.

## Benchmark products

### Wokwi: simulator benchmark

Use Wokwi as the primary simulator benchmark. Important capabilities to match
or selectively exceed include:

- Arduino, ESP32, STM32, AVR, Raspberry Pi Pico, ARM, RISC-V, and Xtensa targets
- Large component library covering sensors, displays, motors, storage, and input
- Wi-Fi, HTTP, MQTT, NTP, SD-card, and filesystem simulation
- Logic analyzer, protocol inspection, waveform capture, and VCD export
- GDB debugging
- MicroPython and multiple embedded toolchains
- VS Code integration
- CLI, GitHub Actions, and automated simulation tests
- Shareable projects, examples, and community workflows
- Custom chip/component API

### Proteus: professional circuit benchmark

Learn from Proteus for:

- Schematic-quality circuit modeling
- MCU and peripheral simulation
- Electrical probes and measurement tools
- Fault finding and fault injection
- PCB and embedded-system workflow integration
- Professional debugging and education tooling

### Renode: firmware and CI benchmark

Learn from Renode for:

- Deterministic virtual time
- Multi-node and networked systems
- ARM and RISC-V firmware execution
- Trace collection and analysis
- Automated tests in CI
- Reproducible local and cloud environments

### Tinkercad Circuits: beginner benchmark

Learn from Tinkercad for:

- Fast zero-install onboarding
- Simple circuit creation
- Guided tutorials
- Starter projects
- Classroom workflows
- Accessible visual explanations

## Required simulator improvements

### Firmware and architecture

- Replace the limited custom interpreter with real firmware compilation where practical
- Support ELF, HEX, and BIN firmware artifacts
- Add AVR, ARM, and RISC-V execution paths
- Add ESP32, STM32, and Raspberry Pi Pico targets
- Model CPU clock, memory map, flash, RAM, stack, and heap limits
- Model interrupt latency, timer behavior, watchdogs, and reset causes
- Add deterministic simulation seeds and reproducible virtual time
- Support Arduino CLI, PlatformIO, ESP-IDF, Pico SDK, and STM32 toolchains
- Add MicroPython; evaluate Zephyr and Rust after the core workflow is stable

### Peripherals and protocols

- Implement real I2C bus behavior and addressable I2C devices
- Implement real SPI transactions and chip-select behavior
- Add UART timing, framing errors, baud mismatch, and dropped bytes
- Add CAN and CAN-FD scenarios
- Add USB and HID scenarios where the execution model allows it
- Add ADC resolution, reference voltage, sampling, and noise behavior
- Add PWM frequency, duty cycle, timer conflicts, and output capture
- Add DMA, RTC, EEPROM, flash, SD card, and filesystem models
- Add Wi-Fi, HTTP, MQTT, DNS, and NTP simulation

### Components

- DHT22, BMP180, MPU6050, DS1307, HC-SR04, RFID, and load-cell modules
- LCD, OLED, TFT, e-paper, LED matrix, NeoPixel, and MAX7219 displays
- Keypads, joysticks, rotary encoders, touch input, and DIP switches
- DC motors, stepper motors, drivers, relays, and battery models
- Shift registers, logic gates, multiplexers, level shifters, and common ICs
- Breadboards, resistors, power rails, and reusable circuit modules
- Logic analyzer as a first-class component
- Documented custom component/chip API

### Electrical behavior

- Add net-based connectivity instead of only component-to-pin links
- Detect floating inputs, missing ground, invalid power, shorts, and contention
- Model voltage levels, current draw, resistor behavior, and basic analog signals
- Warn about unsafe pin configurations and incompatible voltage domains
- Provide explainable electrical diagnostics for learners

## Required debugging tools

- Source-level breakpoints
- Step over, step into, and step out
- Variable watches and expression evaluation
- Call stack view
- Register view
- Memory and peripheral/register view
- Reset and exception inspection
- Serial terminal with timestamps and filters
- Logic analyzer with triggers and named channels
- Waveform viewer with cursors and measurements
- UART, I2C, SPI, CAN, and PWM decoding
- VCD export and import
- Runtime assertions and programmable test probes
- Fault injection for stuck pins, noise, timeouts, dropped bytes, and bad sensors

## Required interview platform

### Learning paths

- Embedded C fundamentals
- Modern C++ for embedded development
- Binary, hexadecimal, bitwise operations, and data representation
- Pointers, arrays, memory layout, alignment, and undefined behavior
- GPIO, timers, PWM, ADC, interrupts, and watchdogs
- UART, SPI, I2C, CAN, USB, and debugging
- RTOS tasks, queues, semaphores, mutexes, priorities, and timing
- Power, performance, reliability, safety, and hardware bring-up
- Hardware/software boundary and production tradeoffs

Every lesson should include a short explanation, visual model, runnable lab,
knowledge check, common mistakes, and an interview question.

### Practical labs

- Lesson-linked simulator project
- Expected behavior and observable symptoms
- Deliberately broken code and circuits
- Hints that become progressively more specific
- Automatic checks for code, wiring, timing, serial output, and pin state
- Resettable experiments
- Learner explanation field: “What happened and why?”
- Solution reveal only after an attempt or explicit request

### Interview practice

- Topic and difficulty filters
- Multiple-choice and short-answer questions
- Code-writing and code-review exercises
- Register and memory-layout questions
- Protocol decoding tasks
- Timing and concurrency problems
- Embedded system-design questions
- Debugging scenarios with logs, waveforms, and faulty firmware
- Timed sessions and full mock interviews
- Written or recorded explanation of the solution
- Rubrics for correctness, tradeoffs, clarity, safety, and testability
- Spaced repetition for weak concepts

### Assessment

- Hidden tests for coding challenges
- Runtime assertions and hardware-state validation
- Static checks for common embedded defects
- Timing, memory, pin-conflict, and protocol checks
- Useful failure messages instead of only pass/fail
- Topic-level readiness score
- Personalized next-step recommendations
- Progress history and interview report export

## Development workflow improvements

- Downloadable project files
- GitHub import and export
- PlatformIO and Arduino CLI compatibility
- STM32CubeIDE and GCC project import
- ELF, HEX, BIN, and map-file support
- VS Code extension or first-class VS Code workflow
- Local CLI for simulation and tests
- GitHub Actions, GitLab CI, and other CI integrations
- Automated tests for serial output, pin state, timing, and logic traces
- Public/private projects, version history, snapshots, forks, and share links
- Documented project format for diagrams, firmware, tests, and metadata

## Education and community

- Guided beginner, intermediate, and advanced tracks
- Prerequisites and estimated lesson time
- Searchable example library
- Public and private project gallery
- Comments, project reviews, and discussion
- Classroom spaces and instructor dashboards
- Assignments, due dates, grading, and feedback
- Company-specific interview tracks
- Leaderboards only where they support learning rather than vanity metrics

## Recommended product architecture

The current single HTML file is appropriate for a prototype. It should evolve
into separated modules:

- `web/`: editor, circuit canvas, lesson UI, interview UI, and dashboards
- `simulator/`: execution engine, board models, peripheral models, and timing
- `components/`: versioned hardware component definitions
- `challenges/`: lessons, tests, hints, rubrics, and expected outcomes
- `backend/`: accounts, projects, progress, sharing, and submissions
- `worker/`: sandboxed compilation, simulation, and automated grading
- `cli/`: local simulation and CI commands
- `docs/`: public project format, component API, and authoring guides

Security requirements for any server-side execution:

- Sandbox untrusted firmware and user code
- Enforce CPU, memory, time, file, and network limits
- Isolate projects and submissions
- Never expose host credentials to simulations
- Make execution reproducible and auditable

## Delivery roadmap

### Phase 1: interview-ready MVP

1. Add Learn, Practice, and Interview navigation.
2. Create one complete path: GPIO -> timers -> interrupts -> UART.
3. Add challenge definitions, hidden tests, hints, scoring, and progress.
4. Add deliberate broken-circuit and broken-firmware exercises.
5. Add basic fault diagnostics and pin-conflict validation.
6. Add 100 high-quality embedded interview questions.
7. Add learner explanations and review reports.

### Phase 2: serious simulator

1. Add real firmware compilation and artifact loading.
2. Add ESP32 and STM32 support.
3. Implement real I2C and SPI peripherals.
4. Add a logic analyzer and waveform viewer.
5. Add breakpoints, watches, registers, and memory inspection.
6. Add fault injection and deterministic replay.
7. Add GitHub import/export, CLI, and CI execution.

### Phase 3: platform breadth

1. Add Pico, MicroPython, CAN, Wi-Fi, SD card, and filesystem workflows.
2. Add Zephyr and Rust support where demand is validated.
3. Add custom components and chip authoring.
4. Add VS Code integration.
5. Add classroom and instructor tooling.
6. Add community projects and reusable challenge packs.

## Success criteria

- A new learner reaches a first successful simulation in under five minutes.
- A learner can diagnose a deliberately broken project without a solution reveal.
- Every major lesson has a runnable lab and an interview assessment.
- Simulation results are reproducible locally and in CI.
- Learners improve on weak topics through spaced practice.
- Users can explain their design decisions, not only make the test pass.
- The platform supports a complete GPIO-to-RTOS interview preparation journey.

## Non-goals

- Supporting every microcontroller on the first release
- Replacing physical hardware for electrical certification or safety testing
- Becoming a full PCB CAD suite before the learning product is validated
- Adding components without a learning, debugging, or interview use case

## Reference products

- Wokwi: https://wokwi.com/
- Wokwi documentation: https://docs.wokwi.com/
- Proteus: https://www.labcenter.com/
- Renode: https://renode.io/
- Tinkercad Circuits: https://www.tinkercad.com/circuits
