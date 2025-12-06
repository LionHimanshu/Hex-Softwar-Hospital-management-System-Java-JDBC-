Hospital-Management-System
A simple Hospital Management System built using Java and MySQL (JDBC). This project allows managing patients, doctors, and appointments from a clean console-based interface. It is designed as a learning project for beginners who want to understand Java + JDBC + MySQL integration.

⭐ Features 👨‍⚕️ Manage Doctors

View all doctors

Check doctor availability by ID

🧑‍🦱 Manage Patients

Add new patients

View patient list

📅 Manage Appointments

Book appointments

Prevent double-booking of doctors

Validate patient & doctor before booking

🖥 Console Interface

Simple, menu-driven CLI for quick testing and learning. 🛠 Technologies Used Technology Purpose Java Core application logic MySQL Database backend JDBC Database connectivity VS Code IDE MySQL Connector/J JDBC driver

Hospital-Management-System/ 
│── src/
│   ├── DBConnection.java 
│   ├── HospitalManagement.java
│   ├── Patients.java │ ├── Doctors.java │
│  
│── lib/
│   └── mysql-connector-j-8.x.x.jar 
│ │── README.md

Database Setup (MySQL)

1. Create Database
   CREATE DATABASE hospital; USE hospital;

2. Create Table
   Patients Table
    CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
    );

 Doctors Table 
 CREATE TABLE doctors (
 id INT AUTO_INCREMENT PRIMARY KEY, 
 name VARCHAR(255) NOT NULL,
 specialty VARCHAR(100) NOT NULL
 );

Appointments Table 

CREATE TABLE appointments (
id INT AUTO_INCREMENT PRIMARY KEY,
patient_id INT NOT NULL,
doctor_id INT NOT NULL,
appointment_date DATE NOT NULL, 
FOREIGN KEY (patient_id) REFERENCES patients(id),
FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);

How to Run the Project

Download or clone the repository 
git clone https://github.com/yourusername/hospital-management-system.git

Add MySQL JDBC Driver
Go to lib/
Add this file:
mysql-connector-j-8.x.x.jar Right-click → Add to Build Path (VS Code / Eclipse).

Update MySQL credentials in DBConnection.java private static final String URL = "jdbc:mysql://localhost:3306/hospital?useSSL=false"; private static final String USER = "root"; // your MySQL username private static final String PASS = "password"; // your MySQL password'

Compile javac -cp ".;lib/mysql-connector-j-8.x.x.jar" src/*.java

Run java -cp ".;lib/mysql-connector-j-8.x.x.jar;src" HospitalManagement

🎯 Learning Objectives

Understand Java–MySQL connectivity

Learn PreparedStatement, ResultSet, and JDBC queries

Practice CRUD operations

Build modular Java applications

🚀 Future Enhancements

Add update/delete options for patients & doctors

Add user authentication

Add a GUI using JavaFX or Swing

Add REST APIs using Spring Boot

Add advanced appointment scheduling system

🙌 Acknowledgment

This project was developed by Himanshu Singh as a personal learning project to improve Java and MySQL skills. Special thanks to online Java learning resources and community tutorials that helped in understanding JDBC concepts.

👤 Author

Himanshu Singh Java Developer | Student | Tech Learner
