/**
  @page EXTI_Example EXTI Configuration Example
  
  @verbatim
  ******************** (C) COPYRIGHT 2012 STMicroelectronics *******************
  * @file    EXTI/EXTI_Example/readme.txt 
  * @author  MCD Application Team
  * @version V1.0.0
  * @date    20-September-2012
  * @brief   Description of the EXTI example.
  ******************************************************************************
  *
  * Licensed under MCD-ST Liberty SW License Agreement V2, (the "License");
  * You may not use this file except in compliance with the License.
  * You may obtain a copy of the License at:
  *
  *        http://www.st.com/software_license_agreement_liberty_v2
  *
  * Unless required by applicable law or agreed to in writing, software 
  * distributed under the License is distributed on an "AS IS" BASIS, 
  * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  * See the License for the specific language governing permissions and
  * limitations under the License.
  *
  ******************************************************************************
  @endverbatim

@par Example Description 

This example shows how to configure external interrupt lines.

In this example, 4 EXTI lines (EXTI0, EXTI2, EXTI6 and EXTI10) when using the STM32373C-EVAL
are configured to generate an interrupt on each falling edge. In the interrupt routine a led
connected to a specific GPIO pin is toggled.

In this example
    - EXTI0  is mapped to PA0
    - EXTI2  is mapped to PA2 
    - EXTI6  is mapped to PE6  
    - EXTI10 is mapped to PF10

After EXTI configuration, a software interrupt is generated on the EXTI0 toggles LED1.
After that,
  when rising edge is detected on EXTI0, LED1 toggles
  when falling edge is detected on EXTI2, LED4 toggles
  when rising edge is detected on EXTI6, LED2 toggles
  when rising edge is detected on EXTI10, LED3 toggles

If STM32373C-EVAL is used,
  when Tamper pushbutton is pressed, LED1 toggles
  when Joystick Sel pushbutton is pressed, LED2 toggles
  when Joystick Up pushbutton is pressed, LED3 toggles
  when Key pushbutton is pressed, LED4 toggles

In this example, EXTI0_Config() function can be substituted by 
STM_EVAL_PBInit(BUTTON_TAMPER, Mode_EXTI) provided in the STM32373C-EVAL driver.
 

@par Directory contents 

  - EXTI/EXTI_Example/stm32f37x_conf.h    Library Configuration file
  - EXTI/EXTI_Example/stm32f37x_it.c      Interrupt handlers
  - EXTI/EXTI_Example/stm32f37x_it.h      Interrupt handlers header file
  - EXTI/EXTI_Example/main.c              Main program
  - EXTI/EXTI_Example/system_stm32f37x.c  STM32F37x system source file
  
@note The "system_stm32f37x.c" is generated by an automatic clock configuration 
      system and can be easily customized to your own configuration. 
      To select different clock setup, use the "STM32F37x_Clock_Configuration_V1.0.0.xls" 
      provided with the AN4132 package available on <a href="http://www.st.com/internet/mcu/family/141.jsp">  ST Microcontrollers </a>
         
@par Hardware and Software environment

  - This example runs on STM32F37x Devices.
  
  - This example has been tested with STMicroelectronics STM32373C-EVAL (STM32F37x)
    evaluation board and can be easily tailored to any other supported device 
    and development board.

  - STM32373C-EVAL Set-up
    - Use LD1 led connected to PC0 pin
    - Use LD2 led connected to PC1 pin
    - Use LD3 led connected to PC2 pin
    - Use LD4 led connected to PC3 pin
    - Use the Tamper push-button connected to pin PA0 (EXTI Line0)
    - Use the Key push-button connected to pin PA2 (EXTI Line2)
    - Use the Joystick Sel push-button connected to pin PE6 (EXTI Line6)
    - Use the Joystick Up push-button connected to pin PF10 (EXTI Line10)

@par How to use it ? 

In order to make the program work, you must do the following :
 - Copy all source files from this example folder to the template folder under
   Project\STM32F37x_StdPeriph_Templates
 - Open your preferred toolchain 
 - Rebuild all files and load your image into target memory
 - Run the example

 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
