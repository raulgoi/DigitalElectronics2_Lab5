# DigitalElectronics2_Lab5
DISPLAY

## Link to my GitHub and name:

Raúl Gómez Ibáñez

Link: (https://github.com/raulgoi/DigitalElectronics2_Lab5)

## Difference between Common Catode and Common Anode 7-segment display

There are two types of LED 7-segment displays: common cathode and common anode. The difference between the two displays is the common cathode has all the cathodes of the 7-segments connected directly together and the common anode has all the anodes of the 7-segments connected together.
When working with a common anode seven segment display, power must be applied externally to the the anode connection that is common to all the segments. Then by applying a ground to a particular segment connection (a-g), the appropriate segment will light up.
A common cathode seven segment is different from a common anode segment in that the cathodes of all the LEDs are connected together. For the use of this seven segment the common cathode connection must be grounded and power must be applied to appropriate segment in order to illuminate that segment.

## Codes

### Counter to 59

   
     ISR(TIMER1_OVF_vect)
     {
          DDRD=0xFF;    
	        DDRB=0xFF;	
	        int x, D, U;  //Declare ports and variables
       
       while(1)
    {  	
		
	for (D=0; D<=5; D++) // Accumulate tens 
	{
		for (U=0; U<=9; U++)  // Accumulate Units
		{
			for (x=0; x<=62; x++)    //Alternate lits
			{
				PORTD=0X00;  
				PORTD=n[U];    
				PORTB=0b10000000;  
				_delay_ms(2);   
				
				PORTD=0x00;  
				PORTD=n[D];  
				PORTB=0b01000000;  
				_delay_ms(2);   
		  	}
		  }
   	}
	

      }
      

### Code display tens and units of a counter at SSD.

    ISR(TIMER0_OVF_vect)
       {
         static uint8_t pos = 0;
       }


    void loop()
    {
      for (int U = 0; U < 10; U++)
         for (int D = 0; D < 5; D++){
     
          display_D(D);

      {
        display_U(U);
      }
     }


## Flowchart

![Flowchart 2](https://user-images.githubusercontent.com/91128806/138856084-5ee5ca66-11c0-4f3e-8843-fbef738294db.png)



## Clock Picture


![Lab05_image](https://user-images.githubusercontent.com/91128806/138852184-34673bc1-c324-4f2b-a215-439f80d4c6c8.png)
