# Embedded Systems Laboratory — STM32F3Discovery

A hands-on laboratory course covering embedded C programming on ARM Cortex-M4 microcontrollers using the STM32F3 HAL library. Projects span GPIO control, hardware timers, USB communication, and digital sensor interfacing over I2C/SPI.

---

## Projects

### Part A — ARM Microcontroller Fundamentals

**Lab 1 — GPIO & Logic Control**  
Implemented pseudo-random dice simulation and a binary LED display counter with button-driven direction control. Introduced HAL GPIO API, SysTick-based delays, and bitwise register manipulation.

**Lab 2 — Timers, PWM & Interrupts**  
Built an event duration measurement system using hardware timer interrupts (TIM2). Implemented software PWM brightness control via timer capture/compare channels, with EXTI-based button interrupt handling — all running concurrently with the main loop.

**Lab 3 — USB CDC Communication**  
Designed a custom ASCII command protocol for bidirectional PC–microcontroller communication over USB Virtual COM Port. Features include LED state control, PWM intensity adjustment, button press counting, and real-time input monitoring — with frame validation and error signaling.

---

### Part B — Digital Sensor Integration (VR Helmet Positioning System)

**Lab 4 — Accelerometer over I2C**  
Interfaced LSM303 accelerometer via I2C. Computed 3-axis head tilt angles (pitch/roll) using static acceleration data per Analog Devices AN-1057. Results streamed over USB CDC at 500 ms intervals; tilt visualized via PWM-controlled LEDs.

**Lab 5 — Gyroscope over SPI**  
Interfaced L3GD20 gyroscope via SPI1. Integrated angular velocity over time to estimate horizontal rotation angle. Zero-point reset via EXTI interrupt on USER button. Results transmitted over USB CDC; LED brightness reflects real-time angular velocity.

**Lab 6 — Magnetometer & Calibration**  
Interfaced LSM303 magnetometer via I2C to determine absolute heading in the horizontal plane. Implemented hard-iron bias calibration routine triggered by button interrupt — collecting min/max field values over a full rotation. Heading displayed on LEDs; results streamed over USB CDC.

---

## Tech Stack

| Area | Details |
|---|---|
| MCU | STM32F303VCT6 (ARM Cortex-M4, 72 MHz) |
| SDK | STM32 HAL, STM32CubeMX |
| IDE | STM32CubeIDE |
| Interfaces | GPIO, I2C, SPI, USB CDC |
| Sensors | LSM303 (accel + mag), L3GD20 (gyro) |
| Language | Embedded C |