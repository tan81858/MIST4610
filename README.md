# Group 5 MIST 4610 Group Project 1

## Team Name:
62755 Group 5

## Team Members:
1. Armaan Bhasin [@armaanbhasin](https://www.github.com/taralbpatel)
2. Colby Cannizzaro [@colbycannizzaro](https://github.com/colbycannizzaro/MIST4610GroupProject1)
3. Evan Liu [@evanliu](https://github.com/evanl0l/4610)
4. Theresa Nguyen[@theresaanguyen](https://www.github.com/theresaanguyen/MIST4610)
5. Allison Ramirez Diaz [@allisonramirezdiaz](https://www.github.com/quoysimpson)

## Scenario Description:
The UGA Department of Recreational Sports in the Division of Student Affairs wants to create a database that keeps track of information about the various sports sessions offered, the staff that run the activities, and the clients that wish to participate in these activities. 

They wish to track the staff that work at Recreational Sports. They would like to store information about a staff member such as their name, email address, and phone number. A staff member can be an instructor or a fitness monitor for multiple classes. 

Each staff member also has at least one certification. The Department would like to store information about the certification name and a description of the certification. They would also like to know what certifications each staff member has obtained, the date it was obtained, and the expiration date for that certification.

The Department of Recreational Sports has a variety of classes to offer to clients at UGA. They would like to keep track of the types of activities offered for a session and the type of activity it is. They would also like to keep information about the start and end times for each session, the day of the week that it occurs on, the semester it is offered, and the location of the session. A session can be either a group or small group–a small group session is offered quarterly. Each session also has an instructor responsible for a specific class and a fitness monitor that overlooks a class. They also need to track how many clients attend each session.

In addition to group sessions, Recreational Sports also offers personal training sessions. Each session is personalized, so they would like to track the session date, start time, and end time for each session. An instructor can teach many personal training sessions and a client can sign up for multiple sessions.

The Department of Recreational Sports has many different clients that sign up for the activities that they offer. They would like to store information about a client such as their name, email, and phone number. Recreational sports are offered to all types of clients such as students, faculty, and alumni/UGA affiliates. Based on the type of client they are, a client will pay a different amount according to the package type they choose to purchase. For group, small group, and personal training sessions; there is a fixed price for the 3 standard types of clients.

On certain occasions, there is a discount that is applicable to group session packages. The Department of Recreational Sports offers an early semester discount that takes 25% the original price for all types of group packages. Halfway through the semester, the department also offers a 50% discount on the original price for all types of group packages.



## Data Model:
<img width="626" height="427" alt="image" src="https://github.com/user-attachments/assets/b98b5089-0cb8-4408-a20f-e3474e4e2727" />

There is a M-M relationship between staff and certifications–the associative entity created is certifications_obtained. A staff can have many certifications and a certificate can be obtained by many individuals. There is a 1-M non-identifying relationship between staff and class_type. A staff can teach multiple classes and a class has one default instructor(staff). There is a 1-M relationship between staff and class_session; a staff can be an instructor for many classes. Another 1-M relationship between staff and class_session shows that a staff can also be a fitness monitor for many classes. Lastly, there is a 1-M identifying relationship between staff and pt_session showing that a staff member can be an instructor for many personal training sessions. There is also a 1-M identifying relationship between pt_session and client. A personal training session can only be created if an instructor and client schedule the session.
Class_session has a 1-1 identifying relationship with class_type; a sports session is identified based on the type of class it is. There is also a M-M identifying relationship between class_session and client–the associative entity between the two is class_attendance. The records of class attendance is dependent on the type of class a session is and the number of clients that attend each session. 



## Data Dictionary:
<img width="679" height="281" alt="image" src="https://github.com/user-attachments/assets/bbd80e1c-6e77-43ef-8048-802814ea3224" />

<img width="673" height="459" alt="image" src="https://github.com/user-attachments/assets/8c85b006-a72f-4933-b1b8-1108af6fcc98" />

<img width="668" height="249" alt="image" src="https://github.com/user-attachments/assets/25bcfd71-0021-49d6-97b2-48c8abc8b4c1" />

<img width="727" height="526" alt="image" src="https://github.com/user-attachments/assets/76a6ed39-bc8b-493e-b0ec-62e0f7be7fb4" />

<img width="441" height="766" alt="image" src="https://github.com/user-attachments/assets/24d8a87a-f4a6-461b-86eb-0142eb4f15d0" />

<img width="709" height="698" alt="image" src="https://github.com/user-attachments/assets/c7090a04-82b5-4fe0-859f-5248d6f274ec" />

<img width="663" height="318" alt="image" src="https://github.com/user-attachments/assets/7c2800ae-bad6-46df-aeb9-03076a97e07f" />

<img width="685" height="314" alt="image" src="https://github.com/user-attachments/assets/a783ec91-a925-483e-9451-40dcf4c1279f" />

<img width="669" height="206" alt="image" src="https://github.com/user-attachments/assets/f643f94b-abae-4d7a-950a-23edc93a3568" />

<img width="673" height="741" alt="image" src="https://github.com/user-attachments/assets/630a22b4-e2da-472f-9e12-d4ace11abed6" />

<img width="680" height="295" alt="image" src="https://github.com/user-attachments/assets/92d25512-20e6-423e-ba0a-4dedd828ead2" />

<img width="657" height="541" alt="image" src="https://github.com/user-attachments/assets/543d8720-7237-4dd9-9c64-e17c35bd9adb" />

<img width="672" height="185" alt="image" src="https://github.com/user-attachments/assets/630c3081-9734-43e1-a765-1094480328f3" />

<img width="660" height="336" alt="image" src="https://github.com/user-attachments/assets/786ec467-bde3-4238-a80e-d81467ec5a15" />

## Queries:
USE ns_F25MIST4610_62755_Group5;

### Simple
<img width="797" height="610" alt="image" src="https://github.com/user-attachments/assets/a25f7984-6d71-4ce2-814d-4994664e89e2" />

1. List the class types offered.

<img width="627" height="219" alt="image" src="https://github.com/user-attachments/assets/2db468af-b94b-4c65-a3cc-c60749450b1e" />


This query provides a summary of the different activity categories that are offered by the Department of Recreational Sports, making it quick for a manager to observe.

2. List all client information.

<img width="625" height="302" alt="image" src="https://github.com/user-attachments/assets/501a27b9-1ea7-41d1-bb48-809965d05c0f" />


This query provides the necessary information about the clients of Recreational Sports that a manager would need to store.

3. List classes on a Tuesday in the afternoon (12pm–7pm).

<img width="626" height="315" alt="image" src="https://github.com/user-attachments/assets/d082b9c5-c455-43cd-aefb-b58bcfdf0c69" />

From a managerial perspective, this query helps identify which classes are scheduled in the afternoon on Tuesdays. Managers can use this to balance instructor workloads, allocate resources and ensure classes are spread evenly throughout the day.

4. List average package prices of clients that attend more than five classes a week.

<img width="626" height="312" alt="image" src="https://github.com/user-attachments/assets/7bbb3f2f-d9a0-4c85-8c93-8ceecb0499da" />

This query provides important information about clients who attend a higher number of classes per week. This allows for a manager to 

### Complex

5. List the contact information including name, number, and email of all staff that have the ACE certification.

<img width="625" height="234" alt="image" src="https://github.com/user-attachments/assets/d3f2da61-e57a-4b14-b459-702e0165072f" />

This query lists information for any staff member that has an ACE certification, which will be useful from a managerial perspective to identify specific staff members needed for classes requiring the ACE certification. This query can also be edited to identify staff members with other certifications. 

6. List all clients who have come to more than 5 group fitness class.

<img width="624" height="243" alt="image" src="https://github.com/user-attachments/assets/4f03f2fe-f6e2-4633-93c8-caaf793e1a26" />

This query is helpful from a managerial perspective to identify repeat clients for group fitness classes. This can also provide insight of what classes has a greater amount of client interest, which can help determine what classes to keep or modify for the next semester.

7. List all students who have taken a morning yoga class and morning cycle class before.

<img width="625" height="162" alt="image" src="https://github.com/user-attachments/assets/b05eab44-a651-430c-8f4e-772413f926c1" />

From a managerial perspective, UGA Recreational Sports likes to see which classes are popular among students to know if they are worth having. This query returns the number of students that attended cycling classes on Thursdays.  

8. List the client who attended both yoga sessions on September 20th, 2025.

<img width="626" height="194" alt="image" src="https://github.com/user-attachments/assets/c6734187-d568-4d4e-945b-338f3c0cd5d6" />

From a managerial perspective, this query helps us identify highly engaged clients who attend multiple sessions of the same activity in one day. We wanted to see if there were any clients committed enough to attend two sessions in one day.

9. List the most active client's based of attendance who have attended to more than 3 classes.

<img width="625" height="309" alt="image" src="https://github.com/user-attachments/assets/66106007-ba47-44d5-96e1-3460abf8db71" />

From a managerial perspective, UGA Recreational Sports can use this query to identify highly active clients, as frequent attendance predicts stronger retention. This helps managers target loyalty efforts and encourage continued engagement.

10. List the instructor's name, the number of sessions, the date the session starts and the client's names based on the class being in Studio A.

<img width="625" height="313" alt="image" src="https://github.com/user-attachments/assets/780fbaa6-0215-4563-8505-f47deb7aae60" />

This query can be used to identify information on a specific class session as long as the studio is A. This can also be changed to identify information on other studios.
















## Database Information: 
1. Name of the database: ns_F25MIST4610_62755_Group5
2. Each query has been bookmarked in the database as a stored procedure for easy execution and grading. Stored procedures follow the naming convention TP_Qx where x corresponds to the query number. For example:
CALL TP_Q1();
