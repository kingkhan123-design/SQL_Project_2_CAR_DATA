# SQL_Project_2_CAR_DATA

# 🚗 Car Dataset SQL Project

This project features a relational database system built to analyze and manage car-related data using SQL. It includes table definitions, insert scripts for 200 sample records, and SQL queries ranging from intermediate to complex level.

---

## 📚 Dataset Overview

The dataset is structured into two related tables:

### 🔧 Table 1: `CarInfo`

Holds general information about each car.

| Column Name | Data Type     | Description                           |
|-------------|---------------|---------------------------------------|
| CarID       | INT (PK)      | Unique identifier for each car        |
| Brand       | VARCHAR(50)   | Manufacturer brand (e.g., Toyota)     |
| Model       | VARCHAR(50)   | Car model name                        |
| Year        | INT           | Manufacturing year                    |
| BodyType    | VARCHAR(30)   | Type of car (e.g., Sedan, SUV)        |
| Price       | DECIMAL(10,2) | Price in INR                          |

---

### 🔧 Table 2: `CarSpecs`

Contains technical specifications linked to each car.

| Column Name  | Data Type      | Description                          |
|--------------|----------------|--------------------------------------|
| SpecID       | INT (PK)       | Unique ID for each spec entry        |
| CarID        | INT (FK)       | Foreign key referencing `CarInfo`    |
| FuelType     | VARCHAR(20)    | Fuel type (Petrol, Diesel, etc.)     |
| Transmission | VARCHAR(20)    | Manual or Automatic                  |
| Horsepower   | INT            | Horsepower rating                    |
| EngineSize   | DECIMAL(3,1)   | Engine displacement in liters        |
| Mileage      | INT            | Kilometers driven                    |

> ✅ All 200 records in `CarSpecs` use `'Petrol'` as the `FuelType`.

---

## 📁 Files Included

- `create_tables.sql` – SQL to create both tables
- `carinfo_insert.sql` – Insert statements for 200 car records
- `carspecs_insert.sql` – Insert statements for matching 200 specs
- `car_queries.sql` – 10+ SQL queries (medium to complex level)

---

## 🔍 SQL Query Topics Covered

### 🧠 Medium Level Queries
- Average price per body type
- Join queries for fuel type and horsepower
- Cars above average horsepower
- Oldest car in the dataset
- Average mileage by fuel type

### 🔎 Complex Queries
- Cars with price above body type average
- Top 3 cars by horsepower
- Count of cars by brand
- Transmission type filters
- Car models with engine size > 2.0L and automatic transmission

---

## 💡 Sample Query

**Top 3 Cars by Horsepower:**
```sql
SELECT ci.Brand, ci.Model, cs.Horsepower
FROM CarInfo ci
JOIN CarSpecs cs ON ci.CarID = cs.CarID
ORDER BY cs.Horsepower DESC
LIMIT 3;
