# Team MIS Project 2

#Team Members
1. Jack Gust [@jackgust1](https://github.com/jackgust1)
2. Katie Lee [@kel64913](https://github.com/kel64913)
3. Jolina Dorgan [@jolinadorgan](https://github.com/jolinadorgan)
4. Emil Kali [@emk19648](https://github.com/emk19648)
5. Michael Haviland [@MichaelHaviland](https://github.com/MichaelHaviland)

# Data Dictionary

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
| parkingAssignmentStartDate  | Start date of parking assignment           | VARCHAR   | 45   |        |      |
| parkingAssignmentEndDate    | End date of parking assignment             | VARCHAR   | 45   |        |      |

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
| roomAssignmentStartDate | Start date of the room assignment            | VARCHAR   | 45   |        |      |
| roomAssignmentEndDate   | End date of the room assignment              | VARCHAR   | 45   |        |      |

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
| Column Name        | Description                                                                                 | Data Type | Size | Key?    |
|--------------------|---------------------------------------------------------------------------------------------|-----------|------|---------|
| idGradInstructor   | Primary Key, unique identifier for the graduate instructor. Represents a graduate student who serves as an instructor. | INT       |      | PK, FK  |
| idUndergradStudent | Foreign Key, references `Student.idStudent`. Identifies the undergraduate student linked to this graduate instructor for supervision or assistance. | INT       |      | FK      |

## Table: GradInstructAssignments
| Column Name       | Description                                                                 | Data Type | Size | Key?    |
|-------------------|-----------------------------------------------------------------------------|-----------|------|---------|
| idGradInstructor  | Foreign Key, references `GraduateInstructor.idGradInstructor`. Represents the graduate instructor assigned to a specific class. | INT       |      | PK, FK  |
| idClasses         | Foreign Key, references `Classes.idClasses`. Identifies the class assigned to the graduate instructor. | INT       |      | PK, FK  |
| classStartDate    | The start date of the graduate instructor's assignment to the class.       | VARCHAR   | 45   |         |
| classEndDate      | The end date of the graduate instructor's assignment to the class.         | VARCHAR   | 45   |         |
