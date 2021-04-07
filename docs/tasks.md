# Tasks Endpoint
Relative URL: */v1/projects/**{projectId}**/tasks*

> Note: With the REST-API you can get and push data from projects in **WORKING** or **PUBLISHED** state. To push data, only projects in **WORKING** state are available. Use the __Project-Version__ request header to indicate the version you want to get.

## Available services
  - [Get tasks](#get-tasks)
  - [Get one task record](#get-one-task-record)
  - [Save tasks](#save-tasks)
  
---
- ### GET TASKS

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of task

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project identifier | :white_check_mark: |

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
                "id": "19EIK5P",
                "name": "Project management",
                "start": "2017-08-06 23:00:00",
                "trackingActuals": false,
                "actualStart": "2017-08-06 23:00:00",
                "actualFinish": "1969-12-31 15:59:59",
                "startNoEarlierThan": "1969-12-31 15:59:59",
                "baselineStart": "2017-08-06 23:00:00",
                "baselineFinish": "2019-03-07 06:07:17",
                "onCriticalPath": false,
                "isParent": false,
                "levelingConflict": false,
                "performingOrganizations": [],
                "issues": "",
                "physicalpercentageComplete": 0.6624747466706505,
                "lateStart": "2018-10-01 08:00:00",
                "lateFinish": "2019-04-30 15:27:24",
                "workflowStateVote": "",
                "baseline1Start": "2017-08-06 23:00:00",
                "baseline2Start": "1969-12-31 15:59:59",
                "baseline3Start": "1969-12-31 15:59:59",
                "baseline4Start": "1969-12-31 15:59:59",
                "baseline5Start": "1969-12-31 15:59:59",
                "baseline6Start": "1969-12-31 15:59:59",
                "baseline7Start": "1969-12-31 15:59:59",
                "baseline8Start": "1969-12-31 15:59:59",
                "baseline9Start": "1969-12-31 15:59:59",
                "baseline10Start": "1969-12-31 15:59:59",
                "baseline11Start": "1969-12-31 15:59:59",
                "baseline12Start": "1969-12-31 15:59:59",
                "baseline13Start": "1969-12-31 15:59:59",
                "baseline14Start": "1969-12-31 15:59:59",
                "baseline1Finish": "2019-03-07 06:07:17",
                "baseline2Finish": "1969-12-31 15:59:59",
                "baseline3Finish": "1969-12-31 15:59:59",
                "baseline4Finish": "1969-12-31 15:59:59",
                "baseline5Finish": "1969-12-31 15:59:59",
                "baseline6Finish": "1969-12-31 15:59:59",
                "baseline7Finish": "1969-12-31 15:59:59",
                "baseline8Finish": "1969-12-31 15:59:59",
                "baseline9Finish": "1969-12-31 15:59:59",
                "baseline10Finish": "1969-12-31 15:59:59",
                "baseline11Finish": "1969-12-31 15:59:59",
                "baseline12Finish": "1969-12-31 15:59:59",
                "baseline13Finish": "1969-12-31 15:59:59",
                "baseline14Finish": "1969-12-31 15:59:59",
                "showNonSummarized": false,
                "bufferLock": false,
                "bufferIncursion": "1969-12-31 15:59:59",
                "bufferIncursionGuide": "1969-12-31 15:59:59",
                "modifiedBy": "",
                "modifiedDate": "1969-12-31 15:59:59",
                "permissions": "",
                "bufferExpectedFinish": "1969-12-31 15:59:59",
                "internalID": 864441,
                "pinDate": "1969-12-31 15:59:59",
                "bufferCalculationMethod": "",
                "extendedLock": false,
                "lockedBy": "",
                "performingResources": [],
                "performingCostItems": [],
                "performingUsers": [],
                "actualLaborEffort": 603.9161660416667,
                "actualLaborCost": 38650.634626666666,
                "actualCostItemCost": 0,
                "actualCost": 38650.634626666666,
                "remainingLaborEffort": 303.61422215277776,
                "remainingLaborCost": 0,
                "remainingCostItemCost": 0,
                "remainingCost": 0,
                "totalLaborEffort": 907.5303881944444,
                "totalLaborCost": 38650.634626666666,
                "totalCostItemCost": 0,
                "totalCost": 38650.634626666666,
                "baselineLaborEffort": 827.5303881944444,
                "baselineLaborCost": 52961.94484444444,
                "baselineCostItemCost": 0,
                "baselineCost": 52961.94484444444,
                "laborACWP": 38650.634626666666,
                "costItemACWP": 0,
                "aCWP": 38650.634626666666,
                "laborBCWS": 38528,
                "costItemBCWS": 0,
                "bCWS": 38528,
                "laborBCWP": 35085.9509940083,
                "costItemBCWP": 0,
                "bCWP": 35085.9509940083,
                "percentageLaborEffortComplete": 0.6654500762703646,
                "sujetIssues": "",
                "topicIssues": "",
                "standardIssues": "",
                "number": 33,
                "wBS": "",
                "workPackageID": "",
                "description": "",
                "duration": 3614,
                "completedDuration": 1944,
                "remainingDuration": 1214,
                "manager1": "",
                "manager2": "",
                "manager3": "",
                "finish": "2019-04-30 15:27:24",
                "completedDate": "2018-10-01 08:00:00",
                "percentageCompleted": 0.6154904336385759,
                "startDelay": 0,
                "outlineLevel": 1,
                "scheduleType": "Hammock",
                "allowSplitting": true,
                "requiredDate": "1969-12-31 15:59:59",
                "requiredLabor": 0,
                "mustStartOn": "1969-12-31 15:59:59",
                "levelingPriority": 50,
                "eVMethod": "% Complete",
                "freeFloat": 0,
                "totalFloat": 0,
                "allowasInterlinkSource": false,
                "interlinkSource": "",
                "allowMyWorkAdd": true,
                "showChildLabels": false,
                "showLabelsonParent": false,
                "networkColumn": 0,
                "networkRow": 0,
                "outlineColumn": 0,
                "outlineRow": 0,
                "showChildSymbols": false,
                "showSymbolsonParent": false,
                "closed": false,
                "allowDelete": true,
                "finishDelay": 0,
                "onCriticalChain": false,
                "safeDuration": 0,
                "bufferDurationGuide": 0,
                "chainRemaining": 0,
                "originalChainLength": 0,
                "baselineDuration": 3304,
                "epicOwnerPicture": "",
                "epic": "",
                "interlinkMirroringTtoT": "Task to Task (Mirroring)",
                "interlinkConstraintTtoT": "Task to Task (External Constraint)",
                "workPackageUserWriter": [],
                "workPackageUserReader": [],
                "workPackageReportComments": "",
                "workPackagePriority": "",
                "workPackageReportImportantEvents": "",
                "workPackageReportDiscussion": "",
                "workPackageLatestFinish": "1969-12-31 15:59:59",
                "workPackageEarliestStart": "1969-12-31 15:59:59",
                "workPackageOrgWriter": "",
                "workPackageOrgReader": "",
                "workPackageTimeStatus": 0,
                "workPackageTemporaryID": "",
                "workPackagetype": "",
                "workPackageTrendStatus": 0,
                "workPackageReportMode": 0,
                "workPackageReportIsImportant": false,
                "workPackageScopeStatus": 0,
                "workPackageReportNextSteps": "",
                "menu": "",
                "manager3Picture": "",
                "mspFinish": "1969-12-31 15:59:59",
                "mspPctCompleted": 0,
                "iterationOwnerPicture": "",
                "iteration": "",
                "manager2Picture": "",
                "manager1picture": "",
                "workPackageContractLock": false,
                "filterTaskLevel": "2",
                "workPackageDescription": "",
                "workPackageCostStatus": 0,
                "release": "",
                "mspStart": "1969-12-31 15:59:59",
                "workPackageReportRisksFilter": "",
                "releaseOwnerPicture": "",
                "ganttSoftAssignment": "",
                "ganttHardAssignmentRate": 1,
                "ganttWatchList": false,
                "ganttSoftAssignmentRate": 1,
                "ganttFlagged": "",
                "exportToMSP": false,
                "ganttHardAssignment": "",
                "ganttCostItemAssignmentInternalID": 0,
                "interlinkPID": "",
                "interlinkMap": "",
                "workPackageReportIssuesFilter": "",
                "interlinkTID": "",
                "workPackageReportIncludeIssues": false,
                "workPackageReportIncludeBudget": false,
                "workPackageReportIncludeRisks": false,
                "workPackageReportIncludePlanning": false,
                "includeMilestones": false,
                "includeFlaggedTasks": false,
                "deliverablesTaskAlerts": false,
                "deliverablesDateAlerts": false,
                "workPackageReportEcoMode": false,
                "deliverablesWorkflowAlerts": false,
                "workPackageContractStart": "1969-12-31 15:59:59",
                "workPackageContractFinish": "1969-12-31 15:59:59",
                "deliverableID": 0,
                "costCenter": "INFORMATION",
                "taskPriority": "",
                "taskText": "",
                "workPackageReportDecisions": "",
                "additionalIndicator2": 0,
                "workPackageReportMeetingAttendees": "",
                "contractDescription": "",
                "additionalIndicator1": 0,
                "workPackageDeliverablesFilter": "",
                "relatedPhases": [],
                "workPackageReportIncludeDeliverables": false,
                "contract": false,
                "dependenciespercentageCompleted": 0,
                "dependenciesOwner": "",
                "dependenciesStart": "1969-12-31 15:59:59",
                "dependenciesFinish": "1969-12-31 15:59:59",
                "dependenciesTotalCost": 0,
                "dependenciesTotalEffort": 0
            }
        },
        {
            "object": {
                "id": "19EIK5D",
                "name": "Design",
                "start": "2017-08-06 23:00:00",
                "trackingActuals": false,
                "actualStart": "2017-08-06 23:00:00",
                "actualFinish": "2017-10-20 08:00:00",
                "startNoEarlierThan": "1969-12-31 15:59:59",
                "baselineStart": "2017-08-06 23:00:00",
                "baselineFinish": "2017-10-20 08:00:00",
                "onCriticalPath": false,
                "isParent": true,
                "levelingConflict": false,
                "performingOrganizations": [],
                "issues": "",
                "physicalpercentageComplete": 1,
                "lateStart": "2017-08-06 23:00:00",
                "lateFinish": "2018-10-01 08:00:00",
                "workflowStateVote": "New",
                "baseline1Start": "2017-08-06 23:00:00",
                "baseline2Start": "1969-12-31 15:59:59",
                "baseline3Start": "1969-12-31 15:59:59",
                "baseline4Start": "1969-12-31 15:59:59",
                "baseline5Start": "1969-12-31 15:59:59",
                "baseline6Start": "1969-12-31 15:59:59",
                "baseline7Start": "1969-12-31 15:59:59",
                "baseline8Start": "1969-12-31 15:59:59",
                "baseline9Start": "1969-12-31 15:59:59",
                "baseline10Start": "1969-12-31 15:59:59",
                "baseline11Start": "1969-12-31 15:59:59",
                "baseline12Start": "1969-12-31 15:59:59",
                "baseline13Start": "1969-12-31 15:59:59",
                "baseline14Start": "1969-12-31 15:59:59",
                "baseline1Finish": "2017-10-20 08:00:00",
                "baseline2Finish": "1969-12-31 15:59:59",
                "baseline3Finish": "1969-12-31 15:59:59",
                "baseline4Finish": "1969-12-31 15:59:59",
                "baseline5Finish": "1969-12-31 15:59:59",
                "baseline6Finish": "1969-12-31 15:59:59",
                "baseline7Finish": "1969-12-31 15:59:59",
                "baseline8Finish": "1969-12-31 15:59:59",
                "baseline9Finish": "1969-12-31 15:59:59",
                "baseline10Finish": "1969-12-31 15:59:59",
                "baseline11Finish": "1969-12-31 15:59:59",
                "baseline12Finish": "1969-12-31 15:59:59",
                "baseline13Finish": "1969-12-31 15:59:59",
                "baseline14Finish": "1969-12-31 15:59:59",
                "showNonSummarized": false,
                "bufferLock": false,
                "bufferIncursion": "1969-12-31 15:59:59",
                "bufferIncursionGuide": "1969-12-31 15:59:59",
                "modifiedBy": "Administrator",
                "modifiedDate": "2019-06-13 18:46:10",
                "permissions": "Work Package Permissions",
                "bufferExpectedFinish": "1969-12-31 15:59:59",
                "internalID": 763656,
                "pinDate": "1969-12-31 15:59:59",
                "bufferCalculationMethod": "",
                "extendedLock": false,
                "lockedBy": "",
                "performingResources": [],
                "performingCostItems": [],
                "performingUsers": [],
                "actualLaborEffort": 1580,
                "actualLaborCost": 181280,
                "actualCostItemCost": 0,
                "actualCost": 181280,
                "remainingLaborEffort": 0,
                "remainingLaborCost": 0,
                "remainingCostItemCost": 0,
                "remainingCost": 0,
                "totalLaborEffort": 1580,
                "totalLaborCost": 181280,
                "totalCostItemCost": 0,
                "totalCost": 181280,
                "baselineLaborEffort": 1580,
                "baselineLaborCost": 181280,
                "baselineCostItemCost": 0,
                "baselineCost": 181280,
                "laborACWP": 181280,
                "costItemACWP": 0,
                "aCWP": 181280,
                "laborBCWS": 181280,
                "costItemBCWS": 0,
                "bCWS": 181280,
                "laborBCWP": 181280,
                "costItemBCWP": 0,
                "bCWP": 181280,
                "percentageLaborEffortComplete": 1,
                "sujetIssues": "",
                "topicIssues": "",
                "standardIssues": "",
                "number": 21,
                "wBS": "",
                "workPackageID": "001",
                "description": "",
                "duration": 432,
                "completedDuration": 352,
                "remainingDuration": 0,
                "manager1": "Abberline, Denise",
                "manager2": "",
                "manager3": "",
                "finish": "2017-10-20 08:00:00",
                "completedDate": "2017-10-20 08:00:00",
                "percentageCompleted": 1,
                "startDelay": 0,
                "outlineLevel": 1,
                "scheduleType": "ASAP",
                "allowSplitting": true,
                "requiredDate": "1969-12-31 15:59:59",
                "requiredLabor": 0,
                "mustStartOn": "1969-12-31 15:59:59",
                "levelingPriority": 50,
                "eVMethod": "% Complete",
                "freeFloat": 0,
                "totalFloat": 0,
                "allowasInterlinkSource": true,
                "interlinkSource": "",
                "allowMyWorkAdd": true,
                "showChildLabels": false,
                "showLabelsonParent": false,
                "networkColumn": 0,
                "networkRow": 0,
                "outlineColumn": 0,
                "outlineRow": 0,
                "showChildSymbols": false,
                "showSymbolsonParent": false,
                "closed": false,
                "allowDelete": true,
                "finishDelay": 0,
                "onCriticalChain": false,
                "safeDuration": 0,
                "bufferDurationGuide": 0,
                "chainRemaining": 0,
                "originalChainLength": 0,
                "baselineDuration": 432,
                "epicOwnerPicture": "",
                "epic": "",
                "interlinkMirroringTtoT": "Task to Task (Mirroring)",
                "interlinkConstraintTtoT": "Task to Task (External Constraint)",
                "workPackageUserWriter": [],
                "workPackageUserReader": [],
                "workPackageReportComments": "",
                "workPackagePriority": "",
                "workPackageReportImportantEvents": "",
                "workPackageReportDiscussion": "",
                "workPackageLatestFinish": "1969-12-31 15:59:59",
                "workPackageEarliestStart": "1969-12-31 15:59:59",
                "workPackageOrgWriter": "",
                "workPackageOrgReader": "",
                "workPackageTimeStatus": 0,
                "workPackageTemporaryID": "001",
                "workPackagetype": "",
                "workPackageTrendStatus": 0,
                "workPackageReportMode": 0,
                "workPackageReportIsImportant": false,
                "workPackageScopeStatus": 0,
                "workPackageReportNextSteps": "",
                "menu": "",
                "manager3Picture": "",
                "mspFinish": "1969-12-31 15:59:59",
                "mspPctCompleted": 0,
                "iterationOwnerPicture": "",
                "iteration": "",
                "manager2Picture": "",
                "manager1picture": "/tmp/tomcat8-tomcat8-tmp/sci9106478647655195777.png",
                "workPackageContractLock": false,
                "filterTaskLevel": "2",
                "workPackageDescription": "",
                "workPackageCostStatus": 0,
                "release": "",
                "mspStart": "1969-12-31 15:59:59",
                "workPackageReportRisksFilter": "",
                "releaseOwnerPicture": "",
                "ganttSoftAssignment": "",
                "ganttHardAssignmentRate": 1,
                "ganttWatchList": false,
                "ganttSoftAssignmentRate": 1,
                "ganttFlagged": "",
                "exportToMSP": false,
                "ganttHardAssignment": "",
                "ganttCostItemAssignmentInternalID": 0,
                "interlinkPID": "",
                "interlinkMap": "",
                "workPackageReportIssuesFilter": "",
                "interlinkTID": "",
                "workPackageReportIncludeIssues": false,
                "workPackageReportIncludeBudget": false,
                "workPackageReportIncludeRisks": false,
                "workPackageReportIncludePlanning": false,
                "includeMilestones": false,
                "includeFlaggedTasks": false,
                "deliverablesTaskAlerts": false,
                "deliverablesDateAlerts": false,
                "workPackageReportEcoMode": false,
                "deliverablesWorkflowAlerts": false,
                "workPackageContractStart": "1969-12-31 15:59:59",
                "workPackageContractFinish": "1969-12-31 15:59:59",
                "deliverableID": 0,
                "costCenter": "",
                "taskPriority": "",
                "taskText": "",
                "workPackageReportDecisions": "",
                "additionalIndicator2": 0,
                "workPackageReportMeetingAttendees": "",
                "contractDescription": "",
                "additionalIndicator1": 0,
                "workPackageDeliverablesFilter": "",
                "relatedPhases": [],
                "workPackageReportIncludeDeliverables": false,
                "contract": false,
                "dependenciespercentageCompleted": 0,
                "dependenciesOwner": "",
                "dependenciesStart": "1969-12-31 15:59:59",
                "dependenciesFinish": "1969-12-31 15:59:59",
                "dependenciesTotalCost": 0,
                "dependenciesTotalEffort": 0
            }
        }
    ],
    "numberOfRecords": 2
}
```
<br/>

---
- ### GET ONE TASK RECORD

**Method**: GET

**Path**: */{taskId}*

**Description**: Action to obtain one task record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project identifier | :white_check_mark: |
| taskId | Task identifier | :white_check_mark: |

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
        "id": "19EIK5P",
        "name": "Project management",
        "start": "2017-08-06 23:00:00",
        "trackingActuals": false,
        "actualStart": "2017-08-06 23:00:00",
        "actualFinish": "1969-12-31 15:59:59",
        "startNoEarlierThan": "1969-12-31 15:59:59",
        "baselineStart": "2017-08-06 23:00:00",
        "baselineFinish": "2019-03-07 06:07:17",
        "onCriticalPath": false,
        "isParent": false,
        "levelingConflict": false,
        "performingOrganizations": [],
        "issues": "",
        "physicalpercentageComplete": 0.6624747466706505,
        "lateStart": "2018-10-01 08:00:00",
        "lateFinish": "2019-04-30 15:27:24",
        "workflowStateVote": "",
        "baseline1Start": "2017-08-06 23:00:00",
        "baseline2Start": "1969-12-31 15:59:59",
        "baseline3Start": "1969-12-31 15:59:59",
        "baseline4Start": "1969-12-31 15:59:59",
        "baseline5Start": "1969-12-31 15:59:59",
        "baseline6Start": "1969-12-31 15:59:59",
        "baseline7Start": "1969-12-31 15:59:59",
        "baseline8Start": "1969-12-31 15:59:59",
        "baseline9Start": "1969-12-31 15:59:59",
        "baseline10Start": "1969-12-31 15:59:59",
        "baseline11Start": "1969-12-31 15:59:59",
        "baseline12Start": "1969-12-31 15:59:59",
        "baseline13Start": "1969-12-31 15:59:59",
        "baseline14Start": "1969-12-31 15:59:59",
        "baseline1Finish": "2019-03-07 06:07:17",
        "baseline2Finish": "1969-12-31 15:59:59",
        "baseline3Finish": "1969-12-31 15:59:59",
        "baseline4Finish": "1969-12-31 15:59:59",
        "baseline5Finish": "1969-12-31 15:59:59",
        "baseline6Finish": "1969-12-31 15:59:59",
        "baseline7Finish": "1969-12-31 15:59:59",
        "baseline8Finish": "1969-12-31 15:59:59",
        "baseline9Finish": "1969-12-31 15:59:59",
        "baseline10Finish": "1969-12-31 15:59:59",
        "baseline11Finish": "1969-12-31 15:59:59",
        "baseline12Finish": "1969-12-31 15:59:59",
        "baseline13Finish": "1969-12-31 15:59:59",
        "baseline14Finish": "1969-12-31 15:59:59",
        "showNonSummarized": false,
        "bufferLock": false,
        "bufferIncursion": "1969-12-31 15:59:59",
        "bufferIncursionGuide": "1969-12-31 15:59:59",
        "modifiedBy": "",
        "modifiedDate": "1969-12-31 15:59:59",
        "permissions": "",
        "bufferExpectedFinish": "1969-12-31 15:59:59",
        "internalID": 864441,
        "pinDate": "1969-12-31 15:59:59",
        "bufferCalculationMethod": "",
        "extendedLock": false,
        "lockedBy": "",
        "performingResources": [],
        "performingCostItems": [],
        "performingUsers": [],
        "actualLaborEffort": 603.9161660416667,
        "actualLaborCost": 38650.634626666666,
        "actualCostItemCost": 0,
        "actualCost": 38650.634626666666,
        "remainingLaborEffort": 303.61422215277776,
        "remainingLaborCost": 0,
        "remainingCostItemCost": 0,
        "remainingCost": 0,
        "totalLaborEffort": 907.5303881944444,
        "totalLaborCost": 38650.634626666666,
        "totalCostItemCost": 0,
        "totalCost": 38650.634626666666,
        "baselineLaborEffort": 827.5303881944444,
        "baselineLaborCost": 52961.94484444444,
        "baselineCostItemCost": 0,
        "baselineCost": 52961.94484444444,
        "laborACWP": 38650.634626666666,
        "costItemACWP": 0,
        "aCWP": 38650.634626666666,
        "laborBCWS": 38528,
        "costItemBCWS": 0,
        "bCWS": 38528,
        "laborBCWP": 35085.9509940083,
        "costItemBCWP": 0,
        "bCWP": 35085.9509940083,
        "percentageLaborEffortComplete": 0.6654500762703646,
        "sujetIssues": "",
        "topicIssues": "",
        "standardIssues": "",
        "number": 33,
        "wBS": "",
        "workPackageID": "",
        "description": "",
        "duration": 3614,
        "completedDuration": 1944,
        "remainingDuration": 1214,
        "manager1": "",
        "manager2": "",
        "manager3": "",
        "finish": "2019-04-30 15:27:24",
        "completedDate": "2018-10-01 08:00:00",
        "percentageCompleted": 0.6154904336385759,
        "startDelay": 0,
        "outlineLevel": 1,
        "scheduleType": "Hammock",
        "allowSplitting": true,
        "requiredDate": "1969-12-31 15:59:59",
        "requiredLabor": 0,
        "mustStartOn": "1969-12-31 15:59:59",
        "levelingPriority": 50,
        "eVMethod": "% Complete",
        "freeFloat": 0,
        "totalFloat": 0,
        "allowasInterlinkSource": false,
        "interlinkSource": "",
        "allowMyWorkAdd": true,
        "showChildLabels": false,
        "showLabelsonParent": false,
        "networkColumn": 0,
        "networkRow": 0,
        "outlineColumn": 0,
        "outlineRow": 0,
        "showChildSymbols": false,
        "showSymbolsonParent": false,
        "closed": false,
        "allowDelete": true,
        "finishDelay": 0,
        "onCriticalChain": false,
        "safeDuration": 0,
        "bufferDurationGuide": 0,
        "chainRemaining": 0,
        "originalChainLength": 0,
        "baselineDuration": 3304,
        "epicOwnerPicture": "",
        "epic": "",
        "interlinkMirroringTtoT": "Task to Task (Mirroring)",
        "interlinkConstraintTtoT": "Task to Task (External Constraint)",
        "workPackageUserWriter": [],
        "workPackageUserReader": [],
        "workPackageReportComments": "",
        "workPackagePriority": "",
        "workPackageReportImportantEvents": "",
        "workPackageReportDiscussion": "",
        "workPackageLatestFinish": "1969-12-31 15:59:59",
        "workPackageEarliestStart": "1969-12-31 15:59:59",
        "workPackageOrgWriter": "",
        "workPackageOrgReader": "",
        "workPackageTimeStatus": 0,
        "workPackageTemporaryID": "",
        "workPackagetype": "",
        "workPackageTrendStatus": 0,
        "workPackageReportMode": 0,
        "workPackageReportIsImportant": false,
        "workPackageScopeStatus": 0,
        "workPackageReportNextSteps": "",
        "menu": "",
        "manager3Picture": "",
        "mspFinish": "1969-12-31 15:59:59",
        "mspPctCompleted": 0,
        "iterationOwnerPicture": "",
        "iteration": "",
        "manager2Picture": "",
        "manager1picture": "",
        "workPackageContractLock": false,
        "filterTaskLevel": "2",
        "workPackageDescription": "",
        "workPackageCostStatus": 0,
        "release": "",
        "mspStart": "1969-12-31 15:59:59",
        "workPackageReportRisksFilter": "",
        "releaseOwnerPicture": "",
        "ganttSoftAssignment": "",
        "ganttHardAssignmentRate": 1,
        "ganttWatchList": false,
        "ganttSoftAssignmentRate": 1,
        "ganttFlagged": "",
        "exportToMSP": false,
        "ganttHardAssignment": "",
        "ganttCostItemAssignmentInternalID": 0,
        "interlinkPID": "",
        "interlinkMap": "",
        "workPackageReportIssuesFilter": "",
        "interlinkTID": "",
        "workPackageReportIncludeIssues": false,
        "workPackageReportIncludeBudget": false,
        "workPackageReportIncludeRisks": false,
        "workPackageReportIncludePlanning": false,
        "includeMilestones": false,
        "includeFlaggedTasks": false,
        "deliverablesTaskAlerts": false,
        "deliverablesDateAlerts": false,
        "workPackageReportEcoMode": false,
        "deliverablesWorkflowAlerts": false,
        "workPackageContractStart": "1969-12-31 15:59:59",
        "workPackageContractFinish": "1969-12-31 15:59:59",
        "deliverableID": 0,
        "costCenter": "INFORMATION",
        "taskPriority": "",
        "taskText": "",
        "workPackageReportDecisions": "",
        "additionalIndicator2": 0,
        "workPackageReportMeetingAttendees": "",
        "contractDescription": "",
        "additionalIndicator1": 0,
        "workPackageDeliverablesFilter": "",
        "relatedPhases": [],
        "workPackageReportIncludeDeliverables": false,
        "contract": false,
        "dependenciespercentageCompleted": 0,
        "dependenciesOwner": "",
        "dependenciesStart": "1969-12-31 15:59:59",
        "dependenciesFinish": "1969-12-31 15:59:59",
        "dependenciesTotalCost": 0,
        "dependenciesTotalEffort": 0
    }
}
```
<br/>

---

- ### SAVE TASKS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single task record or a list of task records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project identifier | :white_check_mark: |

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| id | Equivalent to the field 'ID' in sciforma's 'Task' objects| :x: *[^1]* |
| name | Equivalent to the field 'Name' in sciforma's 'Task' objects| :x: *[^1]* |
| versionID | Equivalent to the field 'Version ID' in sciforma's 'Task' objects| :x: *[^1]* |
| predecessorList | Please use the taskIDs, enclosed in double quotes and separated by commas (e.g: ["19EIK5P", "19EIK5Q"] ) | :x: *[^1]* |
| resourcenumbers | Equivalent to the field 'Resource #s' in sciforma's 'Task' objects| :x: *[^1]* |
| resourceNames | Equivalent to the field 'Resource Names' in sciforma's 'Task' objects| :x: *[^1]* |
| start | Equivalent to the field 'Start' in sciforma's 'Task' objects| :x: *[^1]* |
| trackingActuals | Equivalent to the field 'Tracking Actuals' in sciforma's 'Task' objects| :x: *[^1]* |
| actualStart | Equivalent to the field 'Actual Start' in sciforma's 'Task' objects| :x: *[^1]* |
| actualFinish | Equivalent to the field 'Actual Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| startNoEarlierThan | Equivalent to the field 'Start No Earlier Than' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineStart | Equivalent to the field 'Baseline Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineFinish | Equivalent to the field 'Baseline Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| onCriticalPath | Equivalent to the field 'On Critical Path' in sciforma's 'Task' objects| :x: *[^1]* |
| isParent | Equivalent to the field 'Is Parent' in sciforma's 'Task' objects| :x: *[^1]* |
| levelingConflict | Equivalent to the field 'Leveling Conflict' in sciforma's 'Task' objects| :x: *[^1]* |
| performingOrganizations | Equivalent to the field 'Performing Organizations' in sciforma's 'Task' objects| :x: *[^1]* |
| issues | Equivalent to the field 'Issues' in sciforma's 'Task' objects| :x: *[^1]* |
| physicalpercentageComplete | Equivalent to the field 'Physical % Complete' in sciforma's 'Task' objects| :x: *[^1]* |
| lateStart | Equivalent to the field 'Late Start' in sciforma's 'Task' objects| :x: *[^1]* |
| lateFinish | Equivalent to the field 'Late Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| workflowStateVote | Equivalent to the field 'Workflow State Vote' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline1Start | Equivalent to the field 'Baseline1 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline2Start | Equivalent to the field 'Baseline2 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline3Start | Equivalent to the field 'Baseline3 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline4Start | Equivalent to the field 'Baseline4 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline5Start | Equivalent to the field 'Baseline5 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline6Start | Equivalent to the field 'Baseline6 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline7Start | Equivalent to the field 'Baseline7 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline8Start | Equivalent to the field 'Baseline8 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline9Start | Equivalent to the field 'Baseline9 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline10Start | Equivalent to the field 'Baseline10 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline11Start | Equivalent to the field 'Baseline11 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline12Start | Equivalent to the field 'Baseline12 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline13Start | Equivalent to the field 'Baseline13 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline14Start | Equivalent to the field 'Baseline14 Start' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline1Finish | Equivalent to the field 'Baseline1 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline2Finish | Equivalent to the field 'Baseline2 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline3Finish | Equivalent to the field 'Baseline3 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline4Finish | Equivalent to the field 'Baseline4 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline5Finish | Equivalent to the field 'Baseline5 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline6Finish | Equivalent to the field 'Baseline6 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline7Finish | Equivalent to the field 'Baseline7 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline8Finish | Equivalent to the field 'Baseline8 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline9Finish | Equivalent to the field 'Baseline9 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline10Finish | Equivalent to the field 'Baseline10 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline11Finish | Equivalent to the field 'Baseline11 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline12Finish | Equivalent to the field 'Baseline12 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline13Finish | Equivalent to the field 'Baseline13 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| baseline14Finish | Equivalent to the field 'Baseline14 Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| showNonSummarized | Equivalent to the field 'Show Non-Summarized' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferLock | Equivalent to the field 'Buffer Lock' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferIncursion | Equivalent to the field 'Buffer Incursion' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferIncursionGuide | Equivalent to the field 'Buffer Incursion Guide' in sciforma's 'Task' objects| :x: *[^1]* |
| modifiedBy | Equivalent to the field 'Modified By' in sciforma's 'Task' objects| :x: *[^1]* |
| modifiedDate | Equivalent to the field 'Modified Date' in sciforma's 'Task' objects| :x: *[^1]* |
| permissions | Equivalent to the field 'Permissions' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferExpectedFinish | Equivalent to the field 'Buffer Expected Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| internalID | Equivalent to the field 'Internal ID' in sciforma's 'Task' objects| :x: *[^1]* |
| pinDate | Equivalent to the field 'Pin Date' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferCalculationMethod | Equivalent to the field 'Buffer Calculation Method' in sciforma's 'Task' objects| :x: *[^1]* |
| extendedLock | Equivalent to the field 'Extended Lock' in sciforma's 'Task' objects| :x: *[^1]* |
| lockedBy | Equivalent to the field 'Locked By' in sciforma's 'Task' objects| :x: *[^1]* |
| performingResources | Equivalent to the field 'Performing Resources' in sciforma's 'Task' objects| :x: *[^1]* |
| performingCostItems | Equivalent to the field 'Performing Cost Items' in sciforma's 'Task' objects| :x: *[^1]* |
| performingUsers | Equivalent to the field 'Performing Users' in sciforma's 'Task' objects| :x: *[^1]* |
| actualLaborEffort | Equivalent to the field 'Actual Labor Effort' in sciforma's 'Task' objects| :x: *[^1]* |
| actualLaborCost | Equivalent to the field 'Actual Labor Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| actualCostItemCost | Equivalent to the field 'Actual Cost Item Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| actualCost | Equivalent to the field 'Actual Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| remainingLaborEffort | Equivalent to the field 'Remaining Labor Effort' in sciforma's 'Task' objects| :x: *[^1]* |
| remainingLaborCost | Equivalent to the field 'Remaining Labor Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| remainingCostItemCost | Equivalent to the field 'Remaining Cost Item Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| remainingCost | Equivalent to the field 'Remaining Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| totalLaborEffort | Equivalent to the field 'Total Labor Effort' in sciforma's 'Task' objects| :x: *[^1]* |
| totalLaborCost | Equivalent to the field 'Total Labor Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| totalCostItemCost | Equivalent to the field 'Total Cost Item Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| totalCost | Equivalent to the field 'Total Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineLaborEffort | Equivalent to the field 'Baseline Labor Effort' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineLaborCost | Equivalent to the field 'Baseline Labor Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineCostItemCost | Equivalent to the field 'Baseline Cost Item Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineCost | Equivalent to the field 'Baseline Cost' in sciforma's 'Task' objects| :x: *[^1]* |
| laborACWP | Equivalent to the field 'Labor ACWP' in sciforma's 'Task' objects| :x: *[^1]* |
| costItemACWP | Equivalent to the field 'Cost Item ACWP' in sciforma's 'Task' objects| :x: *[^1]* |
| aCWP | Equivalent to the field 'ACWP' in sciforma's 'Task' objects| :x: *[^1]* |
| laborBCWS | Equivalent to the field 'Labor BCWS' in sciforma's 'Task' objects| :x: *[^1]* |
| costItemBCWS | Equivalent to the field 'Cost Item BCWS' in sciforma's 'Task' objects| :x: *[^1]* |
| bCWS | Equivalent to the field 'BCWS' in sciforma's 'Task' objects| :x: *[^1]* |
| laborBCWP | Equivalent to the field 'Labor BCWP' in sciforma's 'Task' objects| :x: *[^1]* |
| costItemBCWP | Equivalent to the field 'Cost Item BCWP' in sciforma's 'Task' objects| :x: *[^1]* |
| bCWP | Equivalent to the field 'BCWP' in sciforma's 'Task' objects| :x: *[^1]* |
| percentageLaborEffortComplete | Equivalent to the field '% Labor Effort Complete' in sciforma's 'Task' objects| :x: *[^1]* |
| sujetIssues | Equivalent to the field 'Sujet Issues' in sciforma's 'Task' objects| :x: *[^1]* |
| topicIssues | Equivalent to the field 'Topic Issues' in sciforma's 'Task' objects| :x: *[^1]* |
| standardIssues | Equivalent to the field 'Standard Issues' in sciforma's 'Task' objects| :x: *[^1]* |
| number | Equivalent to the field '#' in sciforma's 'Task' objects| :x: *[^1]* |
| wBS | Equivalent to the field 'WBS' in sciforma's 'Task' objects| :x: *[^1]* |
| workPackageID | Equivalent to the field 'Work Package ID' in sciforma's 'Task' objects| :x: *[^1]* |
| description | Equivalent to the field 'Description' in sciforma's 'Task' objects| :x: *[^1]* |
| duration | Equivalent to the field 'Duration' in sciforma's 'Task' objects| :x: *[^1]* |
| completedDuration | Equivalent to the field 'Completed Duration' in sciforma's 'Task' objects| :x: *[^1]* |
| remainingDuration | Equivalent to the field 'Remaining Duration' in sciforma's 'Task' objects| :x: *[^1]* |
| manager1 | Equivalent to the field 'Manager 1' in sciforma's 'Task' objects| :x: *[^1]* |
| manager2 | Equivalent to the field 'Manager 2' in sciforma's 'Task' objects| :x: *[^1]* |
| manager3 | Equivalent to the field 'Manager 3' in sciforma's 'Task' objects| :x: *[^1]* |
| finish | Equivalent to the field 'Finish' in sciforma's 'Task' objects| :x: *[^1]* |
| completedDate | Equivalent to the field 'Completed Date' in sciforma's 'Task' objects| :x: *[^1]* |
| percentageCompleted | Equivalent to the field '% Completed' in sciforma's 'Task' objects| :x: *[^1]* |
| startDelay | Equivalent to the field 'Start Delay' in sciforma's 'Task' objects| :x: *[^1]* |
| outlineLevel | Equivalent to the field 'Outline Level' in sciforma's 'Task' objects| :x: *[^1]* |
| scheduleType | Equivalent to the field 'Schedule Type' in sciforma's 'Task' objects| :x: *[^1]* |
| allowSplitting | Equivalent to the field 'Allow Splitting' in sciforma's 'Task' objects| :x: *[^1]* |
| requiredDate | Equivalent to the field 'Required Date' in sciforma's 'Task' objects| :x: *[^1]* |
| requiredLabor | Equivalent to the field 'Required Labor' in sciforma's 'Task' objects| :x: *[^1]* |
| mustStartOn | Equivalent to the field 'Must Start On' in sciforma's 'Task' objects| :x: *[^1]* |
| levelingPriority | Equivalent to the field 'Leveling Priority' in sciforma's 'Task' objects| :x: *[^1]* |
| eVMethod | Equivalent to the field 'EV Method' in sciforma's 'Task' objects| :x: *[^1]* |
| freeFloat | Equivalent to the field 'Free Float' in sciforma's 'Task' objects| :x: *[^1]* |
| totalFloat | Equivalent to the field 'Total Float' in sciforma's 'Task' objects| :x: *[^1]* |
| calendar | Equivalent to the field 'Calendar' in sciforma's 'Task' objects| :x: *[^1]* |
| allowasInterlinkSource | Equivalent to the field 'Allow as Interlink Source' in sciforma's 'Task' objects| :x: *[^1]* |
| interlinkSource | Equivalent to the field 'Interlink Source' in sciforma's 'Task' objects| :x: *[^1]* |
| allowMyWorkAdd | Equivalent to the field 'Allow My Work Add' in sciforma's 'Task' objects| :x: *[^1]* |
| summarizeSpan | Equivalent to the field 'Summarize Span' in sciforma's 'Task' objects| :x: *[^1]* |
| showChildLabels | Equivalent to the field 'Show Child Labels' in sciforma's 'Task' objects| :x: *[^1]* |
| showLabelsonParent | Equivalent to the field 'Show Labels on Parent' in sciforma's 'Task' objects| :x: *[^1]* |
| networkColumn | Equivalent to the field 'Network Column' in sciforma's 'Task' objects| :x: *[^1]* |
| networkRow | Equivalent to the field 'Network Row' in sciforma's 'Task' objects| :x: *[^1]* |
| outlineColumn | Equivalent to the field 'Outline Column' in sciforma's 'Task' objects| :x: *[^1]* |
| outlineRow | Equivalent to the field 'Outline Row' in sciforma's 'Task' objects| :x: *[^1]* |
| showChildSymbols | Equivalent to the field 'Show Child Symbols' in sciforma's 'Task' objects| :x: *[^1]* |
| showSymbolsonParent | Equivalent to the field 'Show Symbols on Parent' in sciforma's 'Task' objects| :x: *[^1]* |
| closed | Equivalent to the field 'Closed' in sciforma's 'Task' objects| :x: *[^1]* |
| allowDelete | Equivalent to the field 'Allow Delete' in sciforma's 'Task' objects| :x: *[^1]* |
| finishDelay | Equivalent to the field 'Finish Delay' in sciforma's 'Task' objects| :x: *[^1]* |
| onCriticalChain | Equivalent to the field 'On Critical Chain' in sciforma's 'Task' objects| :x: *[^1]* |
| safeDuration | Equivalent to the field 'Safe Duration' in sciforma's 'Task' objects| :x: *[^1]* |
| bufferDurationGuide | Equivalent to the field 'Buffer Duration Guide' in sciforma's 'Task' objects| :x: *[^1]* |
| chainRemaining | Equivalent to the field 'Chain Remaining' in sciforma's 'Task' objects| :x: *[^1]* |
| originalChainLength | Equivalent to the field 'Original Chain Length' in sciforma's 'Task' objects| :x: *[^1]* |
| baselineDuration | Equivalent to the field 'Baseline Duration' in sciforma's 'Task' objects| :x: *[^1]* |
| workflowConfiguration | Equivalent to the field 'workflowConfiguration' in sciforma's 'Task' objects| :x: *[^1]* |
| workflowChangeLog | Equivalent to the field 'workflowChangeLog' in sciforma's 'Task' objects| :x: *[^1]* |

> Note: In general, the user must know what are the task definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
    	"id": "19TESTTASK",
        "workPackageCostStatus": 0,
        "interlinkSource": "",
        "actualLaborEffort": 603.9161660416667,
        "workPackageReportIssuesFilter": "",
        "baseline10Start": "1969-12-31 06:59:59",
        "showSymbolsonParent": false,
        "bufferLock": false,
        "workPackageLatestFinish": "1969-12-31 06:59:59",
        "onCriticalPath": false,
        "remainingDuration": 1214,
        "workPackageReportIsImportant": false,
        "showLabelsonParent": false,
        "baseline12Start": "1969-12-31 06:59:59",
        "topicIssues": "",
        "costItemACWP": 0,
        "interlinkConstraintTtoT": "Task to Task (External Constraint)",
        "costCenter": "INFORMATION",
        "laborBCWP": 35085.9509940083,
        "baseline7Start": "1969-12-31 06:59:59",
        "workflowStateVote": "",
        "startNoEarlierThan": "1969-12-31 06:59:59",
        "ganttHardAssignmentRate": 1,
        "laborBCWS": 38528,
        "dependenciesStart": "1969-12-31 06:59:59",
        "performingUsers": [],
        "interlinkMirroringTtoT": "Task to Task (Mirroring)",
        "baseline14Finish": "1969-12-31 06:59:59",
        "baselineDuration": 3304,
        "mustStartOn": "1969-12-31 06:59:59",
        "deliverablesWorkflowAlerts": false,
        "dependenciesTotalCost": 0,
        "ganttHardAssignment": "",
        "contractDescription": "",
        "actualCostItemCost": 0,
        "remainingCostItemCost": 0,
        "totalCostItemCost": 0,
        "baselineLaborEffort": 827.5303881944444,
        "percentageCompleted": 0.6154904336385759,
        "workPackageReportIncludeRisks": false,
        "baseline6Finish": "1969-12-31 06:59:59",
        "remainingLaborEffort": 303.61422215277776,
        "modifiedBy": "",
        "finishDelay": 0,
        "bufferIncursion": "1969-12-31 06:59:59",
        "baseline9Start": "1969-12-31 06:59:59",
        "baseline1Finish": "2019-03-07 09:07:17",
        "bufferExpectedFinish": "1969-12-31 06:59:59",
        "baseline14Start": "1969-12-31 06:59:59",
        "performingCostItems": [],
        "baseline3Start": "1969-12-31 06:59:59",
        "aCWP": 38650.634626666666,
        "closed": false,
        "mspPctCompleted": 0,
        "baseline7Finish": "1969-12-31 06:59:59",
        "workPackageReportMode": 0,
        "workPackageTimeStatus": 0,
        "eVMethod": "% Complete",
        "workPackageDescription": "",
        "bCWS": 38528,
        "workPackageOrgWriter": "",
        "workPackageReportDecisions": "",
        "relatedPhases": [],
        "bCWP": 35085.9509940083,
        "safeDuration": 0,
        "workPackagePriority": "",
        "baseline10Finish": "1969-12-31 06:59:59",
        "finish": "2019-04-30 06:27:24",
        "workPackageContractFinish": "1969-12-31 06:59:59",
        "ganttSoftAssignmentRate": 1,
        "epicOwnerPicture": "",
        "baselineFinish": "2019-03-07 09:07:17",
        "actualLaborCost": 38650.634626666666,
        "isParent": false,
        "totalLaborEffort": 907.5303881944444,
        "workPackageDeliverablesFilter": "",
        "baseline4Start": "1969-12-31 06:59:59",
        "baseline5Finish": "1969-12-31 06:59:59",
        "includeFlaggedTasks": false,
        "workPackageTemporaryID": "",
        "performingOrganizations": [],
        "name": "Project management Test",
        "modifiedDate": "1969-12-31 06:59:59",
        "baseline2Finish": "1969-12-31 06:59:59",
        "totalCost": 38650.634626666666,
        "deliverableID": 0,
        "ganttCostItemAssignmentInternalID": 0,
        "baseline5Start": "1969-12-31 06:59:59",
        "chainRemaining": 0,
        "description": "",
        "completedDuration": 1944,
        "baselineCost": 52961.94484444444,
        "mspStart": "1969-12-31 06:59:59",
        "workPackageReportIncludePlanning": false,
        "duration": 3614,
        "lockedBy": "",
        "workPackageReportIncludeBudget": false,
        "showChildSymbols": false,
        "workPackageReportNextSteps": "",
        "networkColumn": 0,
        "baseline3Finish": "1969-12-31 06:59:59",
        "levelingPriority": 50,
        "interlinkTID": "",
        "start": "2017-08-07 02:00:00",
        "percentageLaborEffortComplete": 0.6654500762703646,
        "pinDate": "1969-12-31 06:59:59",
        "startDelay": 0,
        "workPackageReportIncludeDeliverables": false,
        "bufferCalculationMethod": "",
        "baseline8Start": "1969-12-31 06:59:59",
        "workPackageOrgReader": "",
        "remainingLaborCost": 0,
        "originalChainLength": 0,
        "release": "",
        "baseline4Finish": "1969-12-31 06:59:59",
        "workPackageEarliestStart": "1969-12-31 06:59:59",
        "wBS": "",
        "requiredDate": "1969-12-31 06:59:59",
        "issues": "",
        "baselineLaborCost": 52961.94484444444,
        "showChildLabels": false,
        "workPackageReportEcoMode": false,
        "bufferIncursionGuide": "1969-12-31 06:59:59",
        "number": 33,
        "baselineCostItemCost": 0,
        "permissions": "",
        "filterTaskLevel": "2",
        "contract": false,
        "epic": "",
        "baseline11Finish": "1969-12-31 06:59:59",
        "deliverablesDateAlerts": false,
        "scheduleType": "Hammock",
        "physicalpercentageComplete": 0.6624747466706505,
        "workPackageUserWriter": [],
        "actualStart": "2017-08-07 02:00:00",
        "performingResources": [],
        "exportToMSP": false,
        "totalLaborCost": 38650.634626666666,
        "baseline12Finish": "1969-12-31 06:59:59",
        "workPackageScopeStatus": 0,
        "extendedLock": false,
        "standardIssues": "",
        "manager2Picture": "",
        "workPackageReportMeetingAttendees": "",
        "dependenciesOwner": "",
        "actualCost": 38650.634626666666,
        "workPackageReportComments": "",
        "workPackageReportRisksFilter": "",
        "dependenciesTotalEffort": 0,
        "taskPriority": "",
        "manager1picture": "",
        "baselineStart": "2017-08-07 02:00:00",
        "menu": "",
        "baseline6Start": "1969-12-31 06:59:59",
        "baseline11Start": "1969-12-31 06:59:59",
        "sujetIssues": "",
        "manager1": "",
        "manager2": "",
        "manager3": "",
        "ganttSoftAssignment": "",
        "deliverablesTaskAlerts": false,
        "dependenciesFinish": "1969-12-31 06:59:59",
        "costItemBCWS": 0,
        "workPackageID": "",
        "baseline2Start": "1969-12-31 06:59:59",
        "remainingCost": 0,
        "costItemBCWP": 0,
        "laborACWP": 38650.634626666666,
        "allowMyWorkAdd": true,
        "outlineRow": 0,
        "dependenciespercentageCompleted": 0,
        "workPackageReportImportantEvents": "",
        "additionalIndicator1": 0,
        "allowSplitting": true,
        "freeFloat": 0,
        "additionalIndicator2": 0,
        "baseline8Finish": "1969-12-31 06:59:59",
        "baseline13Finish": "1969-12-31 06:59:59",
        "interlinkMap": "",
        "allowDelete": true,
        "iterationOwnerPicture": "",
        "releaseOwnerPicture": "",
        "baseline1Start": "2017-08-07 02:00:00",
        "completedDate": "2018-10-01 11:00:00",
        "internalID": 864441,
        "networkRow": 0,
        "workPackageReportDiscussion": "",
        "onCriticalChain": false,
        "baseline9Finish": "1969-12-31 06:59:59",
        "workPackageContractStart": "1969-12-31 06:59:59",
        "baseline13Start": "1969-12-31 06:59:59",
        "workPackagetype": "",
        "workPackageUserReader": [],
        "ganttWatchList": false,
        "workPackageContractLock": false,
        "mspFinish": "1969-12-31 06:59:59",
        "outlineLevel": 1,
        "outlineColumn": 0,
        "trackingActuals": false,
        "manager3Picture": "",
        "workPackageReportIncludeIssues": false,
        "iteration": "",
        "includeMilestones": false,
        "bufferDurationGuide": 0,
        "taskText": "",
        "allowasInterlinkSource": false,
        "ganttFlagged": "",
        "totalFloat": 0,
        "interlinkPID": "",
        "lateFinish": "2019-04-30 06:27:24",
        "actualFinish": "2019-04-30 06:27:24",
        "requiredLabor": 0,
        "showNonSummarized": false,
        "levelingConflict": false,
        "workPackageTrendStatus": 0,
        "lateStart": "2018-10-01 11:00:00"
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
