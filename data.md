## Common SQL Data Types in MySQL 8.0:

When creating tables in a MySQL database, it's important to choose the right data types for each column. Here are some of the most commonly used data types, including new ones introduced in MySQL 8.0, categorized by their use for strings, numbers, and dates/times.

### String Data Types

- **CHAR(size)**: A fixed-length string. The size parameter specifies the length of the string (from 0 to 255). For example, CHAR(10) will always store 10 characters.

- **VARCHAR(size)**: A variable-length string. The size parameter specifies the maximum length of the string (from 0 to 65,535). For example, VARCHAR(255) can store up to 255 characters.

- **TEXT**: A string with a maximum length of 65,535 characters. Used for larger blocks of text.

- **TINYTEXT**: A string with a maximum length of 255 characters. Useful for small pieces of text.

- **MEDIUMTEXT**: A string with a maximum length of 16,777,215 characters. Suitable for longer text blocks.

- **LONGTEXT**: A string with a maximum length of 4,294,967,295 characters. Ideal for very large text blocks.

### Number Data Types

- **INT**: A standard integer. The range can be specified using UNSIGNED to allow only non-negative numbers. For example, INT UNSIGNED ranges from 0 to 4,294,967,295.

- **SMALLINT**: A small integer. The range is from -32,768 to 32,767 or from 0 to 65,535 if UNSIGNED.

- **BIGINT**: A large integer. The range is from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 or from 0 to 18,446,744,073,709,551,615 if UNSIGNED.

- **FLOAT**: A floating-point number. Suitable for single-precision floating-point numbers.

- **DOUBLE**: A double-precision floating-point number. Suitable for double-precision floating-point numbers.

- **DECIMAL(size, d)**: A fixed-point number. The size parameter specifies the total number of digits, and the d parameter specifies the number of digits after the decimal point. For example, DECIMAL(10, 2) can store a number with up to 8 digits before the decimal and 2 digits after.

### Date and Time Data Types

- **DATE**: A date in 'YYYY-MM-DD' format. For example, '2023-01-01'.

- **TIME**: A time in 'HH:MM:SS' format. For example, '12:30:45'.

- **DATETIME**: A date and time combination in 'YYYY-MM-DD HH:MM:SS' format. For example, '2023-01-01 12:30:45'.

- **TIMESTAMP**: A timestamp, typically used for tracking changes to records. Similar to DATETIME but with automatic updating features.

- **YEAR**: A year in four-digit format. For example, '2023'.

### New Data Types in MySQL 8.0

- **JSON**: Stores JSON (JavaScript Object Notation) data. Allows for efficient storage and retrieval of JSON formatted data.

- **GEOMETRY**: A data type for geometric values. Used for spatial data storage.


__Note__
:There are many data types in SQL which has not mentioned here. Please refer to MySQL documentations.



## Constraint

### Common SQL Constraints Explained for Non-Tech Students:

When working with databases, certain rules called "constraints" are used to keep the data accurate and consistent. Here are some of the most common ones:

- **NOT NULL**: This rule ensures that a column always has a value. It prevents any empty or "NULL" values in that column. For example, if you have a table of students, you might use NOT NULL to make sure every student has an ID number.

- **UNIQUE**: This constraint makes sure that all the values in a column are different from each other. For instance, in a table of students, each student's email address should be unique.

- **PRIMARY KEY**: This is a special kind of constraint that combines NOT NULL and UNIQUE. It uniquely identifies each row in a table. Think of it as a unique ID for each row, ensuring there are no duplicates and that every row can be individually identified.

- **FOREIGN KEY**: This constraint creates a link between two tables. It ensures that a value in one table corresponds to a valid value in another table. For example, if you have a table of students and a table of courses, a foreign key can ensure that a student ID in the courses table matches a valid student in the students table.

- **CHECK**: This rule ensures that the values in a column meet a specific condition. For example, you can use CHECK to make sure the age of a student is greater than 0.

- **DEFAULT**: This constraint sets a default value for a column if no value is specified when a new row is added. For example, if you have a column for a student's enrollment status, you could set the default value to "active."

- **CREATE INDEX**: This is not a constraint but a helpful tool to speed up the retrieval of data from the database. It creates an index that makes searching for data faster, similar to an index in a book.


## Data to insets in the tables

``` sql
INSERT INTO airports (name, city, country, iata_code, icao_code)
VALUES
('Los Angeles International', 'Los Angeles', 'USA', 'LAX', 'KLAX'),
('John F. Kennedy International', 'New York', 'USA', 'JFK', 'KJFK'),
('Heathrow', 'London', 'UK', 'LHR', 'EGLL'),
('Charles de Gaulle', 'Paris', 'France', 'CDG', 'LFPG'),
('Haneda', 'Tokyo', 'Japan', 'HND', 'RJTT'),
('Dubai International', 'Dubai', 'UAE', 'DXB', 'OMDB'),
('Frankfurt', 'Frankfurt', 'Germany', 'FRA', 'EDDF'),
('Singapore Changi', 'Singapore', 'Singapore', 'SIN', 'WSSS'),
('Sydney Kingsford Smith', 'Sydney', 'Australia', 'SYD', 'YSSY'),
('Toronto Pearson International', 'Toronto', 'Canada', 'YYZ', 'CYYZ');


INSERT INTO aircrafts 
    (model, manufacturer, capacity) 
VALUES
    ('Boeing 737', 'Boeing', 189),
    ('Airbus A320', 'Airbus', 180),
    ('Boeing 777', 'Boeing', 396),
    ('Airbus A380', 'Airbus', 555),
    ('Embraer E190', 'Embraer', 114),
    ('Boeing 787 Dreamliner', 'Boeing', 242),
    ('Airbus A350', 'Airbus', 325),
    ('Bombardier CRJ200', 'Bombardier', 50),
    ('Boeing 747', 'Boeing', 416),
    ('Airbus A330', 'Airbus', 335),
    ('Cessna 172', 'Cessna', 4),
    ('Boeing 767', 'Boeing', 269),
    ('Airbus A321', 'Airbus', 220),
    ('Boeing 757', 'Boeing', 239),
    ('Airbus A220', 'Airbus', 160);


INSERT INTO Airlines 
    (name, country) 
VALUES 
    ('American Airlines', 'USA'),
    ('Delta Air Lines', 'USA'),
    ('United Airlines', 'USA'),
    ('Southwest Airlines', 'USA'),
    ('Alaska Airlines', 'USA'),
    ('JetBlue Airways', 'USA'),
    ('Spirit Airlines', 'USA'),
    ('Frontier Airlines', 'USA'),
    ('Hawaiian Airlines', 'USA'),
    ('Allegiant Air', 'USA'),
    ('British Airways', 'UK'),
    ('Lufthansa', 'Germany'),
    ('Air France', 'France'),
    ('KLM Royal Dutch Airlines', 'Netherlands'),
    ('Emirates', 'UAE'),
    ('Qatar Airways', 'Qatar'),
    ('Singapore Airlines', 'Singapore'),
    ('Cathay Pacific', 'Hong Kong'),
    ('Qantas', 'Australia'),
    ('Air New Zealand', 'New Zealand');

INSERT INTO Flights 
    (airline_id, aircraft_id, departure_airport_id, arrival_airport_id, departure_time, arrival_time, status) 
VALUES
    (1, 1, 1, 2, '2024-08-10 08:00:00', '2024-08-10 10:00:00', 'Scheduled'),
    (2, 2, 2, 3, '2024-08-11 09:00:00', '2024-08-11 11:00:00', 'Scheduled'),
    (3, 3, 3, 4, '2024-08-12 10:00:00', '2024-08-12 12:00:00', 'Scheduled'),
    (1, 2, 1, 3, '2024-08-13 07:00:00', '2024-08-13 09:30:00', 'Scheduled'),
    (2, 3, 2, 4, '2024-08-14 06:00:00', '2024-08-14 08:45:00', 'Scheduled'),
    (3, 1, 3, 1, '2024-08-15 12:00:00', '2024-08-15 14:30:00', 'Scheduled'),
    (1, 3, 4, 1, '2024-08-16 05:00:00', '2024-08-16 07:30:00', 'Scheduled'),
    (2, 1, 4, 2, '2024-08-17 04:00:00', '2024-08-17 06:15:00', 'Scheduled');

INSERT INTO Passengers 
    (first_name, last_name, email, phone, passport_number) 
VALUES
    ('John', 'Doe', 'john.doe@example.com', '123-456-7890', 'A12345678'),
    ('Jane', 'Smith', 'jane.smith@example.com', '234-567-8901', 'B23456789'),
    ('Alice', 'Johnson', 'alice.johnson@example.com', '345-678-9012', 'C34567890'),
    ('Bob', 'Brown', 'bob.brown@example.com', '456-789-0123', 'D45678901'),
    ('Charlie', 'Davis', 'charlie.davis@example.com', '567-890-1234', 'E56789012'),
    ('David', 'Wilson', 'david.wilson@example.com', '678-901-2345', 'F67890123'),
    ('Emily', 'Clark', 'emily.clark@example.com', '789-012-3456', 'G78901234'),
    ('Frank', 'Lewis', 'frank.lewis@example.com', '890-123-4567', 'H89012345'),
    ('Grace', 'Walker', 'grace.walker@example.com', '901-234-5678', 'I90123456'),
    ('Henry', 'Robinson', 'henry.robinson@example.com', '012-345-6789', 'J01234567');

INSERT INTO Passenger_Details 
    (passenger_id, date_of_birth, nationality, address) 
VALUES
    (1, '1980-01-01', 'USA', '123 Elm St, Springfield, IL'),
    (2, '1990-02-02', 'USA', '456 Maple St, Springfield, IL'),
    (3, '1985-03-03', 'USA', '789 Oak St, Springfield, IL'),
    (4, '1975-04-04', 'USA', '101 Pine St, Springfield, IL'),
    (5, '1995-05-05', 'USA', '202 Birch St, Springfield, IL'),
    (6, '1988-06-06', 'USA', '303 Cedar St, Springfield, IL'),
    (7, '1992-07-07', 'USA', '404 Spruce St, Springfield, IL'),
    (8, '1983-08-08', 'USA', '505 Walnut St, Springfield, IL'),
    (9, '1979-09-09', 'USA', '606 Ash St, Springfield, IL'),
    (10, '1991-10-10', 'USA', '707 Chestnut St, Springfield, IL');

INSERT INTO Bookings 
    (flight_id, passenger_id, seat_number, booking_date, status) 
VALUES
    (1, 1, '12A', '2024-08-01 14:30:00', 'Confirmed'),
    (2, 2, '14B', '2024-08-02 09:45:00', 'Cancelled'),
    (3, 3, '15C', '2024-08-03 17:00:00', 'Confirmed'),
    (1, 4, '16D', '2024-08-04 12:15:00', 'Pending'),
    (2, 5, '17E', '2024-08-05 20:30:00', 'Confirmed'),
    (3, 6, '18F', '2024-08-06 22:45:00', 'Checked-In'),
    (1, 7, '19G', '2024-08-07 11:00:00', 'Confirmed'),
    (2, 8, '20H', '2024-08-08 08:15:00', 'Cancelled'),
    (3, 9, '21I', '2024-08-09 19:30:00', 'Confirmed'),
    (1, 10, '22J', '2024-08-10 07:45:00', 'Confirmed'),
    (2, 11, '23K', '2024-08-11 14:00:00', 'Pending'),
    (3, 12, '24L', '2024-08-12 16:30:00', 'Confirmed'),
    (1, 13, '25M', '2024-08-13 13:15:00', 'Checked-In'),
    (2, 14, '26N', '2024-08-14 21:00:00', 'Confirmed'),
    (3, 15, '27O', '2024-08-15 10:45:00', 'Cancelled');

INSERT INTO Crew 
    (first_name, last_name, position, hire_date)
VALUES
    ('John', 'Doe', 'Pilot', '2015-05-20'),
    ('Jane', 'Smith', 'Co-Pilot', '2016-08-12'),
    ('Emily', 'Jones', 'Flight Attendant', '2018-11-03'),
    ('Michael', 'Brown', 'Flight Attendant', '2019-02-15'),
    ('Sarah', 'Davis', 'Engineer', '2017-09-29');


INSERT INTO Flight_Crew 
    (flight_id, crew_id, role)
VALUES
    (1, 1, 'Pilot'),
    (1, 2, 'Co-Pilot'),
    (1, 3, 'Flight Attendant'),
    (1, 4, 'Flight Attendant'),
    (2, 1, 'Pilot'),
    (2, 5, 'Engineer'),
    (3, 2, 'Co-Pilot'),
    (3, 3, 'Flight Attendant'),
    (4, 1, 'Pilot'),
    (4, 4, 'Flight Attendant');
```

