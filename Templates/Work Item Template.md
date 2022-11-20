---
tags: ["work-item"]
alias: ""
created-at: "{{date}} {{time}}"
parent: ""
progress: " "
stakeholder: []
classification:
priority:
story-point:
backlog: ["product", "backlog"]
iteration-no:
---
# {{title}}
*Created at {{date}} {{time}}*
*Links:* 

## User Story
As a *role*, I want to *action*, so that *benefit*.

## Acceptance Criteria
```dataview
TABLE WITHOUT ID
	(link(file.path, alias)) as ID,
	status as "Status",
	modules as "Related Modules",
	description as Description
FROM #acceptance-criteria 
WHERE contains(related, this.file.name)
```

## Dependencies

## Discussion

## Review