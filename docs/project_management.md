# Project management

- Backlog management: Product backlog and Iteration backlog in [Github Projects board](https://github.com/LEIC-ES-2021-22/3LEIC04T2/projects/1?query=is%3Aopen+sort%3Aupdated-desc)
- Release management:
    - [v0.1 (Iteration 0)](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.1)
    - [v0.2 (Iteration 1)](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.2)
    - [v0.3 (Iteration 2)](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.3)
    - [v0.4 (Iteration 3)](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.4)

## Iteration 1

### Release

[v0.2](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.2)

### Plans

Backlog at the end of the iteration:

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/backlog1_end.png"/>
</p>

### Retrospectives

#### What went well

- Delivers a good UI proof of concept.
- The implemented tasks have no bugs and work properly.
- Good adaptation to the Flutter framework.
- Good adaptation to the original codebase.
- Good group dynamic, communication and teamwork.

#### What went poorly

- The number of incomplete tasks in the iteration backlog was high compared to the number of completed tasks.
- Late start of the work on the iteration.

#### Obstacles along the way

- The last week of the iteration coincided with the week of Queima das Fitas, which reduced the time the team had to work on the project.
- Two group members got infected with COVID-19 around the end of the iteration.
- Conflicting information about the end date of the iteration (information on moodle says the end is after the actual deadline; this update was poorly communicated and confused the team members).

## Iteration 2

### Release

[v0.3](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.3)

### Plans

Backlog at the start of the iteration:

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/backlog2_start.png"/>
</p>

Backlog at the end of the iteration:

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/backlog2_end.png"/>
</p>

### Retrospectives

#### What went well

- Delivers a good product that has value to the user.
- The implemented tasks work as intended.
- All task in the iteration backlog were completed.
- Good group dynamic, communication and teamwork.

#### What went poorly

- No code review nor code reviewer assignment for pull requests on GitHub in many issues.

#### Obstacles along the way

- A unit test in the original UNI code was failing without changes to the code, probably related to its undeterministic call to `Datetime.now()` that made it fail at a specific time of the day.
- Some of the original code was made in a way that we couldn't reuse to our needs because some widgets (`GenericCard`) inherited StatefulWidget instead of using composition as is intended in the flutter framework. This prevented us from calling `setState()` to update those widgets, which is necessary if they are not static. As such, we had to create a similar class (`SectionCard`) that used composition to have access to this method. We ended up creating a new widget instead of changing the existing one so as to avoid needlessly changing the original code that used it and to have more freedom to implement it in a way that is better suited for our case but not for the original one (both classes ended up having slightly different meaning and intended use: ours to divide sections in a page, and the original one to create shortcut widgets in the main page).

## Iteration 3

### Release

[v0.4](https://github.com/LEIC-ES-2021-22/3LEIC04T2/releases/tag/v0.4)

### Plans

Backlog at the start of the iteration:

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/backlog3_start.png"/>
</p>

Backlog at the end of the iteration:

<p align="center" justify="center">
    <img src="https://github.com/LEIC-ES-2021-22/3LEIC04T2/blob/main/images/backlog3_end.png"/>
</p>

### Retrospectives

#### What went well

- Delivers a good product with value to the user and supporting the main features.
- Implementation well tested with no known bugs.
- Good group dynamic, communication and teamwork.

#### What went poorly

- The number of incomplete tasks in the iteration backlog was high.

#### Obstacles along the way

- The deadline of the iteration was too close to the deadlines of other projects in different curricular units, with an heavy impact to the amount of time we could dedicate to this project.
- Implementation of acceptance tests with Gherkin implied updating the flutter SDK. However, this meant changing a lot of code in the original code base, as it used methods that are deprecated in newer versions and wouldn't pass the CI because of lints. Things like the project colors theme were affected by flutter changes. This involved a significant and unexpected amount of work.
- Existing backend of SIGARRA was lacking, with low to no support of the fetches required by our app. In fact, in most cases the only way to get the needed data was to scrap a HTML page. This meant that it was not possible to substitute the mock data with real data from SIGARRA, although a significant portion of the time and effort in this iteration was dedicated to this. Since we couldn't overcome this difficulty, we isolated the mock data in such a way that, if backend were to be implemented for our features, the mock data could easily be substituted with calls to that backend without changing the structure of the project.
- During the work on the iteration, we spotted small bugs that needed fixing and necessary polishing of the existing interface. The cummulative work on those small fixes (that were too small to include in the backlog) also took away some of the time we had dedicated to the iteration.
