# STM32: Basic Button & LED Control
مشروع تجريبي بسيط لزر ضغط (Push Button) بمتحكم stm32 لتحكم في تشغيل و اطفاء LED 
----

## المكونات المستخدمه:
* لوحة Blue pill
* زر ضغط اربع اطراف
* مقاومة 220 اوم (Pull-down)
* لمبة LED
* مقاومة حماية 220 اوم
* اسلاك
----
## ملخص التجربة والملاحظات الفنية
1. **بدون مقاومة (Floating):** التقاط تشويش كهربائي من الجو يسبب إضاءة عشوائية لليد.
2. **شورت مباشر:** توصيل مباشر للـ GND يسبب سحب عالي للتيار (Short Circuit).
3. **الحل الصحيح:** استخدام مقاومة Pull-down خارجية لضمان قراءة مستقرة (`0` في حالة الترك، و `3.3V` عند الضغط).
----

----
 while (1)
  {
	
	    if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0)==GPIO_PIN_SET)
	  	  {
	  	      HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
	  	  }
	  	  else
	  	  {
	  	      HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
	  	  }
}

----

<img width="1178" height="493" alt="image" src="https://github.com/user-attachments/assets/a1c80384-1333-469c-bee0-b117bae35b3b" />
----
<img width="1785" height="2381" alt="٢٠٢٦٠٨٠١_١٨٤٩١٤" src="https://github.com/user-attachments/assets/60cefe5b-d5b4-40cf-9773-22027d7ca781" />

