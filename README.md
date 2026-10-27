# SQL Server: Hospital Database and Restaurant Ratings Analysis

Two T-SQL projects from my MSc Data Science at the University of Salford: one designs a database from scratch, the other analyses an existing one.

## 1. Hospital database — `01_hospital_database.sql`

Designed and built a hospital records database in SQL Server, then wrote the queries, procedures and automation a hospital would need.

- **Schema:** 6 related tables (Patients, Department, Doctor, PendingAppointment, Appointment, Medical_Records) with primary and foreign keys, `UNIQUE` and `CHECK` constraints, and identity columns
- **Data rules:** a constraint that stops appointments being booked in the past; email format validation
- **Stored procedures:** search prescriptions by medicine name (newest first), update a doctor's details, clear out completed appointments
- **Table-valued function:** diagnoses and allergies for every patient with an appointment today
- **View:** every past and upcoming appointment with doctor, specialty, department and patient feedback
- **Triggers:** a cancelled appointment becomes available again; past appointments move automatically from pending to completed
- **Security:** a `doctors` role with access to medical records and appointments, and a separate role for doctors who have left

All patient and doctor data in the script is made up.

## 2. Restaurant ratings analysis — `02_restaurant_ratings_analysis.sql`

Analysed a consumer, restaurant, cuisine and ratings dataset.

- Added foreign keys to link ratings, consumers, restaurants and cuisines
- Compared low-rated Mexican and Italian restaurants with `GROUP BY` on a join
- Found the average age of consumers who gave a zero service rating
- Ranked restaurants by the food rating from the youngest consumer, using a subquery
- Wrote a stored procedure that adjusts service ratings for restaurants with parking
- Used `EXISTS` and `IN` subqueries, system functions, and `GROUP BY ... HAVING ... ORDER BY` to find franchise restaurants, engaged consumers, the most-rated restaurant and the most common cuisines

## Run it

Open either script in SQL Server Management Studio (SSMS) or Azure Data Studio and run it top to bottom. The hospital script creates its own database and sample data. The restaurant script expects the four source tables (`consumers`, `restaurants`, `restaurant_cuisines`, `ratings`) to be imported into `FoodserviceDB` first.

**Skills:** T-SQL · database design · joins · subqueries · stored procedures · functions · views · triggers · role-based access
