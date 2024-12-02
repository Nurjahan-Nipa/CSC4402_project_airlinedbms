# CSC4402_project_airlinedbms

**Test Queries: **

Query-1: To retrieve the data values from crew table, we used 
    SELECT * from Crew
Query-2: To view the flight details we can mention the attributes in the select clause:
 
    SELECT FlightNumber, DepartureAirport, ArrivalAirport, 
    DepartureDateTime, ArrivalDateTime
    FROM Flight;
    
Query-3: We can search passengers by loyalty status by using the query as: 

    SELECT PassengerName, LoyaltyStatus 
    FROM Passenger 
    WHERE LoyaltyStatus = 'Gold';
    
Query-4: Retrieving flights with crew members can be queried in this way:
    
    SELECT f.FlightNumber, c.CrewName, c.Position
    FROM Flight f
    JOIN FlightCrew fc ON f.FlightNumber = fc.FlightNumber
    JOIN Crew c ON fc.CrewID = c.CrewID;
    
Query-5: To view the passengers with reservation, we can query like this:
   
    SELECT p.PassengerName, r.FlightNumber, r.SeatNumber, r.FareClass
    FROM Passenger p
    JOIN Reservation r ON p.PassengerName = r.PassengerName;
    
Query-6:  List Flights by a Specific Crew Member:

     SELECT f.FlightNumber, f.DepartureAirport, f.ArrivalAirport,
     f.DepartureDateTime, f.ArrivalDateTime
     FROM Flight f
     JOIN FlightCrew fc ON f.FlightNumber = fc.FlightNumber
     JOIN Crew c ON fc.CrewID = c.CrewID
     WHERE c.CrewName = 'Paul Roberts';
    
Query-7:  We can count the total number of passengers by loyalty status:

    SELECT LoyaltyStatus, COUNT(*) AS TotalPassengers
    FROM Passenger
    GROUP BY LoyaltyStatus;
   
Query-8:  To count reservations by fare class, we use the following query:

    SELECT FareClass, COUNT(*) AS TotalReservations
    FROM Reservation
    GROUP BY FareClass;
   
