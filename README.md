# WEB-PROGRAMMING-PROJECT-
YMCA Sierra Leone Web Portal
============================

A membership web portal for YMCA Sierra Leone, built with PHP and MySQL. It expands my Assignment 1 login system into a full platform with member profiles, events, learning resources, a community forum and an admin panel.

This is an academic project for DCOMP207 Web Programming at Limkokwing University of Creative Technology, Sierra Leone. It is not the official YMCA Sierra Leone website.

About
-----

YMCA Sierra Leone was established in 1912 and works from 32 Fort Street, Freetown. It supports young people through skills training, livelihoods and community programmes. This portal lets members register, follow their training, join events, use learning materials and connect with mentors, while administrators manage the platform.

Features
--------

- User registration and login with password hashing and sessions
- Separate access for members and administrators
- Member dashboard with training progress, upcoming events and resources
- Profile page with picture upload
- Events and workshops with registration and participation tracking
- Resource library with downloads
- Community forum and mentor matching
- Admin panel for managing users, content and events, with reports

Some features are still being built. See the Project Status section below.

Tech Stack
----------

- PHP 8
- MySQL / MariaDB
- HTML5 and CSS3
- JavaScript (no frameworks)
- XAMPP and phpMyAdmin for local development

Getting Started
---------------

Requirements:

- XAMPP (Apache, PHP, MySQL)
- A web browser

Installation:

1. Clone the repository:

   ```bash
   git clone https://github.com/Alpheous10/<repo-name>.git
   ```

2. Copy the project folder into your XAMPP htdocs folder.

3. Start Apache and MySQL from the XAMPP Control Panel.

4. Open http://localhost/phpmyadmin and create a database called ymca_sl_db.

5. Import database/ymca_sl_db.sql into that database.

6. Open includes/db.php and check the connection settings:

   ```php
   $host = 'localhost';
   $db   = 'ymca_sl_db';
   $user = 'root';
   $pass = '';
   ```

7. Visit http://localhost/ymca-sl-portal/ in your browser.

Making an admin account:

Register a normal account, then run this in the phpMyAdmin SQL tab:

```sql
UPDATE users SET role = 'admin' WHERE email = 'your-email@example.com';
```

Log out and log in again for the change to apply.

Project Structure
-----------------

```
ymca-sl-portal/
|-- index.php
|-- signup.php
|-- login.php
|-- logout.php
|-- dashboard.php
|-- profile.php
|-- events.php
|-- resources.php
|-- community.php
|-- mentorship.php
|-- style.css
|-- includes/       - database connection, header, footer, auth helpers
|-- assets/         - logo and images
|-- uploads/        - profile pictures
|-- admin/          - admin panel pages
`-- database/       - SQL schema and sample data
```

Security
--------

- Passwords are hashed with password_hash() and checked with password_verify()
- All database queries use prepared statements
- Output is escaped with htmlspecialchars()
- The session ID is renewed at login with session_regenerate_id()
- Logout destroys the session and clears the cookie
- Admin pages check the user's role on the server

Project Status
--------------

Done: registration, login, logout, basic dashboard.
In progress: profiles, events, resources, community, mentorship, admin panel
