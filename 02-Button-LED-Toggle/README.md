# STM32: Button Toggle with Debouncing & Pull-down Resistor


مشروع للتحكم في تشغيل وإطفاء LED وضع Toggle باستخدام زر ضغط ومتحكم STM32 مع معالجة التشويش الميكانيكي (Debounce)

----
## المكونات المستخدمه:
* لوحة Blue pill
* زر ضغط اربع اطراف
* مقاومة 220 اوم (Pull-down)
* لمبة LED
* مقاومة حماية 220 اوم
* اسلاك
----

## الكود البرمجي (Main Logic):
```c
while (1)
{
     if (HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_SET)
	{
		HAL_Delay(50);

		if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == 1)
		{

			HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);

			while (HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_SET)
			{

			}

			HAL_Delay(50);
		}
}

----

<img width="1178" height="493" alt="image" src="https://github.com/user-attachments/assets/a1c80384-1333-469c-bee0-b117bae35b3b" />

----

<img width="1785" height="2381" alt="٢٠٢٦٠٨٠١_١٨٤٩١٤" src="https://github.com/user-attachments/assets/60cefe5b-d5b4-40cf-9773-22027d7ca781" />
