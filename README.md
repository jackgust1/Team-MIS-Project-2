# Team MIS Project 2

#Team Members
1. Jack Gust [@jackgust1](https://github.com/jackgust1)
2. Katie Lee [@kel64913](https://github.com/kel64913)
3. Jolina Dorgan [@jolinadorgan](https://github.com/jolinadorgan)
4. Emil Kali [@emk19648](https://github.com/emk19648)
5. Michael Haviland [@MichaelHaviland](https://github.com/MichaelHaviland)


# Data Model

![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/image001.png)

# Data Dictionary: University Database

---
## Table: MealPlan

| Column Name   | Description                              | Data Type | Size | Format | Key? |
|---------------|------------------------------------------|-----------|------|--------|------|
| idMealPlan    | PK, unique identifier for each meal plan | INT       |      |        | PK   |
| mealPlanType  | Type of meal plan                        | VARCHAR   | 45   |        |      |
| planCost      | Cost of the meal plan                    | VARCHAR   | 45   |        |      |

---

## Table: Student

| Column Name       | Description                                 | Data Type | Size | Format | Key? |
|-------------------|---------------------------------------------|-----------|------|--------|------|
| idStudent         | PK, unique identifier for each student      | INT       |      |        | PK   |
| studentFName      | First name of the student                   | VARCHAR   | 45   |        |      |
| studentLName      | Last name of the student                    | VARCHAR   | 45   |        |      |
| studentEmail      | Email of the student                        | VARCHAR   | 45   |        |      |
| studentYear       | Academic year of the student                | VARCHAR   | 45   |        |      |
| studentGpa        | GPA of the student                          | VARCHAR   | 45   |        |      |
| studentType       | Type of student (e.g., full-time, part-time) | VARCHAR   | 45   |        |      |
| studentHomeState  | Home state of the student                   | VARCHAR   | 45   |        |      |
| idMealPlan        | FK, references `MealPlan.idMealPlan`        | INT       |      |        | FK   |

---

## Table: Classes

| Column Name   | Description                         | Data Type | Size | Format | Key? |
|---------------|-------------------------------------|-----------|------|--------|------|
| idClasses     | PK, unique identifier for each class | INT       |      |        | PK   |
| className     | Name of the class                   | VARCHAR   | 45   |        |      |

---

## Table: Enrollment

| Column Name   | Description                                    | Data Type | Size | Format | Key? |
|---------------|------------------------------------------------|-----------|------|--------|------|
| idStudent     | FK, references `Student.idStudent`             | INT       |      |        | PK, FK |
| idClasses     | FK, references `Classes.idClasses`             | INT       |      |        | PK, FK |

---

## Table: Organizations

| Column Name         | Description                                  | Data Type | Size | Format | Key? |
|---------------------|----------------------------------------------|-----------|------|--------|------|
| idOrganizations     | PK, unique identifier for each organization  | INT       |      |        | PK   |
| organizationName    | Name of the organization                     | VARCHAR   | 45   |        |      |
| organizationType    | Type of the organization (e.g., club, society) | VARCHAR   | 45   |        |      |

---

## Table: Parking

| Column Name     | Description                           | Data Type | Size | Format | Key? |
|-----------------|---------------------------------------|-----------|------|--------|------|
| idParking       | PK, unique number identifying parking | INT       | 3    |        | PK   |
| parkingLocation | Name of location for parking          | VARCHAR   | 45   |        |      |
| parkingType     | Identifies the type of parking        | VARCHAR   | 45   |        |      |

---

## Table: ResidenceHalls

| Column Name            | Description                                   | Data Type | Size | Format | Key? |
|------------------------|-----------------------------------------------|-----------|------|--------|------|
| idResidenceHall         | PK, unique identifier for each residence hall | INT       |      |        | PK   |
| residenceHallName       | Name of the residence hall                    | VARCHAR   | 45   |        |      |
| residenceHallOccupancy  | Maximum occupancy of the residence hall       | VARCHAR   | 45   |        |      |

---

## Table: ParkingAssignment

| Column Name                | Description                                | Data Type | Size | Format | Key? |
|----------------------------|--------------------------------------------|-----------|------|--------|------|
| idParkingAssignment         | PK, unique identifier for parking assignment | INT       |      |        | PK   |
| idParking                   | FK, references `Parking.idParking`         | INT       |      |        | FK   |
| idStudent                   | FK, references `Student.idStudent`         | INT       |      |        | FK   |
| parkingAssignmentStartDate  | Start date of parking assignment(i.e. Semester)           | VARCHAR   | 45   |        |      |
| parkingAssignmentEndDate    | End date of parking assignment(i.e. Semester)             | VARCHAR   | 45   |        |      |

---

## Table: StudentInvolvement

| Column Name           | Description                                       | Data Type | Size | Format | Key? |
|-----------------------|---------------------------------------------------|-----------|------|--------|------|
| idStudentInvolvement   | PK, unique identifier for involvement record      | INT       |      |        | PK   |
| idOrganizations        | FK, references `Organizations.idOrganizations`   | INT       |      |        | FK   |
| idStudent              | FK, references `Student.idStudent`               | INT       |      |        | FK   |

---

## Table: DormRoom

| Column Name        | Description                                  | Data Type | Size | Format | Key? |
|--------------------|----------------------------------------------|-----------|------|--------|------|
| idDormRoom         | PK, unique identifier for each dorm room     | INT       |      |        | PK   |
| idResidenceHall    | FK, references `ResidenceHalls.idResidenceHall` | INT    |      |        | PK, FK |
| dormRoomType       | Type of dorm room (e.g., single, double)     | VARCHAR   | 45   |        |      |

---

## Table: RoomAssignment

| Column Name            | Description                                  | Data Type | Size | Format | Key? |
|------------------------|----------------------------------------------|-----------|------|--------|------|
| idRoomAssignment        | PK, unique identifier for room assignment   | INT       |      |        | PK   |
| idDormRoom              | FK, references `DormRoom.idDormRoom`        | INT       |      |        | FK   |
| idStudent               | FK, references `Student.idStudent`          | INT       |      |        | FK   |
| roomAssignmentStartDate | Start date of the room assignment(i.e. Semester)            | VARCHAR   | 45   |        |      |
| roomAssignmentEndDate   | End date of the room assignment(i.e. Semester)              | VARCHAR   | 45   |        |      |

---

## Table: Programs

| Column Name   | Description                             | Data Type | Size | Format | Key? |
|---------------|-----------------------------------------|-----------|------|--------|------|
| idPrograms    | PK, unique identifier for each program  | INT       |      |        | PK   |
| programName   | Name of the program                     | VARCHAR   | 45   |        |      |
| programType   | Type of the program (e.g., degree, certificate) | VARCHAR | 45   |        |      |

---

## Table: StudentPrograms

| Column Name                | Description                                    | Data Type | Size | Format | Key? |
|----------------------------|------------------------------------------------|-----------|------|--------|------|
| idStudent                  | FK, references `Student.idStudent`             | INT       |      |        | PK, FK |
| idPrograms                 | FK, references `Programs.idPrograms`           | INT       |      |        | PK, FK |
| admitTerm                  | Term in which the student was admitted         | VARCHAR   | 45   |        |      |
| expectedGraduationTerm     | Term in which the student is expected to graduate | VARCHAR | 45   |        |      |


## Table: GraduateInstructors
| Column Name        | Description                                                                                 | Data Type | Size | Format  |Key?    |
|--------------------|---------------------------------------------------------------------------------------------|-----------|------|---------|--------|
| idGradInstructor   | Primary Key, unique identifier for the graduate instructor. Represents a graduate student who serves as an instructor. | INT       ||      | PK, FK  |
| idUndergradStudent | Foreign Key, references `Student.idStudent`. Identifies the undergraduate student linked to this graduate instructor for supervision or assistance. | INT       |    ||  | FK      |

## Table: GradInstructAssignments
| Column Name       | Description                                                                 | Data Type | Size | Format |    Key?    |
|-------------------|-----------------------------------------------------------------------------|-----------|------|---------|------------|
| idGradInstructor  | Foreign Key, references `GraduateInstructor.idGradInstructor`. Represents the graduate instructor assigned to a specific class. | INT       ||      | PK, FK  |
| idClasses         | Foreign Key, references `Classes.idClasses`. Identifies the class assigned to the graduate instructor. | INT       |  |   | PK, FK  |
| classStartDate    | The start date of the graduate instructor's assignment to the class. (i.e. Semester)     | VARCHAR   | 45   |     |    |
| classEndDate      | The end date of the graduate instructor's assignment to the class. (i.e. Semester)        | VARCHAR   | 45   |     |    |


# SQL Queries
### Query 1 - View
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query1%20-%20View.png)
### Query 1
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query1.png)
#### Query 1 - Description
To start, we decided to create a view, ProgramGPA, by combining Student, StudentPrograms, and Programs in order to aggregate data to calculate the average GPA of every student within a specific program. By doing this, we have created a quick and reusable table that allows us access to this data.
By creating this view, we were able to reference it within a query, which joins the view with StudentPrograms, in order to display the average GPA along with the amount of students enrolled within the program.
#### Query 1 - Justification
This will serve as a vital and ongoing resource to the manager of the database because it allows them to see both academic performance, but also the enrollment trends surronding the performance. By allowing a manager to see this, they can better allocate instructional resources into high traffic programs where all students seem to trouble and double down investments into programs that they want to maintain performance in.

### Query 2 - Procedure
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%202%20-%20Procedure.png)
### Query 2 - Call with Data
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%202%20-%20Example.png)
#### Query 2 - Description
Primarily, we created the inputs currentTerm, which is a string representing the current term of the school year, and minGPA, which represents a minimum standing a student must be over to graduate. Second, we selected every student's ID, their first and last names, their GPA (to later confirm good standing) and their expected graduation date from the Student and StudentPrograms tables. We set filters to where the expectedGraduationTerm would be equal to the current one and the student's overall cumulative GPA must be greater than or equal to the minimum standing. We then created the group by statement in order to efficiently show the data.
#### Query 2 - Justification
This query would be instrumental in graduation planning, allowing planners to see who graduates and if they qualify for academic honors and awards.

## Query 3 - View
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%203%20View.png)
## Query 3
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%203.png)
#### Query 3 - Description
This view allows for the counting of enrollment within a class and will either identify it as a high demand class (1) or a non high demand class (0). By doing this, we allowed ourselves to be able to play with, as in filter by subject, how we search for high demand classes from a managerial standpoint.
#### Query 3 - Justification
As a manager at the University, we would want to make sure that we can accomadate the high demand of certain majors and make sure that people can take the classes that they want to. If a class or a subject overall has too much demand, we know that we need to allocate more CRN's to the class or subject.

## Query 4 - Procedure and Call with Data
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/d326e629505079128e80d8de2c671aaaefdf1b52/Screenshot%202024-12-03%20at%207.13.02%20PM.png)
#### Query 4 - Description
This procedure Lists the ID, first name, last name, and residing residence hall of students taking at least an undefined Terry classes (classes involving FINA or MIST) as well as how many Terry classes they are taking in descending order. By utilizing a left join we are also able to include students not living on campus. When we call this procedure, we can specifiy how many minimum Terry classes the students in the returned data are taking.
#### Query 4 - Justification
This query helps the school find out which students are taking a major course load in the Terry Business School and how far they live from these classes. For example, a student with 4+ Terry Courses would likely rather reside closer to the business school, so in the future the University can optimize where people live based on what classes they are taking. Additionally, the school can create bus routes to and from the Terry Business school and corresponding dorms. This query would also help the University allocate parking close to the business school for students who don’t live on-campus but take many Terry courses. Lastly, this could help compare and monitor performance of students who do and don’t live near the business school.

## Query 5 - Views
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%205%20-%20Views.png)
### Query 5
![Alt text](https://github.com/jackgust1/Team-MIS-Project-2/blob/main/Query%205%20-%20Example.png)
#### Query 5 - Description
The first of these views list the names of each Greek Life organization (listed as "social" under "organizationType") in the database and the amount of members in each organization. The second query is very similar to the first, but by using an inner join to connect StudentInvolvement to RoomAssignment, we're able to see how many members of each organization live on campus. The query, utilizing both of the views, simply lists the name of each Greek Life organization, the total membership, the amount of members living on campus, and the ratio of the members living on campus compared to the total.
#### Query 5 - Justification
These will serve to help keep track of the membership of Greek Life organizations, both the total membership and the number of members who live on campus. This data could help with organizing events regarding Greek Life or keeping track of the growth of Greek Life organizations over time.

# Dashboard

