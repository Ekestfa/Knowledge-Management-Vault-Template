---
tags: ["scenario"]
alias: ""
created-at: "{{date}} {{time}}"
level: ""
parent: []
contents: []
status: ""
progress:
---
# {{title}}
*Created at {{date}} {{time}}*
*Link:* 

## Questions/Cues

## Scenario Description
*Text..*
*Drawings...*

## Analysis of the Scenario
*Thoughts...*

## Acceptance Criteria
```dataview
TABLE WITHOUT ID
	link(file.name, alias) as ACs,
	status as Status,
	description as Description
FROM #acceptance-criteria 
WHERE parent = this.file.name
```

## Tasks
```dataview
TABLE WITHOUT ID
	link(file.name, alias) as Task,
	progress as Progress,
	status as Status,
	remark as Remark
FROM #task 
WHERE parent = this.file.name
```

## Approach Description

## Discussions

## Summary

## References