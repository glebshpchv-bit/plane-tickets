Here's a conceptual data model for "Бронирование билетов на самолет" (Airplane Ticket Booking).

### 1. Textual Description of Entities and Relationships

**Entities:**

*   **Airport:** Represents a physical airport location.
    *   **Attributes:** Airport ID (Primary Key), Name, City, Country, IATA Code.
*   **Airline:** Represents an airline company.
    *   **Attributes:** Airline ID (Primary Key), Name, IATA Code.
*   **Aircraft:** Represents a specific type of airplane model.
    *   **Attributes:** Aircraft ID (Primary Key), Model Name, Manufacturer, Capacity.
*   **Flight:** Represents a scheduled flight between two airports on a specific date and time.
    *   **Attributes:** Flight ID (Primary Key), Flight Number, Departure DateTime, Arrival DateTime, Price (base), Available Seats.
*   **Passenger:** Represents an individual person who will be flying.
    *   **Attributes:** Passenger ID (Primary Key), First Name, Last Name, Date of Birth, Passport Number, Email, Phone Number.
*   **Booking:** Represents a reservation made by a customer, which can include one or more tickets for different passengers and/or flights.
    *   **Attributes:** Booking ID (Primary Key), Booking Date, Total Price, Booking Status (e.g., Confirmed, Pending, Cancelled), Payment Status.
*   **Ticket:** Represents a single ticket for a specific passenger on a specific flight within a booking. This is an associative entity linking Passengers, Flights, and Bookings.
    *   **Attributes:** Ticket ID (Primary Key), Seat Number, Class (e.g., Economy, Business), Ticket Status (e.g., Issued, Used, Cancelled), Price (final, specific to this ticket).

**Relationships:**

*   **Airport - Flight (Departure):** An `Airport` serves as the departure location for many `Flights`. A `Flight` has exactly one departure `Airport`.
    *   *Cardinality:* One-to-Many (1:M)
*   **Airport - Flight (Arrival):** An `Airport` serves as the arrival location for many `Flights`. A `Flight` has exactly one arrival `Airport`.
    *   *Cardinality:* One-to-Many (1:M)
*   **Airline - Flight:** An `Airline` operates many `Flights`. A `Flight` is operated by exactly one `Airline`.
    *   *Cardinality:* One-to-Many (1:M)
*   **Aircraft - Flight:** An `Aircraft` model can be used for many `Flights`. A `Flight` is assigned to exactly one `Aircraft` model.
    *   *Cardinality:* One-to-Many (1:M)
*   **Booking - Ticket:** A `Booking` can contain one or many `Tickets`. A `Ticket` belongs to exactly one `Booking`.
    *   *Cardinality:* One-to-Many (1:M)
*   **Passenger - Ticket:** A `Passenger` can have many `Tickets` (across different bookings/flights). A `Ticket` is issued for exactly one `Passenger`.
    *   *Cardinality:* One-to-Many (1:M)
*   **Flight - Ticket:** A `Flight` can have many `Tickets` (up to its capacity). A `Ticket` is for exactly one `Flight`.
    *   *Cardinality:* One-to-Many (1:M)

### 2. Mermaid.js ER Diagram

```mermaid
erDiagram
    Airport {
        string id PK "Airport ID"
        string name "Airport Name"
        string city "City"
        string country "Country"
        string iata_code "IATA Code"
    }

    Airline {
        string id PK "Airline ID"
        string name "Airline Name"
        string iata_code "IATA Code"
    }

    Aircraft {
        string id PK "Aircraft ID"
        string model_name "Model Name"
        string manufacturer "Manufacturer"
        int capacity "Capacity"
    }

    Flight {
        string id PK "Flight ID"
        string flight_number "Flight Number"
        datetime departure_datetime "Departure Date/Time"
        datetime arrival_datetime "Arrival Date/Time"
        decimal base_price "Base Price"
        int available_seats "Available Seats"
    }

    Passenger {
        string id PK "Passenger ID"
        string first_name "First Name"
        string last_name "Last Name"
        date date_of_birth "Date of Birth"
        string passport_number "Passport Number"
        string email "Email"
        string phone_number "Phone Number"
    }

    Booking {
        string id PK "Booking ID"
        date booking_date "Booking Date"
        decimal total_price "Total Price"
        string booking_status "Booking Status"
        string payment_status "Payment Status"
    }

    Ticket {
        string id PK "Ticket ID"
        string seat_number "Seat Number"
        string class_type "Class Type"
        string ticket_status "Ticket Status"
        decimal final_price "Final Price"
    }

    Airport ||--o{ Flight : has_departure_from
    Airport ||--o{ Flight : has_arrival_at
    Airline ||--o{ Flight : operates
    Aircraft ||--o{ Flight : used_for
    Flight ||--o{ Ticket : books_seat_on
    Passenger ||--o{ Ticket : is_for
    Booking ||--o{ Ticket : contains
```