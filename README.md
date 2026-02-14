# DVLD - Driving License Management System

## 🚀 Overview

Windows desktop application for managing driving license department operations. Handles person registration, license applications, testing (vision, written, street), license issuance, renewals, replacements, and detention management.

Built to practice 3-tier architecture and complex business workflows in C#.

---

## 🏗 Architecture

**OOP principles applied:** Encapsulation (private fields with public properties), inheritance (base entity classes), polymorphism (different application types share common interface).

**Separation of concerns:** Three distinct layers - Presentation (Windows Forms), Business Logic (entity classes with validation), Data Access (SQL queries with ADO.NET). Each layer has a single responsibility.

**Class design approach:** Entity classes represent database tables (Person, Application, License, Test). Each entity has CRUD methods. Business layer validates operations before calling data access layer. Data access layer uses parameterized queries to prevent SQL injection.

---

## 🧠 Technical Concepts Demonstrated

**Encapsulation:** Private fields with public properties. Business logic hidden inside entity classes. Data access details abstracted from business layer.

**Inheritance:** Base classes for common functionality. Application types inherit from base Application class. License types inherit from base License class.

**Polymorphism:** Different application types (new license, renewal, replacement) handled through common interface. Test types (vision, written, street) share common test structure.

**File/database handling:** ADO.NET for database operations (SqlConnection, SqlCommand, SqlDataReader). Parameterized queries for security. Transaction handling for multi-step operations. Image storage for person photos and license documents.

---

## 🧠 What I Learned

**3-tier architecture enforces discipline:** Presentation layer cannot directly access database. Business layer validates all operations. Data access layer centralizes SQL queries. This separation makes code maintainable and testable.

**Complex workflows require state management:** License application follows strict sequence (register person → create application → pass 3 tests → issue license). State machines help manage entity lifecycles. Business rules must be enforced at multiple levels.

**OOP fundamentals in practice:** Encapsulation protects data integrity. Inheritance reduces code duplication. Polymorphism enables flexible design. Proper class design makes complex systems manageable.

**Database relationships matter:** Foreign keys enforce referential integrity. Proper relationships prevent data inconsistencies. Normalized design reduces redundancy. Understanding SQL is essential for data-driven applications.

---

## Technology Stack

C# .NET Framework 4.8, Windows Forms, SQL Server, ADO.NET, 3-tier architecture

---

## License

MIT
