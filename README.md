# COMET Web Sensor - Sensitive Information Disclosure
<b>Fernando Parizzi</b>

Waiting for CVE<br>
<br>
<b>Confirmed Vulnerable Products and Versions:</b><br>
COMET Web Sensor Firmware Version: 1-5-5-1.0990 / 1.00<br>
<br>

<b>Confirmed Patched Version:</b><br>
Not Known Yet.<br>
<br>

<b>Vulnerable Products info:</b><br>
Comet Websensor T3510 - https://www.comet-america.com/products/web-sensor-remote-thermometer-hygrometer-with-ethernet-interface/reg-t3510 <br>
<br>

### Description:
The Web Sensor for Ambient Temperature and Relative Humidity with Remote Alarm is a high-precision device that monitors temperature and humidity. It features a capacitive polymer sensor for long-term stability and accuracy. The sensor provides additional data interpretation, such as dew point, absolute humidity, and specific enthalpy. A dual-line LCD display and remote alarm make it ideal for monitoring sensitive environments. Unfortunately, the device presented have an information disclosure vulnerability, where a user can alter the page's source code to read stored credentials. <br><br>

### Exploiting:
In the webpage, we can access the e-mail settings through "http://\<deviceIP\>/setup6.cfg" to observe the "hidden" e-mail credentials.<br>
<img width="994" height="823" alt="image" src="https://github.com/user-attachments/assets/24788b9a-0869-4ad9-8918-1fca55650d60" />

Checking the source code it is already possible to obtain the credentials hidden by bullet points:<br>
<img width="1033" height="606" alt="image" src="https://github.com/user-attachments/assets/72ae3dcb-ce7c-4f94-a689-9e3507d4c612" />

For the sake of elucidation, I will change the text type from "password" to "text":<br>
<img width="1061" height="542" alt="image" src="https://github.com/user-attachments/assets/8a6418c9-93cd-476f-926f-1003feeb5589" />

The sensitive information disclosure vulnerability is also present in the "<b>WWW and Security</b>" menu at "http://\<deviceIP\>/setupA.cfg":<br>
<img width="966" height="746" alt="image" src="https://github.com/user-attachments/assets/58c378e7-fcb3-4c53-8752-35ce287b06ad" />


This time the password isn't shown in the source code, however we can still change the text type from "password" to "text" in order to show the hidden admin password:<br>
<img width="844" height="664" alt="image" src="https://github.com/user-attachments/assets/dd2517ce-7bd6-4f05-b904-a7ae7073a541" />




