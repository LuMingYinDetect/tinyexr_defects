Affected Version:
tinyexr 1.0.8 6c8742cc8145c8f629698cd8248900990946d6b1

Vulnerability Description:
The vulnerability is a memory leak bug located at line 9291 of the file /tinyexr/tinyexr.h. This vulnerability could potentially be exploited maliciously to cause resource exhaustion and denial of service attacks.

tinyexr download address:
https://github.com/syoyo/tinyexr.git

Defect details:

1.In line 9172 of the file /tinyexr/tinyexr.h, a variable named 'header' is defined. In line 9230, the program allocates dynamic memory space for the member 'header.channels' of the 'header' variable using malloc. When the if statement in line 9290 evaluates to true, the program will return in line 9291, and the free(header.channels) operation in line 9294 will not be executed. This constitutes a memory leak defect, as shown in the figure below:

![image](https://github.com/LuMingYinDetect/tinyexr_defects/blob/main/tinyexr_1.png)
