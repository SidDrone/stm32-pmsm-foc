# Sensorless FOC Motor Controller on STM32 with CAN Diagnostics

**Status: in progress.** This repository is being built; nothing here is a finished result yet.

## Goal

Field-oriented control in C on an STM32G4 (ST B-G431B-ESC1): Clarke/Park transforms, SVPWM and PI current loops in an ADC-triggered ISR; a PLL flux observer replacing the encoder; flux weakening; regenerative braking with a DC-bus overvoltage clamp; and FreeRTOS tasks serving UDS-style diagnostics over CAN.

## Layout

```
firmware/app/foc/         # Clarke/Park transforms, SVPWM, PI current loops.
firmware/app/observer/    # PLL flux observer and open-loop startup.
firmware/app/control/     # Speed loop, flux weakening, regenerative braking and DC-bus clamp.
firmware/app/diag/        # CAN, UDS-style services, DTC table, fault handling.
firmware/app/rtos/        # FreeRTOS task setup.
firmware/board/           # CubeMX-generated board init for the B-G431B-ESC1.
host-tests/               # Host-side unit tests for the control math.
tools/                    # python-can monitor and plotting scripts.
hardware/                 # BOM, wiring and photos of the bench setup.
docs/                     # Design notes, test plan and results.
```

## Plan

- [ ] Board bring-up and PWM/ADC timing
- [ ] Open-loop spin
- [ ] Current loops (FOC)
- [ ] Speed loop
- [ ] PLL flux observer (sensorless)
- [ ] Flux weakening
- [ ] Regenerative braking + DC-bus clamp
- [ ] FreeRTOS tasks + CAN/UDS diagnostics
- [ ] Measurements and write-up
