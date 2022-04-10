# Architecture and Design

SASS is integrated in the UNI application, which is structured around the MVC architecture. The storage of schedules and settings is local, that is, on the client’s smartphone, and may be updated through user interaction and/or fetches to the SIGARRA API for the latest available information. Submissions are also performed through this API.

## Logical architecture

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/logical_architecture.png"/>
</p>

The **SASS** project is designed to be contained and integrated with the **UNI** app. It follows the MVC architectural pattern adapted to the Flutter framework and the current UNI design decisions. The view uses the model state and also sometimes the controller methods to handle its inner state when reacting to user events. The controller depends on the model to create and update the model state. The controller uses the SIGARRA API to fetch and send data to SIGARRA.

The **view** package includes the visual widgets (stateful and stateless) of the app, namely the pages of SASS on the app. There is a page for class registration, course selection, schedule planning and restrictions selection.

The **model** package includes the relevant models of the SASS app, such as a schedule preference option, a restriction, a class registration submission window, a class, a lecture and a course unit. The last two can be reused from the original UNI app.

The **controller** package includes components to interact with the SIGARRA API service (submit schedule preferences and fetch information), to generate a schedule based on the available classes and user constraints, and to validate a schedule (for example, detecting lecture overlaps). It also includes the **local storage** package to store the user data and fetched data locally. The only relevant component in this package in the context of the SASS project is the controller for the class registration database.

The only external service the app interacts with is the **SIGARRA API**, which allows retrieving and submitting data to SIGARRA: for example, fetching the list of classes and class registration periods, or submitting the schedule preferences.

## Physical architecture

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/physical_architecture.png"/>
</p>

Physically, there are two nodes in the structure of this software system. One is the smartphone used by the student to run the app. The other is the SIGARRA server the app will communicate with.

The **Smartphone** contains the _UNI app_ with the SASS features implemented, which is the app that the student will use. The technology selected was the [Flutter](https://flutter.dev/) framework, since the original UNI app already uses this framework. It also contains the database to locally store the user data and data fetched from SIGARRA, so that it is available the next time the user opens the app. The database is implemented in SQLite, since this is the most natural choice for android apps.

The **SIGARRA server** contains the _SIGARRA API_ artifact which allows fetching and submitting relevant data between the app and the server. Because the physical architecture of SIGARRA is not accessible to us, the other relevant artifacts and technologies used in this node cannot be known. As such, those have been omitted from the UML.

## Vertical prototype

For the vertical prototype, we forked the original UNI app so that the SASS project can be built integrated with the app from the start and be more consistent with it (both in code style and in design style). We have added a new button to the navigation drawer: "Escolha de Turmas". This button has the purpose of opening the main page of the SASS project, that is, the class registration page.

Since there are no substantial SASS features implemented in the iteration 0, this page was filled with a placeholder text listing the authors of the class registration feature.

<table>
  <tr>
    <td><img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/VP_navigation_drawer.jpg"></td>
    <td><img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/VP_credits.jpg"></td>
  </tr>
  <tr>
    <td>Navigation drawer with "Class registration" option.</td>
    <td>Class registration page with credits.</td>
  </tr>
</table>
