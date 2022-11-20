---
tags: 
alias: Home
cssClasses: cards-1-1 table-wide
---
# Dashboard
## Goals
```dataview
TABLE WITHOUT ID
	(link(file.path, alias)) as Title,
	Type as Type,
	status as Status,
	Timespan as Timespan,
	created-at as Created,
	Bar as Progress
FROM #goal
SORT Type DESC
```
## Projects
```dataview
TABLE WITHOUT ID
	(link(file.path, alias[0])) as Title,
	subtitle as Description,
	status as Status,
	kanban-related as Board,
	link(Goal, Goal.alias) as Goals
FROM #project
```
