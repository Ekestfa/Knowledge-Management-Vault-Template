---
tags: project
alias: "{{VALUE:⚒ Add Project}}"
created-at: "{{date}} {{time}}"
contents: []
related: 
subtitle: "{{VALUE:Project Subtitle}}"
status:
goals: []
kanban-board: ""
work-item-number: ""
---
%%
```js quickadd
const goalNotes = DataviewAPI.pages("#goal").where(p => !p.file.path.contains("Templates")).values;
const targetGoal = await this.quickAddApi.suggester(goalNotes.map(p => p.file.name), goalNotes);
const targetGoalFile = app.vault.getAbstractFileByPath(targetGoal.file.path);
let markdownLink = this.app.fileManager.generateMarkdownLink(targetGoalFile, '');
markdownLink = `${markdownLink.slice(0, markdownLink.length - 2)}|${targetGoal.alias}${markdownLink.slice(markdownLink.length - 2)}`
return `Goal:: ${markdownLink}`;
```
kanban-related::
%%

# {{VALUE:⚒ Add Project}}

## Project Info

## Thoughts

## Restrictions

## Business Requirements and Clarifications

## Work Items

```dataview
TABLE WITHOUT ID
	link(file.name, alias) as "Work Item",
	created-at as "Created At"
FROM #work-item-list 
WHERE project = this.file.name
```

## Product Backlog

```dataview
TABLE WITHOUT ID
	progress as Status,
	(link(file.path, alias)) as Name,
	stakeholder as Stakeholder,
	classification as Classification,
	priority as Priority,
	story-point as "Story Point"
FROM #work-item 
WHERE contains(backlog, "product") AND contains(project, "this.file.name")
SORT priority ASC
```

## Iteration Backlog

```dataview
TABLE WITHOUT ID
	iteration-no as "Iteration No",
	progress as Status,
	(link(file.path, alias)) as Name,
	stakeholder as Stakeholder,
	classification as Classification,
	priority as Priority,
	storypoint as "Story Point"
FROM #work-item 
WHERE parent = this.file.name AND contains(backlog, "iteration")
SORT priority ASC, iteration-no ASC
```

## Risks


## Resources