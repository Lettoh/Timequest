Réalisé fin 2023, début 2024

Pour faire fonctionner le plugin avec la base de donnée (requise)

Créer le fichier /src/main/java/lettoh/dev/database/Database.java

package lettoh.dev.database;

import java.sql.*;

public class Database { private Connection connection;

public Connection getConnection() throws SQLException 
{

    if(connection != null){
        return connection;
    }

    String url = "DB URL";
    String user = "DB USER";
    String password = "DB USER PASSWORD";

    Connection connection = DriverManager.getConnection(url, user, password);

    this.connection = connection;

    return connection;
}

public void closeConnection() throws SQLException 
{
    this.connection.close();
}
}
