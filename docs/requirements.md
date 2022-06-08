# Requirements

## Use case model 

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/usecases.png"/>
</p>

| Name | Select courses |
|---|---|
| Actor | Student |
| Description | The student selects or deselects the courses whose classes they wish to participate in. |
| Preconditions | <ul><li>The student is enrolled in at least one cycle of studies.</li></ul> |
| Postconditions | <ul><li>The list of selected courses is updated with the new selection and classes of the selected courses can be selected when editing schedules.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows the list of selected courses, with an option to alter that list.</li><li>The student opts to modify the list and is redirected to the course selection page.</li><li>The system shows the list of available courses, each with a checkbox indicating if it is currently selected or not.</li><li>The student changes which courses are selected.</li><li>The system updates the list of selected courses, showing only the selected ones in the schedules.</li></ol> |
| Alternative flows and exceptions | <ol><li>[Course deselection] If, in step 5, the student deselects at least one course, a confirmation prompt appears before applying the changes, warning that existing schedules will no longer include that course.</li><li>[No course selected] If, in step 5, the student deselects all courses, the system will disallow the student from applying the changes until at least one course is selected.</li></ol> |

| Name | Create or edit schedule |
|---|---|
| Actor | Student |
| Description | The student creates or edits a schedule, choosing among the available classes for his selected courses. |
| Preconditions | <ul><li>The student has at least one course selected for class registration.</li></ul> |
| Postconditions | <ul><li>The list of existing schedules is updated with the new or edited schedule.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows the list of existing schedules, each with an option to edit that schedule, and lastly an option to create a new schedule.</li><li>The student selects one of the options and is redirected to the schedule planning page.</li><li>The system shows the current state of the schedule and a list of the available classes for the currently selected courses.</li><li>The student chooses a class for each course selected.</li><li>If wanted, the student may Generate schedule given constraints.</li><li>The student may leave the scheduling planning page at any time, and the changes made to the schedule are automatically saved.</li></ol> |
| Alternative flows and exceptions | <ol><li>[Name schedule] If desired, in step 5, the user may give a name or change the current name for the current schedule.</li></ol> |

| Name | Generate schedule given constraints |
|---|---|
| Actor | Student |
| Description | The student imposes constraints on the schedule and the system tries to automatically select classes while respecting the given constraints. |
| Preconditions | <ul><li>The student has at least one selected course with no class selected in the schedule.</li></ul> |
| Postconditions | <ul><li>The schedule is filled according to the given constraints, unless that is not possible.</li></ul> |
| Normal flow | <ol><li>The student is on the schedule planning page.</li><li>The system shows an option to automatically generate a schedule.</li><li>The student chooses to automatically generate a schedule.</li><li>The system presents a list of possible constraints that the student may add to the schedule, such as preferred teachers, or unavailable hours.</li><li>The user selects the desired constraints.</li><li>The system fills the schedule by automatically selecting classes in the missing selected courses, while respecting the constraints.</li></ol> |
| Alternative flows and exceptions | <ol><li>[No schedule possible with current constraints] If, in step 6, the constraints do not allow for a schedule to be generated, an error will occur and the user may retry step 5 with different constraints.</li></ol> |

| Name | Delete schedule |
|---|---|
| Actor | Student |
| Description | The student deletes an existing schedule. |
| Preconditions | <ul><li>There is at least one schedule in the list of existing schedules.</li></ul> |
| Postconditions | <ul><li>The schedule is removed from the list of existing schedules.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows the list of existing schedules, each with an option to delete that schedule.</li><li>The student selects one of those options, deleting the respective schedule.</li><li>The system removes that schedule from the shown list of existing ones.</li></ol> |
| Alternative flows and exceptions |  |

| Name | Order schedules by preference |
|---|---|
| Actor | Student |
| Description | The student orders their schedule preferences for submission. |
| Preconditions | <ul><li>There are at least two schedules in the list of existing schedules.</li></ul> |
| Postconditions | <ul><li>The list of existing schedules updated with the new order of preference.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows the list of existing schedules.</li><li>The student drags and drops one of the existing schedules into a new position on the list.</li><li>The system updates the order of the list.</li></ol> |
| Alternative flows and exceptions |  |

| Name | See schedule submission dates |
|---|---|
| Actor | Student |
| Description | The student consults the relevant dates to submit their application for class registration. |
| Preconditions |  |
| Postconditions |  |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows the relevant dates for the student to submit their application next to the submission button.</li></ol> |
| Alternative flows and exceptions | <ol><li>[No available submission dates] In step 2, if the schedule application submission dates are not yet published, then a message will be displayed to the student indicating that.</li></ol> |

| Name | Submit schedule application |
|---|---|
| Actor | Student |
| Description | The student submits their schedule preference directly to SIGARRA. |
| Preconditions | <ul><li>There exists at least one valid schedule in the list of schedules.</li><li>The current date is within the class registration time window.</li></ul> |
| Postconditions | <ul><li>The schedule preference is submitted to SIGARRA, replacing any previous submission.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows a button to submit the current preferences.</li><li>The student submits the schedule through the submit button.</li><li>The schedule application is submitted to SIGARRA, replacing any previous submission.</li></ol> |
| Alternative flows and exceptions | <ol><li>[Schedule with errors] In step 3, if at least one schedule on the preference list has an error preventing it from being submitted to SIGARRA, the student will be prompted to either ignore the schedules with errors in the submission or go back and fix the errors.</li></ol> |

| Name | Activate automatic submission |
|---|---|
| Actor | Student |
| Description | The student activates automatic submission of the schedule application so that it submits the current preferences and any future updates to it as soon as it is permitted on SIGARRA. |
| Preconditions | <ul><li>There exists at least one valid schedule in the list of schedules.</li></ul> |
| Postconditions | <ul><li>The schedule application is submitted as soon as possible every time it is updated.</li></ul> |
| Normal flow | <ol><li>The student accesses the "Class Registration" section of the UNI app.</li><li>The system shows a checkbox to activate automatic submission next to the submit button.</li><li>The student activates the automatic submission by ticking the box.</li><li>The system warns that any schedule with errors will be skipped by automatic submissions.</li><li>The user confirms the automatic submission activation.</li><li>The system will submit the user preferences and any future updates to them from now on as soon as it is permitted on SIGARRA.</li></ol> |
| Alternative flows and exceptions | <ol><li>[Cancel automatic submission] In step 2, if automatic submission is activated, the box will be checked and instead of step 3 and the following steps, the user may untick the box to stop automatic submission.</li></ol> |

## UI Mockups

The Figma file with all the UI Mockups is presented below. It is possible to see the page flow using Figma's presentation feature.

https://www.figma.com/file/DDAZTuVdwik89Y9P1nRDp4/SASS?node-id=0%3A1

## Domain model

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/domainmodel.png"/>
</p>

Students using SASS manage lists of schedule preferences, each for a given semester. A **PreferenceList** is an ordered list of **Schedule** options made by the student, from the most preferred **Schedule** to the least preferred **Schedule**. Each **Schedule** has a name and the list of chosen **Class**es, and can be marked as a draft so that it is skipped when submitting the preferences.

Each **PreferenceList** is associated to **SelectedCourse**s, a list of **Course**s in which the student is enrolled and whose **Classes** they wish to frequent. A **Course** is a curricular unit, having a name, acronym, code and semester it is occurring in. Each **Course** belongs to the syllabus of a **Degree**. Each **Degree** has a name and acronym, and is associated with the **SubmissionWindow**s of each class registration application phase, during which application submission is allowed.

A **Class** has a name and **ClassPeriod**s, which are the periods of time in the schedule when the students in that **Class** are having lessons. Each **ClassPeriod** has a teacher, classroom, and the weekday as well as begin and end times of that period. A **ClassPeriod** may be a **TheoreticalClass**, **PracticalClass**, **TheoreticalPraticalClass**, **LabClass**, **PracticalLabClass**, and **OrientationClass**.

