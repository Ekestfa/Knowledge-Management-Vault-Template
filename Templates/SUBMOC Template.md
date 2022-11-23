---
tags: ["SUBMOC"]
created-at: "{{date}} {{time}}"
---
# {{title}}

```dataview
TABLE WITHOUT ID
	link(file.name, alias) as "Title"
FROM #HUB
WHERE !contains(file.name, "Template") AND contains(parent, this.file.name)
SORT priority ASC
```