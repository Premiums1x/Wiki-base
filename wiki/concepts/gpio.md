---
concept: gpio
entity_type: concept
aliases: ["general-purpose-input-output"]
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:41Z
---

## Definition
General Purpose Input/Output (GPIO) is an interface used to configure and control various components in a computer or embedded system. It involves pins that can be programmed by the software to send data out (as output) or receive data from external sources (as input).

## How it works
In embedded systems, GPIO pins are part of the microcontroller units (MCUs) or microprocessors, allowing direct interaction with external devices like sensors, actuators, and other peripherals. The GPIO functionality of a pin can be configured through software into different states, including input, output, or input with pull-up/pull-down resistors. This configuration enables the pin to either drive a signal (e.g., controlling an LED to turn on) or read the state of a signal (e.g., detecting a button press). [[mcu]] is essential to understand how GPIO interacts with hardware circuits.

GPIO pins are often grouped in registers for easy and efficient manipulation in software. When a pin is configured as an output, it can be set to drive a specific logic level (high or low), allowing it to control digital output devices. When used as an input, GPIO pins detect the presence or absence of a logical signal and provide this information to the processor. Because GPIO has a direct interface with the hardware, the interaction time is minimized, making it a crucial component for time-sensitive applications, such as those found in [[rtos]].

GPIO functionality is a subset of the broader electrical engineering concept of digital electronics, where digital signals are processed and manipulated at the hardware level. The principle of using digital logic to implement the GPIO interface makes it a foundation for more complex interfaces and protocols, including irq - Interrupt Request lines, which can trigger software-defined actions during significant events.

## Variants
GPIO implementations vary widely across devices and we can categorize them into a few key variants:
- **Single GPIO Pins**: Each pin functions independently, allowing for simple and straightforward control schemes.
- **Extended GPIO Ports**: Some interfaces include multiple pins that can be assigned different functions, either individually or together.
- **Push-Pull Outputs**: Outputs can push a pin high or leave it floating when low.
- **Open-Drain Outputs**: Outputs can pull a pin low but not provide a high voltage. This requires an external pull-up resistor to achieve a high logic state.

Certain MCUs have special GPIO features that can be used for specific purposes:
- **PWM (Pulse Width Modulation)** on GPIOs to control the brightness of LEDs or the speed of motors.
- **PWM GPIOs** can deliver a wide range of pulse durations, allowing for fine control over the external circuit's behavior.
- **Timer Outputs**: These GPIOs can output a pulse or a repeating signal based on timer settings, enabling precise time-based actions in embedded systems.

## Trade-offs
There are several trade-offs when using GPIO, primarily time efficiency and resource usage:
- **Performance Overhead**: Though fast, reading and writing to GPIO pins can compete for attention with more critical operations. Systems with strict real-time requirements must account for the delays introduced by GPIO operations.

The speed and low-level control provided by GPIO are contrasted with higher-level communication interfaces like uart, which are more optimized for serial data transmission. However, the configuration complexity of these other interfaces often makes them less ideal for simple tasks that can be handled effectively with GPIO.

GPIO's ability to directly interact with hardware [[mcu]] makes it an indispensable feature for low-level control, but for applications requiring more sophisticated communication protocols and greater levels of abstraction, GPIO alone may not be sufficient, leading to dependency on more complex interfaces.

## See also
- [[rtos]]
- [[mcu]]
- interrupts