# :memo: Customizing object definitions
The attributes of SciForma objects can be redefined in the configuration files stored in **definitions folder** (It is tipically located at *SCIFORMA_API_HOME/SCIFORMA_**VERSION**/definitions*).

> You can modify the SCIFORMA_API_HOME in the file /sciforma-commons.jar/com/rego/sciforma/commons/configuration/standalone_config.properties


The REST API loads the configuration of SciForma and mixes it with the customizations set by the administrator, if there is no customization for a particular object and attribute, the configuration loaded from SciForma will be taken.

### Steps executed by the REST-API:
1. Loads SciForma definitions of type **BUILTIN_FIELD_TYPE**

```java
//Reading the field definitions from the sciforma system data
FieldDefinitions definitions = (FieldDefinitions) session.getSystemData(SystemData.FIELD_DEFINITIONS);
		
//Getting the list of built-in fields fields for the category
List<FieldDefinition> builtInFieldList = definitions.getFieldList(category, FieldDefinitions.BUILTIN_FIELD_TYPE);
```
<br/>

2. Loads SciForma definitions of type **USER_DEFINED_FIELD_TYPE**

```java
//Getting the list of user defined fields for the category
List<FieldDefinition> usedDefinedFieldList = definitions.getFieldList(category, FieldDefinitions.USER_DEFINED_FIELD_TYPE);
```

<br/>

3. Loads the definitions made by the administrator into the configuration files. Typically these look like this:

```json
{
	"name" : "Timesheet",
	"attributes" : [
		{ "code": "remainingEstimate", "dataType": "INTEGER", "name": "Remaining Estimate", "exclude": true  },
		{ "code": "wBS", "dataType": "STRING", "name": "WBS", "exclude": true  },
		{ "code": "notes", "dataType": "INTEGER", "name": "Notes", "exclude": true  },
		{ "code": "pin", "dataType": "BOOLEAN", "name": "Pin", "exclude": true  },
		{ "code": "duration", "dataType": "INTEGER", "name": "Duration", "exclude": true  },
		{ "code": "percentageCompleted", "dataType": "DOUBLE", "name": "% Completed", "exclude": true  },
		{ "code": "weekTotals", "dataType": "STRING", "name": "Week Totals", "exclude": true  },
		{ "code": "status", "dataType": "STRING", "name": "Status", "exclude": true  },
		{ "code": "summaryStatus", "dataType": "STRING", "name": "Summary Status", "exclude": true  },
		{ "code": "remainingEffort", "dataType": "DOUBLE", "name": "Remaining Effort", "exclude": true  },
		{ "code": "variancePlan", "dataType": "DOUBLE", "name": "Variance (Plan)", "exclude": true  },
		{ "code": "varianceActuals", "dataType": "DOUBLE", "name": "Variance (Actuals)", "exclude": true  },
		{ "code": "corrections", "dataType": "DOUBLE", "name": "Corrections", "exclude": true  },
		{ "code": "hidden", "dataType": "BOOLEAN", "name": "hidden", "exclude": true  }
	]
}
```

In the previous example, some fields are hidden using the *exclude* attribute.

<br/>

Finally, you must ensure that if you add support to new objects, they must be registered in the [EnumSciformaDefinitions](../../sciforma-bom/sciforma-rest/src/main/java/com/rego/sciforma/rest/enums/EnumSciformaDefinitions.java) enumeration
