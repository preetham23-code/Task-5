task 5
2-Bit Comparator using VSDSquadron Mini Board
Overview
This project implements a 2-bit comparator using the VSDSquadron Mini Board. The comparator compares two 2-bit binary numbers and determines if one is greater than, less than, or equal to the other. The results are displayed using LEDs.
Project Objectives
Design a 2-bit comparator in C programming.
Implement it on the VSDSquadron Mini Board.
Verify functionality using LED indicators.
Gain hands-on experience in digital circuit design and hardware implementation.
Key Components
Component	Description
VSDSquadron Mini Board	Microcontroller for logic implementation
Breadboard & Jumper Wires	For circuit assembly
LEDs (3)	Display comparison results
220Ω Resistors	Current limiting for LEDs
Pin Configuration
LED	VSDSquadron Board
LED1 (Yellow, A > B)	PIN4 (PD4)
LED2 (Red, A = B)	PIN5 (PD5)
LED3 (Green, A < B)	PIN6 (PD6)
Functional Description
A > B → Yellow LED (LED1) lights up.
A = B → Red LED (LED2) lights up.
A < B → Green LED (LED3) lights up.
Truth Table
A1	A0	B1	B0	A > B	A = B	A < B
0	0	0	0	0	1	0
0	0	0	1	0	0	1
0	0	1	0	0	0	1
0	0	1	1	0	0	1
0	1	0	0	1	0	0
0	1	0	1	0	1	0
0	1	1	0	0	0	1
0	1	1	1	0	0	1
1	0	0	0	1	0	0
1	0	0	1	1	0	0
1	0	1	0	0	1	0
1	0	1	1	0	0	1
1	1	0	0	1	0	0
1	1	0	1	1	0	0
1	1	1	0	1	0	0
1	1	1	1	0	1	0
Code
#include <ch32v00x.h>
#include <debug.h>
#include <stdio.h>

#define LED1_PIN GPIO_Pin_4 // Yellow LED (A > B)
#define LED2_PIN GPIO_Pin_5 // Red LED (A = B)
#define LED3_PIN GPIO_Pin_6 // Green LED (A < B)
#define LED_PORT GPIOD

void GPIO_Config(void) {
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    GPIO_InitTypeDef GPIO_InitStructure;
    GPIO_InitStructure.GPIO_Pin = LED1_PIN | LED2_PIN | LED3_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(LED_PORT, &GPIO_InitStructure);
}

void compare_2bit(uint8_t a, uint8_t b) {
    GPIO_ResetBits(LED_PORT, LED1_PIN | LED2_PIN | LED3_PIN);

    if (a > b) {
        GPIO_SetBits(LED_PORT, LED1_PIN); // A > B: Yellow LED
    } else if (a == b) {
        GPIO_SetBits(LED_PORT, LED2_PIN); // A == B: Red LED
    } else {
        GPIO_SetBits(LED_PORT, LED3_PIN); // A < B: Green LED
    }
}

int main(void) {
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    for (uint8_t a = 0; a <= 3; a++) {
        for (uint8_t b = 0; b <= 3; b++) {
            compare_2bit(a, b);
            Delay_Ms(5000); // Delay for visualization
        }
    }
    
    return 0;
}
How to Use
Set up the circuit:
Connect LED1 (Yellow) to PD4, LED2 (Red) to PD5, LED3 (Green) to PD6 via 220Ω resistors.
Use jumper wires to connect components on a breadboard.
Flash the code onto the VSDSquadron Mini Board.
The board will cycle through all 2-bit number combinations, lighting up the respective LED based on the comparison result.
Expected Output
If A > B, the Yellow LED (PD4) lights up.
If A = B, the Red LED (PD5) lights up.
If A < B, the Green LED (PD6) lights up.
Conclusion
This project demonstrates a 2-bit comparator using C programming and hardware implementation on the VSDSquadron Mini Board. It provides hands-on experience in digital logic design, GPIO programming, and embedded systems.
