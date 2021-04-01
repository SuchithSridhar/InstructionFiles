# Task Warrior

`pacman -S task`  
`apt-get install task-warrior`

task \<FILTER> \<REPORT | COMMAND>

## Reports

> task (task next)
> task list
> task \<ID> info

## Adding

Add a task

> task add Water the flowers

## Modifying

- task \<ID> mod
- task edit - Edit the task using the system editor.
- task annotate
- task undo (Undo the last command)
- task purge (Completely remove a task forever) Coming 2.6.0

## Tags

Add a tag

> task add +home +work Water the flowers

Remove a tag

> task 4 mod -home

## Projects

Add a project to a tag

> task add project:Home Water the flowers

SubProjects

> task add project:Home.Kitchen Water the flowers

## Priority

Add a specific priority

> task add pri:H Water the dying flowers.

Options for priority: H, M, L

## Dates

Different kinds of dates are available:

- Use a _due date_ to specify the exact date by which a task must be
  completed.
- The _scheduled date_ represents the earliest opportunity to work on a
  task. (Gives a reminder on this date) (Still shown on task list).
- The _wait date_ represents the earliest opportunity the task should
  show up on the task list.
- The _until date_ specifies a date after which the task
  self-destructs.

Exact Specification:

> task ... due:7/14/2008

ISO-8601:

> task ... due:2013-03-14T22:30:00Z

Relative Wording:

> task .. due:now
> task .. due:today
> task .. due:yesterday
> task .. due:friday

Day number with ordinal

> task .. due:3wks
> task .. due:23rd
> task .. due:9hrs

Start of ...

> task .. due:sow (start of week)
> task .. due:soww (start of work week)
> task .. due:socw (start of calendar week)
> task .. due:som (start of month)
> task .. due:soq (start of quarter)
> task .. due:soy (start of year)

(replace 's' with 'e' and that means end)

Date arithmetic

task .. due:today+3d
task .. due:fri+16h

## Deleting

## Completing

## Annotations

Just a way of associating more meta data with the task that's created
in the form of free-form text.

Add an annotation to an existing task.

> task 1 annotate Go to the shop on the corner of the road.
