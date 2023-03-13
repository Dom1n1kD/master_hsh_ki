Erklärung der Fakten:

airline(lufthansa). <- Die Lufthansa ist als Fluggesellschaft in der Datenbank definiert
insolvent(airberlin). <- Die Fluggesellschaft Airberlin ist insolvent 
employees(tuifly, 70000). <- Die Fluggesellschaft TuiFly beschäftigt 70000 Mitarbeiter
passengers(ryanair, 193200000). <- Die Fluggesellschaft Ryanair transportiert 193,2 Millionen Passagiere pro Jahr 
aircraft(eurowings, a319, airbus). <- Die Fluggesellschaft Eurowings fliegt mit dem Flugzeug Modell A319 von Airbus 

Erklärung der Regeln:

operating(AIRLINE, X) :- 
	not(insolvent(AIRLINE)). <- Die Fluggesellschaften, die nicht insolvent sind, sind im Betrieb
topairline(AIRLINE) :-
	operating(AIRLINE),
	passengers(AIRLINE, P),
	P > 100000000. <- Fluggesellschaften mit mehr als 100 Passagieren pro Jahr gehören zu den Top-Fluggesellschaften

Schreiben Sie eine Abfrage pro Aufgabe in PROLOG:

- Überprüfen Sie, ob Delta als Fluggesellschaft in der Datenbank definiert ist
airline(delta)

- Finden Sie alle insolventen Fluggesellschaften
insolvent(X)

- Überprüfen Sie, ob SAS laut Datenbank im Betrieb ist
not(insolvent(sas))

- Überprüfen Sie, ob mindestens eine der Fluggesellschaften WoWAir oder Wizzair im Betrieb sind
insolvent(wowair);insolvent(wizzair)

- Finden Sie die Fluggesellschaft, die laut Datenbank genau 142,3 Millionen Passagiere pro Jahr befördert *
passengers(X, 142300000)

- Finden Sie die Fluggesellschaft, die laut Datenbank mehr als 100 Tausend Mitarbeiter beschäftigt*
employees(X, P), P>100000

- Finden Sie die Fluggesellschaft, die laut Datenbank weniger als 10 Tausend Mitarbeiter beschäftigt*
employees(X, P), P<10000

- Finden Sie die Fluggesellschaft, die laut Datenbank mehr als 100 Millionen Passagiere pro Jahr befördert und weniger als 20 Tausend Mitarbeiter hat*
passengers(X, P), P>100000000, employees(X, E), E<20000

- Überprüfen Sie, ob Airfrance zu den Top-Fluggesellschaften gehört?*
topairline(airfrance)

- Überprüfen Sie, ob British Airways zu den Top-Fluggesellschaften gehört oder genau 45 Tausend Mitarbeiter beschäftigt* 
topairline(britishairways);employees(britishairways,45000)

- Finden Sie alle Fluggesellschaften, die mit dem Airbus A380 fliegen*
aircraft(X, a380, airbus)

- Finden Sie alle Flugzeugmodelle von Boing der Fluggesellschaft Airfrance*
aircraft(airfrance, X, boeing)

- Finden Sie die Fluggesellschaften, die mit dem Modell 737 von Boeing fliegen*
aircraft(X, 737, boeing)

Zusatzaufgabe:

- Finden Sie alle Flugzeugmodelle von Bombardier der Datenbank*
aircraft(X, Y, bombardier)

- Finden Sie die insolvente Airline, die Flugzeuge von Boeing, Cessna und Bombardier hatte 
insolvent(X), (aircraft(X, A, boeing), aircraft(X, B, cessna), aircraft(X, C, bombardier))