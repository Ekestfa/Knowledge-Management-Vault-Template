---
tags: MOC
alias: Home
cssClasses: cards-1-1 table-wide
---
# Dashboard

## Goals
```dataview
TABLE WITHOUT ID
	link(file.path, alias) as Title,
	Type as Type,
	status as Status,
	Timespan as Timespan,
	created-at as "Creation Time",
	Bar as Progress
FROM #goal
WHERE !contains(file.name, "Template")
SORT Type DESC
```

## Projects
```dataview
TABLE WITHOUT ID
	link(file.path, alias) as Title,
	subtitle as Description,
	status as Status,
	kanban-related as Board,
	link(Goal, Goal.alias) as Goals
FROM #project
WHERE !contains(file.name, "Template")
```

## Index
```dataview
TABLE WITHOUT ID
	link(file.name,alias) as Topic
FROM #SUBMOC
WHERE !contains(file.name, "Template")
```

## Permanent Notes
List of permanent notes, which status is not `done`.

```dataview
TABLE WITHOUT ID
	link(file.name, alias) as "Permanent Notes",
	created-at as "Creation Time"
FROM #permanent 
WHERE !contains(file.name, "Template") AND progress = "done"
```


## Literature Notes
List of permanent notes, which status is not `done`.

```dataview
TABLE WITHOUT ID
	link(file.name, alias) as "Literature Notes",
	created-at as "Creation Time",
	information-gathering as "5W1H",
	source-type as "Source Type",
	remark as Remark
FROM #literature  
WHERE !contains(file.name, "Template") AND progress != "done"
```