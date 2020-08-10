# gist: STM32 triggered N pulse

About 

- how to use an advanced timer (TIM1 for F401) to generate N pulses output when receiving a trigger, and
- How to generate PWM using TIMs

[There](./README-res/res.md) are more snap shots from CubeMX

##### To output PWM

1. Set Mode: Channel? PWM Generation
2. Counter setting: Prescaler/Counter Period = ?
3. PWM Generation Channel ? > Pulse = ?
4. `HAL_TIM_PWM_Start(&htim?, TIM_CHANNEL_?)`
5. BE CAREFUL WITH `GPIO max speed`

##### To output N pulses after trigger signal

1. Slave Mode: Trigger Mode
2. Trigger Source: TI1FP1: TI1(Timer input 1) after FP(filter and polarity selection)
3. Channel 2: PWM Generation CH2
4. One Pulse Mode: Enable
5. Counter Setting > Prescaler/Counter Period = ?
6. Counter Setting > Repeatition Counter = N pulse
7. Trigger > Polarity/Filter
8. PWM Generation Channel 2 > Pulse = ?
9. `HAL_TIM_PWM_Start(&htim?, TIM_CHANNEL_?)`
10. BE CAREFUL WITH `GPIO max speed`

## Reference materials

Datasheet [stm32f401re.pdf](./README-res/stm32f401re.pdf) 

F401 resources reference manual [dm00096844...](./README-res/dm00096844-stm32f401xbc-and-stm32f401xde-advanced-armbased-32bit-mcus-stmicroelectronics.pdf) 

Cortex M4 Programming Manual [dm00046982...](./README-res/dm00046982-stm32-cortexm4-mcus-and-mpus-programming-manual-stmicroelectronics.pdf) 