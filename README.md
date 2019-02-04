# Elcykelpool
Utvecklingsprojekt på Högskolan i Halmstad

Hyr en elcykel via en hemsida, cykeln hämtas och lämnas från ett elcykelgarage. 

Server:
Raspberry pi, raspbian.
phpMyAdmin, MySQL databas
Hemsida (wordpress) bokning av elcykel. Registrering/inloggning, bokning, uthämtning/inlämning av cykel. Sparas i databasen.
PHP skript utanför hemsidan. Kollar igenom databasen efter händelser (t.ex. en kund vill hämta ut en bokad cykel), skickar tillhörande meddelande till respektive "fack" i garget (t.ex. lämna ut cykel). Hämtar information från alla garage och uppdaterar status i databasen.
UDP Modbus meddelande mellan server och garage.

Gateway:
Arduino Uno i garage som konverterar mellan UDP Modbus och RTU Modbus.

Garage:
