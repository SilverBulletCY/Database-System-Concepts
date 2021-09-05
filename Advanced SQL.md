**JDBC**：

```java
import java.sql.*;

public class jdbcDemo {
    static final String JDBC_DRIVER = "com.mysql.cj.jdbc.Driver";
    static final String DB_URL = "jdbc:mysql://localhost:3306/test?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC";

    static final String USER = "root";
    static final String PASSWORD = "******";

    public static void main(String[] args) {
        Connection conn = null;
        Statement stmt = null;
        try {
            Class.forName(JDBC_DRIVER);

            System.out.println("连接数据库...");
            conn = DriverManager.getConnection(DB_URL, USER, PASSWORD);

            PreparedStatement pStmt = conn.prepareStatement("insert into instructor values(?,?,?,?)");
            pStmt.setString(1, "88877");
            pStmt.setString(2, "Perry");
            pStmt.setString(3, "Finance");
            pStmt.setInt(4, 125000);
            pStmt.executeUpdate();


            System.out.println("实例化Statement对象...");
            stmt = conn.createStatement();
            String sql;
            sql = "select ID,name from instructor";
            ResultSet rs = stmt.executeQuery(sql);

            while (rs.next()) {
                String id = rs.getString("ID");
                String name = rs.getString("name");

                System.out.println("ID:" + id + ",name:" + name);
            }
            rs.close();
            stmt.close();
            conn.close();
        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        } finally {
            try {
                if (stmt != null) stmt.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
            try {
                if (conn != null) conn.close();
            } catch (SQLException throwables) {
                throwables.printStackTrace();
            }
        }
        System.out.println("Finished!");
    }
}

```