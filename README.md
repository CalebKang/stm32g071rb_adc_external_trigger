# stm32g071rb_adc_external_trigger

1. EXTI11이 들어오면 ADC Conversion을 실행. 

2. 실행 중에 ADC Window Watch Dog이 실행되며 설정 이상이면 CLL_OCP_FLAG 를 SET.

3. ADC Conversion Complete Callback에서 FLAG를 확인하여 SET되어 있으면 ADC Trigger를 Software trigger로 변경하고 계속해서 ADC Conversion.
    
4. ADC Conversion 결과가 설정 이하이며 FLAG를 RESET하고 ADC Trigger를 EXTI Trigger로 변경.
