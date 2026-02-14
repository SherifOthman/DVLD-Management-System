# DVLD Management System - Driving License Department

A Windows desktop application for managing driving license department operations, built to practice 3-tier architecture and complex business workflows in C#.

## Purpose

This project simulates a complete driving license department system, handling everything from person registration through testing, license issuance, renewal, and detention management. It demonstrates how to build a large-scale desktop application with proper architectural separation and complex business rules.

## Architecture

**Three-Tier Structure**:

```
DVLD/                  # Presentation Layer (30+ Windows Forms)
DVLD_Business/         # Business Logic Layer (14 entity classes)
DVLD_DataAccess/       # Data Access Layer (SQL queries with ADO.NET)
```

**Key Design Decisions**:

- Strict separation of concerns across three layers
- Business logic layer validates all operations
- Data access layer uses parameterized queries (SQL injection prevention)
- Presentation layer only handles UI and user input

## Technical Skills Demonstrated

**3-Tier Architecture**:

- Presentation layer communicates only with business layer
- Business layer enforces all business rules
- Data access layer handles all database operations
- Each layer can be modified independently

**Complex Business Workflows**:

- Sequential testing process (Vision → Written → Street)
- License lifecycle management (issue → renew → replace → detain → release)
- Application state machine (New → Completed/Cancelled)
- Automatic deactivation of old licenses when issuing new ones

**Database Design**:

- 14 tables with proper relationships (1-to-many, many-to-many)
- Foreign key constraints for referential integrity
- Stored procedures for complex operations (not used, but supported)
- SQL Server integrated security

**Windows Forms Development**:

- 30+ forms with consistent UI patterns
- User controls for reusable components
- Data binding to display database records
- Form validation and error handling

**Data Access with ADO.NET**:

- SqlConnection for database connectivity
- SqlCommand with parameterized queries
- SqlDataReader for efficient data retrieval
- Transaction handling for multi-step operations

## Implementation Details

**Application Workflow**:

1. Register person with personal information
2. Create application for new driving license
3. Schedule and pass 3 sequential tests:
   - Vision test (must pass to proceed)
   - Written test (must pass to proceed)
   - Street test (must pass to proceed)
4. Issue license automatically after passing all tests
5. Manage license (renew, replace, detain, release)

**Testing System**:

- Each test type has configurable fees
- Tests must be passed in sequence
- Failed tests can be retaken with additional fee
- Test appointments prevent scheduling conflicts
- Complete test history tracking

**License Operations**:

- **Issuance**: Automatic after passing all tests
- **Renewal**: Creates new license, deactivates old one
- **Replacement**: For lost or damaged licenses
- **Detention**: Requires fine payment to release
- **International**: Based on valid local license

**Data Access Pattern**:

```csharp
// Business layer calls data access layer
public static clsPerson Find(int PersonID)
{
    // Data access layer executes SQL query
    return clsPersonData.GetPersonByID(PersonID);
}
```

**Business Rule Example**:

- Cannot issue license without passing all 3 tests
- Cannot renew expired license (must apply as new)
- Cannot detain already detained license
- Must pay fine to release detained license

## Technology Stack

- C# .NET Framework 4.8
- Windows Forms for UI
- SQL Server for database
- ADO.NET for data access
- 3-tier architecture pattern

## What I Learned

**Architectural Benefits**:

- Separation of concerns makes code more maintainable
- Business logic layer prevents invalid operations
- Data access layer centralizes all SQL queries
- Each layer can be tested independently

**Complex Business Logic**:

- State machines help manage entity lifecycles
- Sequential workflows require careful validation
- Business rules must be enforced at multiple levels
- Audit trails are important for tracking changes

**Database Design**:

- Proper relationships prevent data inconsistencies
- Foreign keys enforce referential integrity
- Indexes improve query performance
- Normalized design reduces data redundancy

**Windows Forms Challenges**:

- Managing state across multiple forms is complex
- Data binding simplifies UI updates
- User controls promote reusability
- Validation must happen at both UI and business layers

**ADO.NET Fundamentals**:

- Parameterized queries prevent SQL injection
- Connection pooling improves performance
- DataReader is more efficient than DataSet for read-only data
- Transactions ensure data consistency

**Real-World Patterns**:

- Application types with configurable fees
- Test scheduling with conflict prevention
- License history tracking for auditing
- User authentication with session management

## Project Stats

- 30+ Windows Forms with full functionality
- 14 business entity classes with CRUD operations
- 14 database tables with relationships
- 100+ embedded icons and resources
- Complete 3-tier architecture
- 7 application types (new license, renewal, replacement, etc.)

---

**Learning Focus**: 3-tier architecture, complex business workflows, Windows Forms development, and ADO.NET data access
