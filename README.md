# 🚗 DVLD Management System - Driving License Department

> **Windows Forms Desktop Application** for complete driving license department operations with 3-tier architecture

## 🔗 **Live Demo**

- **📸 Screenshots**: [View Application Screenshots](images/)
- **💾 Database**: SQL Server backup file included (Database.bak)
- **🖥️ Platform**: Windows Desktop Application (.NET Framework 4.8)

## 🎯 **What This Project Is**

A fully functional desktop application for managing Driving & Vehicle License Department operations. Built with C# Windows Forms using 3-tier architecture, it handles the complete lifecycle from person registration through testing, license issuance, renewal, and detention management.

## 🛠️ **Technology Stack**

| Technology                | Purpose                            |
| ------------------------- | ---------------------------------- |
| **C# .NET Framework 4.8** | Core application development       |
| **Windows Forms**         | Desktop user interface (30+ forms) |
| **SQL Server**            | Database with integrated security  |
| **ADO.NET**               | Data access with SqlClient         |

## ✅ **Key Features Implemented**

### **Core Management**

- ✅ **People Management** - Complete CRUD with personal info, nationality, images
- ✅ **User Authentication** - Login system with session management and "Remember Me"
- ✅ **Driver Management** - Driver records with license history tracking

### **Application System (7 Types)**

- ✅ New Driving License, Renew License, Replace Lost/Damaged License
- ✅ Release Detained License, International License, Retake Test
- ✅ Status tracking (New, Cancelled, Completed) with fee management

### **Testing System**

- ✅ **3 Sequential Tests** - Vision → Written → Street (must pass all)
- ✅ Test appointment scheduling with results recording
- ✅ Retake support and complete test history

### **License Operations**

- ✅ **License Issuance** - Automatic creation after passing all tests
- ✅ **License Management** - Renewal, replacement, detention, and release
- ✅ **International Licenses** - Based on valid local licenses
- ✅ **Expiration Tracking** - Validity management with class-based periods

## 🏗️ **Architecture**

**Three-Tier Structure:**

- **Presentation** (DVLD) - 30+ Windows Forms with complete UI
- **Business Logic** (DVLD_Buisness) - 14 core entities with full CRUD
- **Data Access** (DVLD_DataAccess) - Parameterized SQL queries

**Key Workflows:**

1. Person Registration → Application → 3 Tests → License Issuance
2. License Renewal/Replacement with automatic old license deactivation
3. License Detention with fine fees → Release with application workflow

## 💾 **Database**

**14 Core Tables:** People, Users, Drivers, Applications, Licenses, Tests, etc.
**Connection:** SQL Server with integrated security (configurable in clsDataAccessSettings.cs)

## 🚀 **Quick Start**

1. Restore Database.bak to SQL Server
2. Update connection string in clsDataAccessSettings.cs
3. Build solution in Visual Studio
4. Run application and login with database credentials

## 📊 **Project Stats**

- **30+ Forms** with complete functionality
- **14 Business Classes** with full CRUD operations
- **14 Database Tables** with proper relationships
- **100+ Icons** embedded in resources
- **Complete 3-tier architecture** with proper separation

---

**Part of:** Programming Advices Course - Full Real Project by Mohamed AbouHadhood
