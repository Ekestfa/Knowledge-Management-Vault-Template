---
tags: goal
alias: {{VALUE:Goal}}
created-at: "{{DATE:YYYY-MM-DD HH:mm}}"
contents: []
status:
Type: 
Progress: 0
Target: {{VALUE:🎯 Target (number)}}
Reason: {{VALUE:Why this goal?}}
Timespan: {{VALUE:10 Years, 5 Years, 3 Years, 1 Year, 6 Months, 1 Month, 1 Week}}
---
%%
Bar:: `$= dv.view('progress-bar', {file: '{{DATE}} - {{VALUE:Goal}}'})`
Projects:: 
%%


## Intent

## Scope

## Roadmap

## Related Projects
```dataview
TABLE WITHOUT ID
	link(file.name,alias) as "Project Name",
	status as Status,
	work-item-number as "Work Items",
	kanban-board as Board,
	created-at as "Creation Time"
FROM #project
WHERE parent = this.file.name OR contains(goals, this.file.name)
```

## Related Scenarios
```dataview
TABLE WITHOUT ID
	link(file.name,alias) as "Scenario",
	status as Status,
	level as Level,
	kanban-board as Board,
	created-at as "Creation Time"
FROM #project
WHERE parent = this.file.name OR contains(goals, this.file.name)
```

## Discussion