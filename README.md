# Elcykelpool
Utvecklingsprojekt på Högskolan i Halmstad <br>
Hyr en elcykel via en hemsida, cykeln hämtas och lämnas från ett elcykelgarage. 

Server (master): <br>
Server på en Raspberry pi 3, raspbian.
phpMyAdmin, MySQL databas
Hemsida (wordpress) bokning av elcykel. Registrering/inloggning, bokning, uthämtning/inlämning av cykel. Sparas i databasen.
PHP skript utanför hemsidan. Kollar igenom databasen efter händelser (t.ex. en kund vill hämta ut en bokad cykel), skickar tillhörande meddelande till respektive "fack" i garget (t.ex. lämna ut cykel). Hämtar information från alla garage och uppdaterar status i databasen.
UDP Modbus meddelande mellan server och garage.

Gateway: <br>
Arduino Uno i garage som konverterar mellan UDP Modbus och RTU Modbus. Ethernet-kabel mellan server och gateway under utvecklingen (ethernet-shield). Gateway kommunicerar mellan alla fack parallellkopplade via RS-485.

Garage (slave): <br>
Arduino Pro Mini, en i varje fack (3st per garage). Tar emot och svarar på RTU Modbus meddelanden. Sköter styrning av garage (knappsats, lampor, cykelhiss, dörrlås, dörrgivare, cykelgivare, laddningsspänning osv.).

# Verktyg/metoder använda/lärda
Raspberry pi 3, raspbian (linux) operativsystem <br>
Arduino, arduino create, C++ <br>
Internet kommunikation. IPv4, mac, dhcp, ssh, telnet, udp, socket, port <br>
RS-485, RS-232, RS-422. RTU Modbus <br>
PHP, hämta från och skriva till MySQL databas. Skicka/ta emot UDP meddelanden <br>
PHPMyAdmin, MySQL databas <br>
Wordpress <br>
