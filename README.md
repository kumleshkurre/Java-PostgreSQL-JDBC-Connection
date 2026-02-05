# Java PostgreSQL Database Connection Project
## 📌 Project Description
---
This project demonstrates how to create a Java application and connect it with a PostgreSQL database using JDBC.
It includes examples of:
- Creating a Java project in Eclipse
- Adding PostgreSQL JDBC driver
- Executing SELECT queries
- Using main method and constructor-based connection

## 🛠️ Tools & Technologies Used
- Java (JDK 8+)
- Eclipse IDE
- PostgreSQL Database
- JDBC (PostgreSQL Driver)

## 📂 Project Setup Steps (Eclipse)
- Step 1: Create Java Project
- Open Eclipse
- Go to File
- Click New
- Select Project
- Choose Java
- Select Java Project
- Enter Project Name
- Press Enter / Finish

## 🗄️ Database Connection Setup (PostgreSQL JDBC)
- Step 1: Download JDBC Driver
- Download PostgreSQL JDBC JAR file from:
👉 https://jdbc.postgresql.org/download/
- Step 2: Add JDBC JAR to Project
- Right click on your Project Folder
- Select Build Path
- Click Configure Build Path
- Go to Libraries
- Select Classpath
- Click Add External JARs
- Select downloaded PostgreSQL JDBC JAR
- Click Apply
- Click Apply and Close
- ✅ After this, Referenced Libraries will be created automatically.

## 📄 Create Java Class File
- Right click on src folder
- Click New
- Select Class
- Enter Class Name
- Check ✔ public static void main(String[] args)
- Click Finish

## ⚠️ Important Note
- Package name and Class name can be same or different
- Database credentials should be correct
- PostgreSQL service must be running

### 🔹 Example 1: Package Name & Class Name Same (SELECT Query)
```js
  package kumleshkurre;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class kumleshkurre {

    public static void main(String[] args) {

        Connection con;
        Statement stmt;     // select query use
        ResultSet rs;      // data store

        try {
            // Database Connection
            con = DriverManager.getConnection(
                "jdbc:postgresql://localhost:5432/your_database_name",
                "your_username",
                "YOUR_PASSWORD"
            );

            System.out.println("Connection Successful");

            // Create Statement
            stmt = con.createStatement();

            // Execute Query
            rs = stmt.executeQuery("SELECT * FROM contact");

            while (rs.next()) {
                System.out.println(
                    rs.getString("name") + " " + rs.getString("mob")
                );
            }

        } catch (Exception e) {
            System.out.println("Error : " + e);
        }
    }
}
```
### 🔹 Example 2: Constructor-Based Connection
- (Package Name & Class Name Different)
```js
package kumleshkurre;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class CSpgconnection {

    Connection con;
    Statement stmt;        // select query use
    ResultSet rs;         // data store

    public static void main(String[] args) {
        new CSpgconnection();   // Object create hote he constructor call hoga
    }

    public CSpgconnection() {        // constructor
        try {
            // Database Connection
            con = DriverManager.getConnection(
                "jdbc:postgresql://localhost:5432/your_database_name",
                "your_username",
                "YOUR_PASSWORD"
            );

            System.out.println("Connection Successful");

            // Create Statement
            stmt = con.createStatement();

            // Execute Query
            rs = stmt.executeQuery("SELECT * FROM contact");

            while (rs.next()) {
                System.out.println(
                    rs.getString("name") + " " + rs.getString("mob")
                );
            }

        } catch (Exception e) {
            System.out.println("Error : " + e);
        }
    }
}
```
## ✅ Output
- Successfully connects to PostgreSQL database
- Fetches data from contact table
- Displays data in console

## 🚀 Future Enhancements
- Use PreparedStatement
- Add INSERT, UPDATE, DELETE operations
- Exception handling improvements
- MVC architecture

  ## 👤 Author
  Kumlesh Kurre
- Java | PostgreSQL | JDBC | Backend Enthusiast

## ⭐ Support
If you like this project, please ⭐ star the repository to support my work!
