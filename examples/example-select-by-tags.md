# Select files by tags

```dataview
TABLE file.folder AS "Folder",
	file.mtime AS "Modified",
	join(map(file.tags, (t) => t), ", ") AS "Tags"
FROM "words" OR "templates"
WHERE contains(file.tags, "vrsta/glagol")
	AND contains(file.tags, "nivo/A1")
SORT file.name ASC
```