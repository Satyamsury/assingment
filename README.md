Java program of CRUD oprations
# create a table into sql
package CRUD;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class CreateTable {

 
   static final String DB_URL = "jdbc:mysql://localhost/assingment";
   static final String USER = "root";
   static final String PASS = "Sa1Ty9Am99";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
          String sql = "CREATE TABLE assingment " +
        		  "(id INTEGER not NULL, " +
                  " name VARCHAR(30), " + 
                  " dob VARCHAR(30), " + 
                  " doj VARCHAR(30), " + 
                  " PRIMARY KEY ( id ))"; 
         stmt.executeUpdate(sql);
         System.out.println("Created table in assingment database...");   	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
# Insert student data into Student table
package CRUD;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class Insert 
 {
   static final String DB_URL = "jdbc:mysql://localhost/assingment";
   static final String USER = "root";
   static final String PASS = "Sa1Ty9Am99";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         // Execute a query
        System.out.println("Inserting records into the table assingment...");                    
         String sql = "INSERT INTO assingment VALUES (567, 'anfss', '10/05/1998', 12/01/2020)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment  VALUES (45, 'Saftyam', '12/04/1999', 25/01/2017)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES (333, 'ffmfd', '22/13/1999', 28/01/2019)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES(4022, 'Sumifx nt', '11/01/1998', 24/11/2019)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES(512, 'mansefnsnasi', '11/05/1998', 24/11/2019)";
         stmt.executeUpdate(sql);
         System.out.println("Insert records into the table  assingment...");  	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
# Update student data into Student table
package CRUD;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class Insert 
 {
   static final String DB_URL = "jdbc:mysql://localhost/assingment";
   static final String USER = "root";
   static final String PASS = "Sa1Ty9Am99";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
         // Execute a query
        System.out.println("Inserting records into the table assingment...");                    
         String sql = "INSERT INTO assingment VALUES (567, 'anfss', '10/05/1998', 12/01/2020)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment  VALUES (45, 'Saftyam', '12/04/1999', 25/01/2017)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES (333, 'ffmfd', '22/13/1999', 28/01/2019)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES(4022, 'Sumifx nt', '11/01/1998', 24/11/2019)";
         stmt.executeUpdate(sql);
         sql = "INSERT INTO  assingment VALUES(512, 'mansefnsnasi', '11/05/1998', 24/11/2019)";
         stmt.executeUpdate(sql);
         System.out.println("Insert records into the table  assingment...");  	  
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}

# Delete student data from Student table
package CRUD;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Updates{
   static final String DB_URL = "jdbc:mysql://localhost/assingment";
   static final String USER = "root";
   static final String PASS = "Sa1Ty9Am99";
   static final String QUERY = "SELECT id, name FROM assingment";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {		      
    	  String sql = "UPDATE assingment " +
    	            "SET id = 30 WHERE id in (25)";
         stmt.executeUpdate(sql);
         ResultSet rs = stmt.executeQuery(QUERY);
         while(rs.next()){
            //Display values
            System.out.print("ID: " + rs.getInt("id"));
            System.out.print(", name: " + rs.getString("name"));
            
    
         }
         rs.close();
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
# Get a list of all students

package CRUD;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Show {


   static final String DB_URL = "jdbc:mysql://localhost/assingment";
   static final String USER = "root";
   static final String PASS = "Sa1Ty9Am99";
   static final String QUERY = "SELECT id, name, dob, doj FROM assingment";

   public static void main(String[] args) {
    
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
         ResultSet rs = stmt.executeQuery(QUERY);
      ) {		      
         while(rs.next()){
            
            System.out.print("ID: " + rs.getInt("id"));
            System.out.print(", name: " + rs.getString("name"));
            System.out.print(", dob: " + rs.getString("dob"));
            System.out.println(", doj: " + rs.getString("doj"));
         }
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
# Get one student information depending on the student id filter.
package CRUD;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Serach_by_id {

       static final String DB_URL = "jdbc:mysql://localhost/assingment";
	   static final String USER = "root";
	   static final String PASS = "Sa1Ty9Am99";
	   static final String QUERY = "SELECT * FROM assingment where id = 567";

	   public static void main(String[] args) {
	    
	      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
	         Statement stmt = conn.createStatement();
	         ResultSet rs = stmt.executeQuery(QUERY);
	      ) {		      
	         while(rs.next()){
	            
	            System.out.print("ID: " + rs.getInt("id"));
	            System.out.print(", name: " + rs.getString("name"));
	            System.out.print(", dob: " + rs.getString("dob"));
	            System.out.println(", doj: " + rs.getString("doj"));
	         }
	      } catch (SQLException e) {
	         e.printStackTrace();
	      } 
	   }
	}


