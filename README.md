# 3LEIC04T2

## Members

 - Isabel Vieira - up201907399
 - João Baltazar - up201905616
 - Nuno Costa - up201906272
 - Pedro Gonçalo Correia - up201905348
 - Pedro Silva - up201907523
...

# SASS - Schedule Assistant

## Vision Statement

For FEUP students, who need to apply for class attendance schedules at the start of each semester, SASS is a UNI app tool that helps them to quickly and easily plan and submit their schedule preferences. 

Unlike SIGARRA, our product offers a more intuitive and convenient interface, with schedule planning before the registration period, smart generation, and automatic submission.

## Main Features

- Schedule planning - Select and experiment different combinations of classes, even before class registration is opened.
- Multiple options - Create multiple alternative schedules ordered by preference.
- Intuitively adjust options - Easily select and jump between alternative schedules, reorder, copy and delete alternatives, and assign a name to each alternative to serve as a mnemonic.
- Overlap detection - Detect and signal overlapping classes, but still allow the user to select them.
- Automatic generation - Automatically generate a schedule that respects the constraints the user imposes.
- Course inference - Retrieve from SIGARRA the courses the user is enrolled on, instead of manually specifying which courses to register in classes.
- Choice submission - Submit the current list of preferences to SIGARRA directly from the app.
- Registration period dates - Conveniently check the dates when class registration period starts and ends for the user.
- Automatic submission - Set the app to automatically submit the current list of preferences as soon as class registration is allowed in SIGARRA.

## Assumptions and dependencies

- SIGARRA API to retrieve student course enrollments, class timetable, and class registration periods, as well as to submit class registration options.
