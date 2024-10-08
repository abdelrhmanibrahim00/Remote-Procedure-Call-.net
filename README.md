Classroom Simulation Project
Overview

This project simulates a classroom environment with components that include a server (Classroom), teachers, and doors. It follows a cycle where students are generated, teachers vote to start or end a class, and students leave once the class ends. The voting processes for starting and ending the class are managed separately.
Situation

In this scenario, the classroom starts with no session in progress. Doors act as entry points where a random number of students (which can be positive or negative) are generated. These students are accumulated in the classroom. If the number of students exceeds a set threshold, the teachers begin voting to decide if the class should start.

During the session, doors are closed, and no additional students are added to the classroom. Teachers continue voting every 2 seconds for when the class should end. Once the class ends, students leave, and the cycle restarts.
Task

The objective of this project is to simulate:

    The generation of students by the doors.
    Teachers voting to start and end the class.
    Management of the class session, including closing doors and tracking the number of students.

Specific requirements include:

    Random student generation by doors.
    Teachers vote every 2 seconds, and the class begins if at least half vote to start.
    While in session, doors are closed, and the student count remains static.
    After the class begins, teachers vote every 2 seconds for the end of the class.
    The class ends when at least half of the teachers vote to stop the session, at which point a random number of students leave.
    Separate channels are used for voting to start and end the session.

Action

To implement this, the project involves three main components:

    Classroom (Server): Manages the state of the classroom, the count of students, and the session status.
    Teacher: Simulates voting behavior. Each teacher randomly votes every 2 seconds on whether to start or end the class.
    Door: Generates a random number of students, which can be positive or negative. These students are added to the classroom's student count.

The logic for the teachers' voting and door management is handled by independent processes running on a timed loop (every 2 seconds).
Key Features

    Student Generation: Randomized student numbers are added by the doors to the classroom.
    Teacher Voting: Teachers randomly vote for class start or end based on a 50% majority.
    Session Control: While the class is in session, doors are closed, and no students are added.
    Separate Voting Channels: The voting process for starting and ending the class is handled through different channels, ensuring no overlap.

Result

The simulation successfully models a cycle where:

    Students are randomly generated by the doors.
    Teachers vote to start the class once a threshold is met.
    When the class starts, no additional students are added, and doors are closed.
    Teachers continue voting during the session to decide when the class should end.
    Upon ending the session, students leave, and the simulation restarts from the beginning.

This project demonstrates effective management of a timed simulation with parallel voting processes and dynamic student management.
How to Run the Project

    Clone the repository from GitHub.
    Run the server (Classroom) to start the simulation.
    Teachers will automatically begin voting based on the student count.
    Doors will generate random student numbers periodically.
