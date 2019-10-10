---
title: Create Or Update Enity Action
keywords: tracking, consolidated, import, data, entity, createOrUpdateAction
last_updated: 08 November, 2017
tags:
summary: "Create or update an entity with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-entity-action.html
folder: Import
dynamic_content: true
show_mandatory_column: true
columns: [hieracrchyEntityName, ignoredColumn]
parameters: [defaultEntityId]
---

### Examples

Please see below a complete example, with data CSV to import, XML configuration, and resulting entity hierarchy. 

XML:
```xml 
<actions>
	<createOrUpdateEntityAction>
		<options>
			<defaultEntityId>8</defaultEntityId>
		</options>
		<fields>
			<hierarchyEntityName/>
			<hierarchyEntityName/>
		</fields>
	</createOrUpdateEntityAction>
</actions>
```

CSV:
```csv
A,B
A,C
```

HIERARCHY:

```
Entity 8
 - A
 - - B
 - - C
```

### Error Messages

Message | Explanation
---- | ----
Task will fail if the defaultEntityId is not a valid entity ID. | 
