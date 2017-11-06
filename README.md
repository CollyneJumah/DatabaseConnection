
# DatabaseConnection
Java Database Connection
//import the following 

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.Statement;
import javax.swing.JOptionPane;

/**
 *
 * @author CollyneJumah
 */
public class dbConnect {
//make connections public by using a public access modifier
    Connection conn=null;
    ResultSet rs;
    Statement st;
    PreparedStatement pst= null;
    
   //create a method fo the connection
  public void Connect(){
      try{
            String dbname="your database name";// enter your database name created
            String pass="";   //this specifies the password field which should be empty
            String username="root"; //username 
            String Url="jdbc:mysql://localhost:3306/";  // specifies the url connection,hosting local with port 3306 of your server
            String Drivers="com.mysql.jdbc.Driver";
            
            Class.forName(Drivers);
            conn=DriverManager.getConnection(Url+dbname,username,pass);
            JOptionPane.showMessageDialog(null,"Connected");
      
      }catch(Exception ex){
          JOptionPane.showMessageDialog(null, ex);
      }
  
  }
    public static void main(String[] args) {
        dbConnect db= new dbConnect();
        db.Connect();
        
    }
