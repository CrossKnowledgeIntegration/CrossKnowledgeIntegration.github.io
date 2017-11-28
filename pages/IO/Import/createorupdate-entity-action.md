---
title: Create Or Update Enity Action
keywords: tracking, consolidated, import, data, entity, createOrUpdateAction
last_updated: 08 November, 2017
tags:
summary: "Create or update an entity with respect to the data row from the import file."
sidebar: home_sidebar
permalink: createorupdate-entity-action.html
folder: Import
---


### Available columns

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`ignoredColumn` |  	See columnsMapping_ignoredColumn. | actionColumn | No |
`hieracrchyEntityName` |  See columnsMapping_hierarchyEntityName. | actionColumn | No |

### Filters and parameters

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`defaultEntityId` | The default value for the entity id | int | No | 1


### Examples

```xml 
<actions>
	<createOrUpdateEntityAction>
		<options>
			<defaultEntityId>1</defaultEntityId>
		</options>
		<fields>
			<hierarchyEntityName/>
			<hierarchyEntityName/>
		</fields>
	</createOrUpdateEntityAction>
</actions>
```

### Error Messages

Message | Explanation
---- | ----