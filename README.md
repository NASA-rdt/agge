Android and Google Glass Live Stream Application
--------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------

Modified by Asha Harris
-----------------------------------------------------------------

Import to Eclipse Android Developer Tools (ADT).

Establish a USB connection to the Google Glass or Android device, and enable debugging.

Right-click on liveGlass in Package Explorer and select "Run as Android Application".

Start the application, enter the Raspberry Pi IP address and port, and click “start”. (Note: native applications must be started from Eclipse on Google Glass. You must connect the Glass and run the application from Eclipse each time to start the app.)

Issues:

•	Wi-Fi on the GSFC campus blocks the necessary connection for testing the stream from the Raspberry Pi to the app; it is blocked. Tethering is also currently not allowed. 
  
  o	Possible Solution: create a Ustream account on ustream.com and substitute the IP address/port assignment section of     code in MainActivity.java for a URL assignment to the Ustream feed. This allows for access to a stream for testing without  needing to access the Raspberry Pi’s local network. I have been testing using this method recently.

String URL = "http://[ustream URL]";     
requestWindowFeature(Window.FEATURE_NO_TITLE);      
getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN,WindowManager.LayoutParams.FLAG_FULLSCREEN);         
mv = new MjpegView(this);      
setContentView(mv);              
new DoRead().execute(URL);

•	The application starts, but a blank screen appears when trying to access the live stream.
o	Possible Solution: This problem has not been solved, and the error is not stemming from the code so there has been difficulty in resolving where the cause of the issue. However, using the URL substitution (as shown in the last bullet pt.) may lead to a solution. 
  
  o	I have tried importing and utilizing the built in media player as well. (import android.media.MediaPlayer; )

