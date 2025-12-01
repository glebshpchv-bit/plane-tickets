As an expert Agile Product Owner, here are comprehensive User Stories for an airplane ticket booking system ("Бронирование билетов на самолет"), following the INVEST principle. Acceptance Criteria are provided for key stories to ensure clarity and testability.

---

### **User Stories for Airplane Ticket Booking System**

#### **I. Flight Search & Discovery**

1.  **As a traveler, I want to search for flights based on origin, destination, dates, and number of passengers, so that I can find available flights for my trip.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am on the flight search page
        *   **WHEN** I enter "London" as origin, "New York" as destination, a specific departure date, and "2 Adults"
        *   **THEN** I should see a list of available flights matching my criteria.
        *   **AND** the search results should display flight times, airlines, and prices for each option.
        *   **GIVEN** I select "Round Trip"
        *   **WHEN** I provide a return date
        *   **THEN** the search should include both outbound and return flight options.
        *   **GIVEN** I select "Multi-city"
        *   **WHEN** I provide multiple origin/destination pairs and dates
        *   **THEN** the search should find flights for all specified segments.

2.  **As a traveler, I want to filter flight search results by price, airline, number of stops, and departure/arrival times, so that I can quickly narrow down options that best suit my preferences.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I have search results displayed
        *   **WHEN** I select "1 Stop" in the filter options
        *   **THEN** only flights with exactly one stop should be shown.
        *   **WHEN** I set a price range filter (e.g., "$500 - $800")
        *   **THEN** only flights within that price range should be displayed.
        *   **WHEN** I select a specific airline (e.g., "British Airways")
        *   **THEN** only flights operated by British Airways should be visible.

3.  **As a traveler, I want to sort flight search results by price, duration, or departure time, so that I can prioritize the most important criteria for my booking.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I have search results displayed
        *   **WHEN** I choose to sort by "Price (Lowest to Highest)"
        *   **THEN** the flights should be reordered with the cheapest options appearing first.
        *   **WHEN** I choose to sort by "Duration (Shortest to Longest)"
        *   **THEN** flights with the shortest travel time should appear first.

4.  **As a traveler, I want to view detailed information about a selected flight, including layovers, baggage allowance, and aircraft type, so that I can make an informed decision before booking.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I have selected a flight from the search results
        *   **WHEN** I click to view details
        *   **THEN** I should see the full itinerary, including all segments and layover durations.
        *   **AND** I should see the specific baggage allowance (e.g., "1 checked bag, 1 carry-on").
        *   **AND** I should see the type of aircraft operating the flight.

5.  **As a traveler, I want to select different fare options (e.g., Economy, Flexible Economy, Business Class) for a flight, so that I can choose the balance between price and flexibility/amenities.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am viewing a flight option
        *   **WHEN** I see different fare types (e.g., "Basic Economy", "Standard Economy", "Flexible Economy")
        *   **THEN** I should see a clear description of what each fare type includes (e.g., no baggage, changeable, seat selection included).
        *   **WHEN** I select a fare type
        *   **THEN** the total price should update accordingly.

#### **II. Passenger Information & Ancillary Services**

6.  **As a traveler, I want to enter my personal and contact information for all passengers, so that the tickets can be correctly issued.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am on the passenger information page
        *   **WHEN** I enter passenger details (First Name, Last Name, Date of Birth, Gender, Nationality, Passport Number, Expiry Date)
        *   **THEN** the system should validate required fields are filled.
        *   **AND** the system should validate date formats and passport expiry (e.g., cannot be expired).
        *   **WHEN** I enter my contact email and phone number
        *   **THEN** these should be associated with the booking for confirmation and communication.

7.  **As a traveler, I want to add special requests like dietary meals or wheelchair assistance, so that my needs are communicated to the airline.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am entering passenger details
        *   **WHEN** I choose a special meal option (e.g., Vegetarian, Gluten-free)
        *   **THEN** this preference should be saved with the booking.
        *   **WHEN** I indicate the need for wheelchair assistance
        *   **THEN** this assistance request should be clearly added to the booking.

8.  **As a traveler, I want to select additional services like extra baggage, preferred seats, or travel insurance, so that I can customize my travel experience.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am on the ancillaries selection page
        *   **WHEN** I choose to add an extra checked bag
        *   **THEN** the additional cost should be clearly displayed and added to the total.
        *   **WHEN** I view the seat map and select a specific seat (e.g., window, aisle)
        *   **THEN** the chosen seat should be reserved, and any associated fees added to the total.
        *   **WHEN** I choose to add travel insurance
        *   **THEN** the insurance details and cost should be presented and added to the booking total.

#### **III. Payment & Confirmation**

9.  **As a traveler, I want to pay for my flight booking using a secure payment method, so that my tickets can be issued.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I have reviewed my booking summary and total price
        *   **WHEN** I enter valid credit card details (Card Number, Expiry Date, CVV, Cardholder Name)
        *   **THEN** the payment should be processed securely.
        *   **AND** upon successful payment, a confirmation message should be displayed.
        *   **GIVEN** I enter invalid credit card details
        *   **THEN** an appropriate error message should be displayed, and payment should fail.
        *   **WHEN** I select an alternative payment method (e.g., PayPal)
        *   **THEN** I should be redirected to the secure payment gateway for that method.

10. **As a traveler, I want to receive an email confirmation with my booking details and PNR, so that I have a record of my purchase and can manage my trip.**
    *   **Acceptance Criteria:**
        *   **GIVEN** my payment has been successfully processed
        *   **WHEN** the booking is confirmed
        *   **THEN** I should receive an email within 5 minutes containing my booking reference (PNR), full itinerary, passenger names, and total amount paid.
        *   **AND** the email should include information on how to manage my booking.

#### **IV. User Account & Management**

11. **As a new user, I want to register for an account with my email and password, so that I can save my details and manage my bookings.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am on the registration page
        *   **WHEN** I provide a valid email address and a strong password
        *   **THEN** my account should be created successfully.
        *   **AND** I should receive a confirmation email.
        *   **GIVEN** I try to register with an already existing email
        *   **THEN** I should receive an error message indicating the email is already in use.

12. **As a registered user, I want to log in to my account, so that I can access my saved information and past bookings.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I have an existing account
        *   **WHEN** I enter my correct email and password
        *   **THEN** I should be successfully logged in and directed to my dashboard.
        *   **GIVEN** I enter incorrect credentials
        *   **THEN** an error message should be displayed, and I should not be logged in.

13. **As a registered user, I want to view a list of my past and upcoming flight bookings, so that I can keep track of my travel history.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am logged into my account
        *   **WHEN** I navigate to "My Bookings"
        *   **THEN** I should see a clear list of all my confirmed bookings, separated into "Upcoming" and "Past".
        *   **AND** for each booking, essential details like destination, dates, and PNR should be visible.

14. **As a registered user, I want to save passenger details (e.g., name, date of birth, passport info) in my profile, so that I don't have to re-enter them for every new booking.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I am logged in and navigating to my profile
        *   **WHEN** I add new passenger details (e.g., for a family member) and save them
        *   **THEN** these details should be stored securely in my account.
        *   **WHEN** I am making a new booking
        *   **THEN** I should have the option to select saved passenger details to pre-fill the form.

#### **V. System Reliability & Usability**

15. **As a system, I want to detect if flight availability or prices have changed during the booking process, so that users are always presented with accurate information.**
    *   **Acceptance Criteria:**
        *   **GIVEN** a user has selected a flight and proceeds to payment
        *   **WHEN** the price or availability of that flight changes before payment is confirmed
        *   **THEN** the user should be notified of the change and prompted to accept the new price/availability or select another flight.
        *   **AND** the system should prevent the booking from completing with outdated information.

16. **As a user, I want to see clear and actionable error messages when something goes wrong, so that I understand the problem and how to resolve it.**
    *   **Acceptance Criteria:**
        *   **GIVEN** I fail to fill a required field in a form
        *   **THEN** an inline error message should appear next to the field, explaining what is missing.
        *   **GIVEN** a payment fails due to insufficient funds
        *   **THEN** a message like "Payment failed: Insufficient funds. Please check your card details or try another method." should be displayed.