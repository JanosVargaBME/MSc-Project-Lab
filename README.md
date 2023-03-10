# MSc-Project-Laboratory 1-2

## Sprint based Task manager

### Specification

----

My main goal is to create a Task manager to handle sprints for a company.

The company's admin can manage Projects (CRUD functions) and set Project admins for each project. The admin can register new developers. The projects can be viewed in an overview table.

Each project uses sprint as a unit of time management. Project admins can manage the sprint's data (length, start/end date, developers) on an admin page.

For every sprint, the developers can add Work items to handle the project development. The work items are arranged hierarchically:

> EPIC

> ------ Feature

> --------------- User Story

> ---------------------------- Task

> ---------------------------- Bug

Each Work item has a:
- Title
- Description
- Developer
- State: New/Active/Resolved/Closed
- Log data(eg.: estimated/remaining hours)
- Branch name
- PR link
- Parent item

All work items are displayed in a basic table view on the Work Item's list page.

All work items are displayed in a hierarchical tree list on the Backlogs page.

All work items are displayed for the selected sprint on a Kanban board like page, where the developers can drag and drop the Tasks/Bugs to another state.

### Weekly schedule

----

>1. Project specification, DB Scheme, Mock-ups, Weekly schedule, Git init

>2. Project (ASP.NET + BLazor), nswag and DB init

>3. Authentication (Identity based server), login + registration implementation

>4. Role based authorization (Admin, Project Admin, User)

>5. DB scheme init

>6. Project overview page implementation

>7. Project overview/manager page implementation

>8. Sprint's admin page implementation

>9. Work Items page implementation 

>10. Backlogs page impementation

>11. Sprint Task Board implementation

>12. Sprint Task Board implementation

>13. Test, test, test

>14. Documentation

>+ Optional task:  Project and Task export to PDF

### DB Scheme

----

Employee:
- Name
- RegistrationDate
- IsActive
- Capacity (1/0.75/0.5) 
- Role (Admin/Developer)

Project:
- Name
- Description
- StartDate
- EndDate
- ProjectAdmin (`Employee`)
- Developers (`List<Employee>`)
- Sprints (`List<Sprint>`)

Sprint:
- StartDate
- EndDate
- WorkDayCount
- DeveloperCapacities (`List<DeveloperCapacity>`)

DeveloperCapacity:
- EmployeeId
- CapacityHour (per week)

WorkItem:
- Title
- Description
- Files?
- EmployeeId
- State: New/Active/Resolved/Closed
- OriginalEstimatedHours
- HoursLogged
- BranchName
- PullRequestLink
- ParentItem

### Mock-ups

Project Overview Page

![Project Overview Page](./mockups/projects.png)

Backlog Page

![https://www.kevinrchant.com/2020/12/03/viewing-agile-and-scrum-work-items-at-the-same-time-in-azure-devops/](./mockups/backlog.png)

Sprint Task Board:

![Sprint Task Board](./mockups/task_board.jpg)
