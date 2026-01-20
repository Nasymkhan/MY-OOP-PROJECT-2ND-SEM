# Chrome Dino – OOP Project (BSSE 2nd Semester)

Author: Naseem Khan  
Semester: BSSE, 2nd Semester  
Project Type: Java OOP (Swing)

## Overview
Desktop game recreating the Chrome T‑Rex runner. Clean OOP structure with UI, gameplay components, and a simple authentication layer (file or MySQL).

## Screenshots
- Add images to the screenshots folder and they will display here:
- <img width="401" height="251" alt="image" src="https://github.com/user-attachments/assets/2509bd8a-a986-4d4f-b474-0be2270e969d" />

-<img width="406" height="257" alt="image" src="https://github.com/user-attachments/assets/26a134e2-193d-4e95-81c0-b2e79e6bcf9a" />

-<img width="778" height="487" alt="image" src="https://github.com/user-attachments/assets/1fc2ed69-9ed6-4472-9990-f1e19859646a" />

- <img width="786" height="494" alt="image" src="https://github.com/user-attachments/assets/c90bfec8-d300-4968-8934-9224b658ee26" />


## Features
- Playable runner with jump, collision, score, best score
- Cheat codes: `hack` to go fast and invincible, `off` to return and save best
- Login and Create Account (Gmail emails), Admin panel (create/delete users)
- Storage: `users.db` file or `DINO` MySQL DB via XAMPP

## Requirements
- Java 8+ (JDK)
- Optional: XAMPP MySQL and MySQL Connector/J (for DB mode)

## Run (File Storage)
```bash
javac utility\Resource.java components\Dino.java components\Ground.java components\Obstacles.java GamePanel.java UserInterface.java auth\AuthDialog.java auth\AdminPanel.java auth\User.java auth\UserRepository.java auth\FileUserRepository.java auth\MySQLUserRepository.java auth\UserStore.java
java UserInterface
```

## Run (MySQL via XAMPP)
1. Create DB and table:
   - In phpMyAdmin → Import → pick `db_init.sql` → Execute
2. Copy `db.properties.example` to `db.properties` and keep:
   - `url=jdbc:mysql://localhost:3306/DINO?useSSL=false&serverTimezone=UTC`
   - `user=root`
   - `password=`
   - `table=users`
3. Launch with Connector/J:
```bash
java -cp .;C:\path\to\mysql-connector-j-<ver>.jar UserInterface
```

## Controls
- Space: start / jump / reset (after game over)
- Type `hack`: invincible fast mode
- Type `off`: normal mode, best score saved

## Admin
- In login: use email `admin` and password `admin` OR press the Admin button
- Manage users: create and delete; view best scores

## Structure
- `UserInterface`: main window, loads `GamePanel`
- `GamePanel`: loop, render, input handling
- `components/`: `Dino`, `Ground`, `Obstacles`
- `auth/`: `AuthDialog`, `AdminPanel`, `UserStore`, repositories
- `utility/Resource`: image loader

## Notes
- Passwords: plaintext for demo simplicity; use hashing + salting in production
- Email must end with `@gmail.com`
- Mobile must be `03xxxxxxxxx` or `+923xxxxxxxxxx`

## License
Personal/academic use. You can fork and improve for learning.
