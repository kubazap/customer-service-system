# Customer Service System

A web application project written in Java Spring Boot using PostgreSQL and Thymeleaf. The application allows you to manage appointments, customers and employees, and includes a two-step verification mechanism (TOTP).

## How to run the project locally

To run the application locally, follow these steps:

### 1. Start the PostgreSQL server

Make sure the **PostgreSQL** service is running.

### 2. Create the database

Log in to your local PostgreSQL database and create a new database named:

```sql
CREATE DATABASE system_obslugi_klienta;
```

### 3. Set the required environment variables

In your run environment (e.g. IntelliJ IDEA → **Edit Configurations → Environment variables**), set the following variables:

| Environment variable    | Description                                                 |
|-------------------------|-------------------------------------------------------------|
| `SPRING_MAIL_USERNAME`  | SMTP login generated in Brevo (e.g. `user@smtp-brevo.com`)  |
| `SPRING_MAIL_PASSWORD`  | SMTP password generated in Brevo                            |
| `EMAIL_SENDER_EMAIL`    | Verified sender email address (e.g. `contact@yourdomain.com`) |
| `db_username`           | PostgreSQL username (e.g. `postgres`)                       |
| `db_password`           | PostgreSQL user password                                    |

**Example configuration in IntelliJ:**
```
SPRING_MAIL_USERNAME=user@smtp-brevo.com;SPRING_MAIL_PASSWORD=your-smtp-password;EMAIL_SENDER_EMAIL=contact@yourdomain.com;db_username=postgres;db_password=secret
```

### 4. Run the project

Run the project from your IDE (e.g. IntelliJ IDEA) or with Maven:

```bash
./mvnw spring-boot:run
```

The application will be available at:
```
http://localhost:8080
```

### 5. Import the initial data into the database

Import the initial data using the SQL file included in the project:

```
src/main/resources/static/databases/all.sql
```

You can do this, for example, with the `psql` tool in the console:

```bash
psql -U postgres -d system_obslugi_klienta -f path/to/all.sql
```

## Technologies used in the project

- **Spring Boot** – web application framework
- **PostgreSQL** – database
- **Thymeleaf** – HTML template engine
- **Spring Security** – authentication mechanism (with TOTP)
- **Brevo (Sendinblue)** – SMTP email service
- **Bootstrap 4** – frontend
