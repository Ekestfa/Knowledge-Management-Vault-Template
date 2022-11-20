---
tags: goal
alias: {{VALUE:Goal}}
created-at: "{{date}} {{time}}"
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

## Discussion

### Created projects
```dataviewjs
const pages = dv.current().file.inlinks.where(p => dv.page(p.path).tags?.contains('project'));

dv.table(["Project", "Status"], pages.map(p => {
	const page = dv.page(p.path); 
	return [page.file.link, page.status]
}));
```
