#include<stdio.h>
#include<unistd.h>

#include "library.h"

#define LEDPort 0

const unsigned char Bin2LED[] = 
                               /*  0     1     2    3 */
                               {0x3f,  0x06,  0x5b, 0x4f,
                               /*  4     5     6    7*/
                               0x66,   0x6d,   0x7d, 0x07,
                               /*  8     9     A    B*/
                               0x7f,  0x67,   0x77, 0x7c, 
                               /*  C     D     E    F*/
                                0x39, 0x5e,   0x79, 0x71};


                              
int main(int argc, char *argv[])
{

   	CM3DeviceInit();
        CM3PortInit(LEDPort);
     
        int i,sec,LEDval;

   	i = 0;

	printf(" lab_1\n");

	while(1)
	{
                sec = i/10;
               	
                LEDval = Bin2LED[i];	
                      
		CM3PortWrite(LEDPort,LEDval);

		printf(" %d \n",i);
                
                i++;
                 
                if(i == 16)
                  { 
                    i = 0;
                   } 

		sleep(1);	  // non blocking sleep

	}

   	CM3DeviceDeInit();
	return 0;
}  
