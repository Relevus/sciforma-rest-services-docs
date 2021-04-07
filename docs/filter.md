# Guidelines for using filters

The way how filters are built is by using the attribute code, this codes varies in each type of category, Check [definitions](definitions.md) to know which fields are available to filter.

The fields accepted to build the filter are those that have the sciforma's field 'kind' equals to 'NORMAL'. 'DISTRIBUTED', 'DATED' and 'LIST' are not accepted.

**Conditional Operators**: 

| Name | Symbol | Description | Usage |
| --- | --- | --- | :---: |
| Equal | = | Filters records when the given value is equals to sciforma attribute value | Valid for all cases |
| Not Equal | != | Filters records when the given value is not equal to sciforma attribute value | Valid for all cases |
| Greater or Equal Than | >= | Filters records when the given value is greather equals than sciforma's attribute value | Valid for those cases where the user is comparing fields of type 'String', 'Date', 'Integer', 'Double'. In the case of 'Boolean', the condition is not valid. |
| Less or Equal Than | <= | Filters records when the sciforma's attribute value is less or equals than the given value | Valid for those cases where the user is comparing fields of type 'String', 'Date', 'Integer', 'Double'. In the case of 'Boolean', the condition is not valid. |
| Greater Than | > | Filters records when the sciforma's attribute value is greather than the given value | Valid for those cases where the user is comparing fields of type 'String', 'Date', 'Integer', 'Double'. In the case of 'Boolean', the condition is not valid. |
| Less Than | < | Filters records when the sciforma's attribute value is less than the given value | Valid for those cases where the user is comparing fields of type 'String', 'Date', 'Integer', 'Double'. In the case of 'Boolean', the condition is not valid. |
| Like | like | Filters records when the sciforma's attribute value contains to the given text | Only valid when comparing a field of type 'String' |
| In | in | Filters records when the sciforma's attribute value is equal to one of the specified values. The list of values must be separated by comma (,) | Only valid when comparing a field of type 'String' |

**Boolean Operators**: 

| Name | Symbol | Description | Usage |
| --- | --- | --- | :---: |
| Or | or | It is a normal 'or' condition where both sides of the condition are inclusive | Used to link 2 conditions |
| And | and | It is a normal 'and' condition where both sides of the condition are exclusive | Used to link 2 conditions |

**Example**: 

Let's consider the following filter:

projects?filter=((('key' like '1A12SNR') or ('key' = 'JFCF8J0W'))  or (('key' = '348,206.00') and ('percentageCompleted' > '0')))

A conditional tree is built by using each condition of the filter (See image below). In the first iteration of the filter analysis, each condition enclosed by parenthesys is a leaf and each leaf condition is solved by searching the full list of sciforma objects. Once the condition is solved, each leaf is renamed and becomes a part of newer condition for a higher level of the tree, this process creates a simplified version of the tree, and the process of validating each leaf starts again recursively until all the conditions are solved and just one 'master' leaf remains, which is in fact the result of executing the full filter and it is the resulting filtered list.

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/Filter_example.PNG?raw=true" />
</p>

**Global filters**:

| Code | Description | Data type |
| --- | --- | :---: |
| distributed.fromDate | Indicates the start date to return the range of the distributed value. It requires 'toDate' filter. | Date in format yyyy-MM-dd |
| distributed.toDate | Indicates the end date to return the range of the distributed value. It requires 'fromDate' filter. | Date in format yyyy-MM-dd |



