# Hospital Manager API

This is a REST API for managing hospital information (Patients, Doctors, and Hospitals). It's built using Spring Boot and connects to a PostgreSQL database.

## Prerequisites

Before you can run this application, you'll need to have the following installed:

*   **Java Development Kit (JDK):** Version 11 or higher.
*   **Maven:** A build automation tool used for managing project dependencies.
*   **PostgreSQL:** A relational database management system.

## Configuration

1.  **Create a PostgreSQL database:** Create a database named `your_database_name` (or a name of your choosing) in your PostgreSQL server.

2.  **Update the `application.properties` file:**  Open the `src/main/resources/application.properties` file and update the following properties with your PostgreSQL database credentials:

    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/your_database_name
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    spring.datasource.driver-class-name=org.postgresql.Driver
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
    spring.jpa.show-sql=true
    ```

    *   Replace `your_database_name`, `your_username`, and `your_password` with your actual PostgreSQL credentials.

## Running the Application

1.  **Clone the repository:**

    ```bash
    git clone <your_repository_url>
    ```

    Replace `<your_repository_url>` with the URL of your GitHub repository.

2.  **Navigate to the project directory:**

    ```bash
    cd HospitalManager
    ```

3.  **Build and run the application using Maven:**

    ```bash
    ./mvnw spring-boot:run
    ```

    or, if you don't have the Maven Wrapper:

    ```bash
    mvn spring-boot:run
    ```

    This will start the Spring Boot application on port 8080 (by default).

## API Endpoints

The API provides the following endpoints for managing hospital data:

*   **/api/patients:**  Manages patient information.
    *   `GET`: Retrieves a list of all patients or a specific patient by ID.
    *   `POST`: Creates a new patient.
    *   `PUT`: Updates an existing patient.
    *   `DELETE`: Deletes a patient.
*   **/api/doctors:** Manages doctor information.
    *   `GET`: Retrieves a list of all doctors or a specific doctor by ID.
    *   `POST`: Creates a new doctor.
    *   `PUT`: Updates an existing doctor.
    *   `DELETE`: Deletes a doctor.
*   **/api/hospitals:** Manages hospital information.
    *   `GET`: Retrieves a list of all hospitals or a specific hospital by ID.
    *   `POST`: Creates a new hospital.
    *   `PUT`: Updates an existing hospital.
    *   `DELETE`: Deletes a hospital.

## Testing the API

You can use tools like `curl` or Postman to test the API endpoints. Here are some examples using `curl`:

*   **Get all patients:**

    ```bash
    curl http://localhost:8080/api/patients
    ```

*   **Create a new patient:**

    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"name": "John Doe", "dob": "1990-01-01", "gender": "Male", "address": "123 Main St", "phoneNumber": "555-1234"}' http://localhost:8080/api/patients
    ```

## Technologies Used

*   Spring Boot
*   Spring Data JPA
*   PostgreSQL
*   Maven

## License

[Your License (e.g., MIT License)] - Replace this with your chosen license.