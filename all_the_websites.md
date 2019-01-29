- The MOOCademy

> creation of the table 'courses'
```sql
CREATE TABLE IF NOT EXISTS courses (
'id_course' INTEGER PRIMARY KEY AUTOINCREMENT,
'title_course' TEXT,
'description_course' TEXT );
```
> creation of the table 'lessons'

```sql
CREATE TABLE IF NOT EXISTS lessons (
'id_lesson' INTEGER PRIMARY KEY AUTOINCREMENT,
'title_lesson' TEXT,
'body_lesson' TEXT,
'course_id' INTEGER NOT NULL,
FOREIGN KEY (course_id) REFERENCES courses(id_course) );
```
- The Hacking Pinterest
> creation of the table create_pins
```sql
CREATE TABLE IF NOT EXISTS create_pins (
'id_pin' INTEGER PRIMARY KEY AUTOINCREMENT,
'url_pin' TEXT);
```
> creation of the table comment_pin
```sql
CREATE TABLE IF NOT EXISTS comment_pin (
'id_comment' INTEGER PRIMARY KEY AUTOINCREMENT,
'title_comment' TEXT,
'pin_id' INTEGER NOT NULL
FOREIGN KEY (pin_id) REFERENCES create_pins(id_pin) );
```
- The Hacking News

> creation of the table message
```sql
CREATE TABLE IF NOT EXISTS message (
'id_message' INTEGER PRIMARY KEY AUTOINCREMENT,
'title_message' TEXT
);
```
> creation of the table users
```sql
CREATE TABLE IF NOT EXISTS users (
	'id_user' INTEGER PRIMARY KEY AUTOINCREMENT,
    'user_name' TEXT,
    'message_id' INTEGER NOT NULL,
    FOREIGN KEY (message_id) REFERENCES message(id_message)
);
```
> creation of the table comment
 ```sql
 CREATE TABLE IF NOT EXISTS users (
	'id_comment' INTEGER PRIMARY KEY AUTOINCREMENT,
    'comment_text' TEXT,
    'message_id' INTEGER NOT NULL,
    FOREIGN KEY (message_id) REFERENCES message(id_message)
);
```
- The Hacking Class
> creation of the table courses

```sql
CREATE TABLE IF NOT EXISTS courses (
	'id_course' INTEGER PRIMARY KEY AUTOINCREMENT,
	'course_name' TEXT
);
```
> creation of the table users

```sql
CREATE TABLE IF NOT EXISTS users (
   'id_user' INTEGER PRIMARY KEY AUTOINCREMENT,
   'user_name' TEXT,
   'course_id' INTEGER NOT NULL,
  	FOREIGN KEY (course_id) REFERENCES courses(id_courses) 
   );
```