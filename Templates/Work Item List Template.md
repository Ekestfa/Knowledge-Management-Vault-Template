---
tags: ["work-item-list"]
alias: 
created-at: "{{date}} {{time}}"
project: 
content: []
---
%%
related-kanban::
%%
# {{title}}
*Created at {{date}} {{time}}*
*Link:*

## Use Case Diagram

## Work Items
```dataview
TABLE WiTHOUT ID
	progress as Status,
	(link(file.path, alias)) as Name,
	stakeholder as Stakeholder,
	classification as Classification,
	priority as Priority,
	story-point as "Story Point"
FROM #work-item 
WHERE parent = this.file.name
SORT priority ASC
```
