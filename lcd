#include <unistd.h>
#include <stdio.h>
#include "library.h"


#define  LEDport  1


	//const unsigned  char val[] ={"Hello World"};
	//const unsigned char value[] = {"Welcome TO RPi"};

/* store this table in code space */
const unsigned char Bin2LED[] =
 
/*  0     1     2    3 */
{0x40, 0x79, 0x24, 0x30,
/*  4     5     6    7*/
0x19, 0x12, 0x02, 0x78,
/*  8     9     A    B*/
0x00, 0x18, 0x08, 0x03,
/*  C     D     E    F*/
0x46, 0x21, 0x06, 0x0E
};


int main(int argc, char *argv[])
{

  CM3DeviceInit();
  CM3PortInit(LEDport);

	int i,sec,LCDval,LCDvalue;

	
	while(1)
	{
        
		printf("lcd display on\n");

        position_set_lcd(1);    //positon
   
     
		i = 0;	
	do
		{
			sec = i/10;
			LCDval = val[i];
		    CM3PortWrite(LEDport,LcDval);
			printf("%c",LCDval);
		    i++;
		}while(i<11);
		
		printf("/n");
	    position_set_lcd(2);
	
        i = 0;
	do
		{
			
			sec = i/10;
            LCDvalue = value[i];
			CM3PortWrite(LEDport,LCDvalue);
			printf("%c",LCDvalue);
		
		}while(i<14);
         printf("\n");
		
		clear_display();
		printf("display off\n");
		sleep(1);                //non blocking sleep
	}



	CM3DeviceDeInit();   


}  
