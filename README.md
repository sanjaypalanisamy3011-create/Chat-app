# Chat Application User Database (JDBC)

A console Java app that manages chat users in MySQL using JDBC: register, login, online list, logout, delete.

## Structure
- `schema.sql` – database and `users` table
- `src/DBConnection.java` – JDBC connection (edit URL/user/password)
- `src/UserDAO.java` – CRUD operations with PreparedStatement, salted SHA-256 hashing
- `src/Main.java` – console menu
- `lib/` – put MySQL Connector/J jar here

## Run
1. Run `schema.sql` in MySQL.
2. Download Connector/J (mysql-connector-j-x.x.x.jar) into `lib/`.
3. Set your password in `DBConnection.java`.
4. Compile and run (Java 14+):
   - Windows: `javac -cp ".;lib/*" -d out src/*.java` then `java -cp "out;lib/*" Main`
   - Linux/macOS: `javac -cp ".:lib/*" -d out src/*.java` then `java -cp "out:lib/*" Main`

## Notes
- For production use bcrypt/PBKDF2 instead of plain SHA-256.
- Possible extensions: messages table, GUI, connection pooling (HikariCP).
