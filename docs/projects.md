# Projects Endpoint
Relative URL: */v1/projects*

> Note: With the REST-API you can get and push data from projects in **WORKING** or **PUBLISHED** state. To push data, only projects in **WORKING** state are available. Use the __Project-Version__ request header to indicate the version you want to get.

## Available services
  - [Get projects](#get-projects)
  - [Get one project record](#get-one-project-record)
  - [Save projects](#save-projects)
  
---
- ### GET PROJECTS

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of project

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**:

> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | 'filter' param has an invalid value. Check your filters. |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "records": [
        {
            "object": {
                "id": "1A12SNR",
                "name": "Accounting System Migration",
                "manager1": "Alvarez, William",
                "manager2": "Carter, Agatha",
                "manager3": "Anderson, Paul",
                "startConstraint": "2017-08-06 00:00:00",
                "singleCriticalPath": false,
                "start": "1969-12-31 23:00:00",
                "finish": "2019-04-30 15:27:24",
                "performingOrganizations": [],
                "mode": "read-only",
                "levelingPriority": 50,
                "trackingSource": "Assignment Timesheet",
                "createDate": "2017-11-07 08:01:23",
                "modifiedDate": "2019-06-13 18:46:10",
                "modifiedBy": "Administrator",
                "interlinkSource": "",
                "started": true,
                "percentageCompleted": 0.9774459275728506,
                "publishedDate": "2019-05-16 10:09:43",
                "maximumTaskId": "19TESTTASK",
                "honorRequiredDates": false,
                "closed": false,
                "softAssignmentCostSource": "Organization",
                "defaultResourceAssignmentCostSource": "Resource",
                "actualsfromTrackingSourceOnly": false,
                "active": true,
                "statusTime": 2,
                "statusScope": 2,
                "strategyCompliance": "",
                "strategyAlignmentComments": "",
                "statusComments": "",
                "skillsExpertise": "",
                "statusReportMode": 0,
                "statusCost": 3,
                "technicalGap": "",
                "technicalFeasibilityMaturity": "",
                "timeTrackingMode": "<None>",
                "technologicalRisk": "",
                "technicalFeasibility": "",
                "reportSummarizeFilter": "3",
                "technicalFeasibilityComplexity": "",
                "technicalFeasibilityComment": "",
                "organizationReaders": [
                    "ABC Corporation.IT.Development"
                ]
            }
        }
    ],
    "numberOfRecords": 1
}
```
<br/>

---
- ### GET ONE PROJECT RECORD

**Method**: GET

**Path**: */{projectId}*
> Note: If you need to get/edit the **Non project** created in Sciforma, use as projectId = _non-project_

**Description**: Action to obtain one project record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project identifier | :heavy_check_mark: |

**Query parameters**

> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | 'filter' param has an invalid value. Check your filters. |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "object": {
        "id": "1A12SNR",
        "name": "Accounting System Migration",
        "manager1": "Alvarez, William",
        "manager2": "Carter, Agatha",
        "manager3": "Anderson, Paul",
        "startConstraint": "2017-08-06 00:00:00",
        "singleCriticalPath": false,
        "start": "1969-12-31 23:00:00",
        "finish": "2019-04-30 15:27:24",
        "performingOrganizations": [],
        "mode": "read-only",
        "levelingPriority": 50,
        "trackingSource": "Assignment Timesheet",
        "createDate": "2017-11-07 08:01:23",
        "modifiedDate": "2019-06-13 18:46:10",
        "modifiedBy": "Administrator",
        "interlinkSource": "",
        "started": true,
        "percentageCompleted": 0.9774459275728506,
        "publishedDate": "2019-05-16 10:09:43",
        "maximumTaskId": "19TESTTASK",
        "honorRequiredDates": false,
        "closed": false,
        "softAssignmentCostSource": "Organization",
        "defaultResourceAssignmentCostSource": "Resource",
        "actualsfromTrackingSourceOnly": false,
        "active": true,
        "statusTime": 2,
        "statusScope": 2,
        "strategyCompliance": "",
        "strategyAlignmentComments": "",
        "statusComments": "",
        "skillsExpertise": "",
        "statusReportMode": 0,
        "statusCost": 3,
        "technicalGap": "",
        "technicalFeasibilityMaturity": "",
        "timeTrackingMode": "<None>",
        "technologicalRisk": "",
        "technicalFeasibility": "",
        "reportSummarizeFilter": "3",
        "technicalFeasibilityComplexity": "",
        "technicalFeasibilityComment": "",
        "organizationReaders": [
            "ABC Corporation.IT.Development"
        ]
    }
}
```
<br/>

---

- ### SAVE PROJECTS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single project record or a list of project records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :heavy_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| id | Equivalent to the field 'ID' in sciforma's 'Project' objects. If you need to edit the **Non project** created in Sciforma, use as id = _non-project_| :heavy_check_mark: *[^1]* |
| name | Equivalent to the field 'Name' in sciforma's 'Project' objects| :heavy_check_mark: *[^1]* |
| versionID | Equivalent to the field 'Version ID' in sciforma's 'Project' objects| :x: *[^1]* |
| allocatedResources | Equivalent to the field 'allocatedResources' in sciforma's 'Project' objects| :x: *[^1]* |
| manager1 | Equivalent to the field 'Manager 1' in sciforma's 'Project' objects| :x: *[^1]* |
| manager2 | Equivalent to the field 'Manager 2' in sciforma's 'Project' objects| :x: *[^1]* |
| manager3 | Equivalent to the field 'Manager 3' in sciforma's 'Project' objects| :x: *[^1]* |
| startConstraint | Equivalent to the field 'Start Constraint' in sciforma's 'Project' objects| :x: *[^1]* |
| singleCriticalPath | Equivalent to the field 'Single Critical Path' in sciforma's 'Project' objects| :x: *[^1]* |
| start | Equivalent to the field 'Start' in sciforma's 'Project' objects| :x: *[^1]* |
| finish | Equivalent to the field 'Finish' in sciforma's 'Project' objects| :x: *[^1]* |
| performingOrganizations | Equivalent to the field 'Performing Organizations' in sciforma's 'Project' objects| :x: *[^1]* |
| mode | Equivalent to the field 'Mode' in sciforma's 'Project' objects| :x: *[^1]* |
| calendar | Equivalent to the field 'Calendar' in sciforma's 'Project' objects| :x: *[^1]* |
| levelingPriority | Equivalent to the field 'Leveling Priority' in sciforma's 'Project' objects| :x: *[^1]* |
| trackingSource | Equivalent to the field 'Tracking Source' in sciforma's 'Project' objects| :x: *[^1]* |
| actualLaborEffort | Equivalent to the field 'Actual Labor Effort' in sciforma's 'Project' objects| :x: *[^1]* |
| actualLaborCost | Equivalent to the field 'Actual Labor Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| actualCostItemCost | Equivalent to the field 'Actual Cost Item Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| actualCost | Equivalent to the field 'Actual Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| remainingLaborEffort | Equivalent to the field 'Remaining Labor Effort' in sciforma's 'Project' objects| :x: *[^1]* |
| remainingLaborCost | Equivalent to the field 'Remaining Labor Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| remainingCostItemCost | Equivalent to the field 'Remaining Cost Item Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| remainingCost | Equivalent to the field 'Remaining Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineLaborEffort | Equivalent to the field 'Baseline Labor Effort' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineLaborCost | Equivalent to the field 'Baseline Labor Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineCostItemCost | Equivalent to the field 'Baseline Cost Item Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineCost | Equivalent to the field 'Baseline Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineStart | Equivalent to the field 'Baseline Start' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineFinish | Equivalent to the field 'Baseline Finish' in sciforma's 'Project' objects| :x: *[^1]* |
| currentBaseline | Equivalent to the field 'Current Baseline' in sciforma's 'Project' objects| :x: *[^1]* |
| totalLaborCost | Equivalent to the field 'Total Labor Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| totalCostItemCost | Equivalent to the field 'Total Cost Item Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| totalLaborEffort | Equivalent to the field 'Total Labor Effort' in sciforma's 'Project' objects| :x: *[^1]* |
| totalCost | Equivalent to the field 'Total Cost' in sciforma's 'Project' objects| :x: *[^1]* |
| issues | Equivalent to the field 'Issues' in sciforma's 'Project' objects| :x: *[^1]* |
| initiator | Equivalent to the field 'Initiator' in sciforma's 'Project' objects| :x: *[^1]* |
| version | Equivalent to the field 'Version' in sciforma's 'Project' objects| :x: *[^1]* |
| asofDate | Equivalent to the field 'As of Date' in sciforma's 'Project' objects| :x: *[^1]* |
| owningOrganization | Equivalent to the field 'Owning Organization' in sciforma's 'Project' objects| :x: *[^1]* |
| approved | Equivalent to the field 'Approved' in sciforma's 'Project' objects| :x: *[^1]* |
| eVMethod | Equivalent to the field 'EV Method' in sciforma's 'Project' objects| :x: *[^1]* |
| savedStatus | Equivalent to the field 'Saved Status' in sciforma's 'Project' objects| :x: *[^1]* |
| laborACWP | Equivalent to the field 'Labor ACWP' in sciforma's 'Project' objects| :x: *[^1]* |
| costItemACWP | Equivalent to the field 'Cost Item ACWP' in sciforma's 'Project' objects| :x: *[^1]* |
| aCWP | Equivalent to the field 'ACWP' in sciforma's 'Project' objects| :x: *[^1]* |
| laborBCWS | Equivalent to the field 'Labor BCWS' in sciforma's 'Project' objects| :x: *[^1]* |
| costItemBCWS | Equivalent to the field 'Cost Item BCWS' in sciforma's 'Project' objects| :x: *[^1]* |
| bCWS | Equivalent to the field 'BCWS' in sciforma's 'Project' objects| :x: *[^1]* |
| laborBCWP | Equivalent to the field 'Labor BCWP' in sciforma's 'Project' objects| :x: *[^1]* |
| costItemBCWP | Equivalent to the field 'Cost Item BCWP' in sciforma's 'Project' objects| :x: *[^1]* |
| bCWP | Equivalent to the field 'BCWP' in sciforma's 'Project' objects| :x: *[^1]* |
| createDate | Equivalent to the field 'Create Date' in sciforma's 'Project' objects| :x: *[^1]* |
| modifiedDate | Equivalent to the field 'Modified Date' in sciforma's 'Project' objects| :x: *[^1]* |
| modifiedBy | Equivalent to the field 'Modified By' in sciforma's 'Project' objects| :x: *[^1]* |
| interlinkSource | Equivalent to the field 'Interlink Source' in sciforma's 'Project' objects| :x: *[^1]* |
| started | Equivalent to the field 'Started' in sciforma's 'Project' objects| :x: *[^1]* |
| percentageCompleted | Equivalent to the field '% Completed' in sciforma's 'Project' objects| :x: *[^1]* |
| publishedDate | Equivalent to the field 'Published Date' in sciforma's 'Project' objects| :x: *[^1]* |
| maximumTaskId | Equivalent to the field 'Maximum Task Id' in sciforma's 'Project' objects| :x: *[^1]* |
| honorRequiredDates | Equivalent to the field 'Honor Required Dates' in sciforma's 'Project' objects| :x: *[^1]* |
| closed | Equivalent to the field 'Closed' in sciforma's 'Project' objects| :x: *[^1]* |
| softAssignmentCostSource | Equivalent to the field 'Soft Assignment Cost Source' in sciforma's 'Project' objects| :x: *[^1]* |
| defaultResourceAssignmentCostSource | Equivalent to the field 'Default Resource Assignment Cost Source' in sciforma's 'Project' objects| :x: *[^1]* |
| actualsfromTrackingSourceOnly | Equivalent to the field 'Actuals from Tracking Source Only' in sciforma's 'Project' objects| :x: *[^1]* |
| active | Equivalent to the field 'Active' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline1SavedDate | Equivalent to the field 'Baseline1 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline2SavedDate | Equivalent to the field 'Baseline2 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline3SavedDate | Equivalent to the field 'Baseline3 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline4SavedDate | Equivalent to the field 'Baseline4 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline5SavedDate | Equivalent to the field 'Baseline5 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline6SavedDate | Equivalent to the field 'Baseline6 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline7SavedDate | Equivalent to the field 'Baseline7 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline8SavedDate | Equivalent to the field 'Baseline8 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline9SavedDate | Equivalent to the field 'Baseline9 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline10SavedDate | Equivalent to the field 'Baseline10 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline11SavedDate | Equivalent to the field 'Baseline11 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline12SavedDate | Equivalent to the field 'Baseline12 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline13SavedDate | Equivalent to the field 'Baseline13 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| baseline14SavedDate | Equivalent to the field 'Baseline14 Saved Date' in sciforma's 'Project' objects| :x: *[^1]* |
| parentAssignments | Equivalent to the field 'Parent Assignments' in sciforma's 'Project' objects| :x: *[^1]* |
| softAssignmentMatching | Equivalent to the field 'Soft Assignment Matching' in sciforma's 'Project' objects| :x: *[^1]* |
| portfolioFolder | Equivalent to the field 'Portfolio Folder' in sciforma's 'Project' objects| :x: *[^1]* |
| ordinalRank | Equivalent to the field 'Ordinal Rank' in sciforma's 'Project' objects| :x: *[^1]* |
| scaledRank | Equivalent to the field 'Scaled Rank' in sciforma's 'Project' objects| :x: *[^1]* |
| ordinalMetrics | Equivalent to the field 'Ordinal Metrics' in sciforma's 'Project' objects| :x: *[^1]* |
| scaledMetrics | Equivalent to the field 'Scaled Metrics' in sciforma's 'Project' objects| :x: *[^1]* |
| requestMode | Equivalent to the field 'Request Mode' in sciforma's 'Project' objects| :x: *[^1]* |
| previousPublishedDate | Equivalent to the field 'Previous Published Date' in sciforma's 'Project' objects| :x: *[^1]* |
| generationnumber | Equivalent to the field 'Generation #' in sciforma's 'Project' objects| :x: *[^1]* |
| defaultDistributionType | Equivalent to the field 'Default Distribution Type' in sciforma's 'Project' objects| :x: *[^1]* |
| permissions | Equivalent to the field 'Permissions' in sciforma's 'Project' objects| :x: *[^1]* |
| restrictAssignmentRequestOrganizations | Equivalent to the field 'Restrict Assignment/Request Organizations' in sciforma's 'Project' objects| :x: *[^1]* |
| fixedProject | Equivalent to the field 'Fixed Project' in sciforma's 'Project' objects| :x: *[^1]* |
| internalID | Equivalent to the field 'Internal ID' in sciforma's 'Project' objects| :x: *[^1]* |
| loggedinUserPermissions | Equivalent to the field 'Logged-in User's Permissions' in sciforma's 'Project' objects| :x: *[^1]* |
| reviewTimesheetBeforeApply | Equivalent to the field 'Review Timesheet Before Apply' in sciforma's 'Project' objects| :x: *[^1]* |
| reviewTimesheetBeforeApprove | Equivalent to the field 'Review Timesheet Before Approve' in sciforma's 'Project' objects| :x: *[^1]* |
| useMaximumTaskID | Equivalent to the field 'Use Maximum Task ID' in sciforma's 'Project' objects| :x: *[^1]* |
| usePromotionAnalysis | Equivalent to the field 'Use Promotion Analysis' in sciforma's 'Project' objects| :x: *[^1]* |
| type | Equivalent to the field 'Type' in sciforma's 'Project' objects| :x: *[^1]* |
| validationRule | Equivalent to the field 'Validation Rule' in sciforma's 'Project' objects| :x: *[^1]* |
| workflowHistory | Equivalent to the field 'Workflow History' in sciforma's 'Project' objects| :x: *[^1]* |
| workflowStateVote | Equivalent to the field 'Workflow State Vote' in sciforma's 'Project' objects| :x: *[^1]* |
| finishConstraint | Equivalent to the field 'Finish Constraint' in sciforma's 'Project' objects| :x: *[^1]* |
| scheduleDirection | Equivalent to the field 'Schedule Direction' in sciforma's 'Project' objects| :x: *[^1]* |
| scheduleMethod | Equivalent to the field 'Schedule Method' in sciforma's 'Project' objects| :x: *[^1]* |
| syncStartDate | Equivalent to the field 'Sync Start Date' in sciforma's 'Project' objects| :x: *[^1]* |
| syncLatestFinishDate | Equivalent to the field 'Sync Latest Finish Date' in sciforma's 'Project' objects| :x: *[^1]* |
| xmlUpdateScenario | Equivalent to the field 'XML Update Scenario' in sciforma's 'Project' objects| :x: *[^1]* |
| xmlUpdateFile | Equivalent to the field 'XML Update File' in sciforma's 'Project' objects| :x: *[^1]* |
| calendarFeeds | Equivalent to the field 'Calendar Feeds' in sciforma's 'Project' objects| :x: *[^1]* |
| outlineXFld | Equivalent to the field 'OutlineXFld' in sciforma's 'Project' objects| :x: *[^1]* |
| outlineYFld | Equivalent to the field 'OutlineYFld' in sciforma's 'Project' objects| :x: *[^1]* |
| extendedLock | Equivalent to the field 'Extended Lock' in sciforma's 'Project' objects| :x: *[^1]* |
| lockedBy | Equivalent to the field 'Locked By' in sciforma's 'Project' objects| :x: *[^1]* |
| performingResources | Equivalent to the field 'Performing Resources' in sciforma's 'Project' objects| :x: *[^1]* |
| performingCostItems | Equivalent to the field 'Performing Cost Items' in sciforma's 'Project' objects| :x: *[^1]* |
| useResourcesFrom | Equivalent to the field 'Use Resources From' in sciforma's 'Project' objects| :x: *[^1]* |
| performingUsers | Equivalent to the field 'Performing Users' in sciforma's 'Project' objects| :x: *[^1]* |
| duration | Equivalent to the field 'Duration' in sciforma's 'Project' objects| :x: *[^1]* |
| baselineDuration | Equivalent to the field 'Baseline Duration' in sciforma's 'Project' objects| :x: *[^1]* |
| sujetIssues | Equivalent to the field 'Sujet Issues' in sciforma's 'Project' objects| :x: *[^1]* |
| topicIssues | Equivalent to the field 'Topic Issues' in sciforma's 'Project' objects| :x: *[^1]* |
| standardIssues | Equivalent to the field 'Standard Issues' in sciforma's 'Project' objects| :x: *[^1]* |
| workflowConfiguration | Equivalent to the field 'workflowConfiguration' in sciforma's 'Project' objects| :x: *[^1]* |
| workflowChangeLog | Equivalent to the field 'workflowChangeLog' in sciforma's 'Project' objects| :x: *[^1]* |

> Note: In general, the user must know what are the project definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
        "id": "1A12SNR",
        "name": "Accounting System Migration",
        "manager1": "Alvarez, William",
        "manager2": "Carter, Agatha",
        "manager3": "Anderson, Paul",
        "startConstraint": "2017-08-06 00:00:00",
        "singleCriticalPath": false,
        "start": "1969-12-31 23:00:00",
        "finish": "2019-04-30 15:27:24",
        "performingOrganizations": [],
        "mode": "read-only",
        "levelingPriority": 50,
        "trackingSource": "Assignment Timesheet",
        "createDate": "2017-11-07 08:01:23",
        "modifiedDate": "2019-06-13 18:46:10",
        "modifiedBy": "Administrator",
        "interlinkSource": "",
        "started": true,
        "percentageCompleted": 0.9774459275728506,
        "publishedDate": "2019-05-16 10:09:43",
        "maximumTaskId": "19TESTTASK",
        "honorRequiredDates": false,
        "closed": false,
        "softAssignmentCostSource": "Organization",
        "defaultResourceAssignmentCostSource": "Resource",
        "actualsfromTrackingSourceOnly": false,
        "active": true,
        "statusTime": 2,
        "statusScope": 2,
        "strategyCompliance": "",
        "strategyAlignmentComments": "",
        "statusComments": "",
        "skillsExpertise": "",
        "statusReportMode": 0,
        "statusCost": 3,
        "technicalGap": "",
        "technicalFeasibilityMaturity": "",
        "timeTrackingMode": "<None>",
        "technologicalRisk": "",
        "technicalFeasibility": "",
        "reportSummarizeFilter": "3",
        "technicalFeasibilityComplexity": "",
        "technicalFeasibilityComment": "",
        "organizationReaders": [
            "ABC Corporation.IT.Development"
        ]
    }
}
```

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | There is a problem parsing the json content, check your json payload |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "records": [
        {
            "id": "JX6JJX1S",
            "status": "SUCCESS",
            "isNew": true,
            "validationMessages": [
                {
                    "status": "WARNING",
                    "message": "Field 'workPackageTaskID' is read-only. Value skipped."
                }
            ]
        }
    ]
}
```
