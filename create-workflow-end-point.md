Create a new workflow endpoint:
https://workflow-staging.signavio.com/api/v1/5a27c5b6d9383b14da6c9619/workflows

Example Curl:

```bash
curl 'https://workflow-staging.signavio.com/api/v1/5a27c5b6d9383b14da6c9619/workflows' \
  -H 'accept: */*' \
  -H 'accept-language: en-US,en;q=0.9,de;q=0.8,hi;q=0.7,zh-CN;q=0.6,zh;q=0.5,cy;q=0.4,fr;q=0.3' \
  -H 'authorization: undefined' \
  -H 'content-type: text/plain;charset=UTF-8' \
  -H 'origin: https://workflow-staging.signavio.com' \
  -H 'priority: u=1, i' \
  -H 'referer: https://workflow-staging.signavio.com/5a27c5b6d9383b14da6c9619/processes/create' \
  -H 'sec-ch-ua: "Chromium";v="140", "Not=A?Brand";v="24", "Google Chrome";v="140"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "macOS"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/140.0.0.0 Safari/537.36' \
  --data-raw '{"id":"t3g3p4ce0tcpnrebn8","name":"abc","trigger":null,"activities":[],"transitions":[],"variables":[],"labelIds":[],"diagram":{"canvas":{"children":[],"bounds":{"upperLeft":{"x":0,"y":0},"lowerRight":{"x":0,"y":0}}},"edges":[]},"coreInformation":{"fields":[]}}'
```

Example Response:

```json
{
    "name": "abc",
    "activities": [],
    "transitions": [],
    "variables": [],
    "id": "68dcedb8843ee973933be5fc",
    "organizationId": "5a27c5b6d9383b14da6c961a",
    "involvedUserIds": [],
    "involvedGroupIds": [],
    "lastUpdated": "2025-10-01T09:00:40.971Z",
    "enableCases": false,
    "diagram": {
        "canvas": {
            "bounds": {
                "lowerRight": {
                    "x": 0.0,
                    "y": 0.0
                },
                "upperLeft": {
                    "x": 0.0,
                    "y": 0.0
                }
            },
            "children": []
        },
        "edges": [],
        "version": 1
    },
    "coreInformation": {
        "fields": []
    },
    "changed": true,
    "editorId": "66ea8df96483b76785e90b2e",
    "editorLock": "2025-10-01T09:00:40.971Z",
    "ownerId": "66ea8df96483b76785e90b2e",
    "labelIds": [],
    "editor": {
        "id": "66ea8df96483b76785e90b2e",
        "color": "#83cb76",
        "firstName": "Ajit Singh",
        "groupIds": [],
        "lastName": "Chahal",
        "emailAddress": "ajit.singh.chahal@sap.com",
        "organizationIds": []
    },
    "owner": {
        "id": "66ea8df96483b76785e90b2e",
        "color": "#83cb76",
        "firstName": "Ajit Singh",
        "groupIds": [],
        "lastName": "Chahal",
        "emailAddress": "ajit.singh.chahal@sap.com",
        "organizationIds": []
    },
    "labels": [],
    "published": false
}

```

Detailed information:
# Workflow Object MCP Documentation

## Overview
This document describes the structure and properties of a workflow object based on BPMN 2.0 standards with system-specific extensions.

## Root Properties

### `name` (required)
- **Type**: `string`
- **Description**: Describes the name of the workflow
- **Constraints**:
  - Cannot be null or undefined
  - No length limits
  - Does not need to be unique
- **Example**: `"The API Whisperer"`

### `id` (required)
- **Type**: `string`
- **Description**: Unique identifier for the workflow
- **Constraints**: Auto-generated once created
- **Example**: `"68dbed66cb40e3f639272753"`

### `organizationId` (required)
- **Type**: `string`
- **Description**: Identifier of the organization this workflow belongs to
- **Example**: `"584ec417d9383b68ed2cd560"`

## Activities Array

### `activities` (required)
- **Type**: `Array<Activity>`
- **Description**: Contains BPMN 2.0 activity elements that define the workflow steps
- **Constraints**:
  - Can be empty array
  - Cannot be null or undefined
  - Contains objects representing different activity types

#### Activity Types

#### StartEvent
Based on BPMN 2.0 standard for workflow initiation points.

```json
{
  "type": "startEvent",
  "name": "",
  "id": "auto-generated-id"
}
```

**Properties:**
- `type`: Always `"startEvent"`
- `name`: Optional string (recommended for clarity of starting point)
- `id`: Auto-generated unique identifier
- **Constraints**:
  - Can only have outgoing transitions, no incoming
  - Can only have one outgoing transition
- **Variants**: Basic start events, intermediate timer events, intermediate link events

#### UserTask
Represents human-performed activities based on BPMN 2.0.

```json
{
  "type": "userTask",
  "candidateIds": [],
  "candidateGroupIds": [],
  "candidateExpressions": [],
  "form": {
    "fields": [
      {
        "elementType": "fieldDefinition",
        "id": "auto-generated-id",
        "asButtons": true,
        "binding": {
          "expression": "variable-id"
        },
        "parameters": {}
      }
    ]
  },
  "escalateToIds": [],
  "escalateToGroupIds": [],
  "escalateToVariableExpressions": [],
  "name": "task-name",
  "id": "auto-generated-id"
}
```

**Properties:**
- `type`: Always `"userTask"`
- `name`: String name of the task
- `id`: Auto-generated unique identifier
- `candidateIds`: Array of user ID strings for assignment options (users must be known to organization)
- `candidateGroupIds`: Array of group ID strings that resolve to users for assignment
- `candidateExpressions`: String referencing a user variable from the variables array
- `form.fields`: Array of form field definitions
  - `elementType`: Type of form element (e.g., `"fieldDefinition"`)
  - `asButtons`: Boolean - when `true`, renders buttons at bottom of form (can only appear before gateways)
  - `binding.expression`: References a variable ID for data binding
  - `parameters`: Object for additional field configuration
- `escalateToIds`: Array for task reassignment after timeouts
- `escalateToGroupIds`: Array for group escalation after timeouts
- `escalateToVariableExpressions`: Array for variable-based escalation

**Note**: Multiple form field types available beyond choice/button fields (reminder: provide form field example later).

#### ExclusiveGateway
Based on BPMN 2.0 XOR gateway for routing decisions.

```json
{
  "type": "exclusiveGateway",
  "name": "gateway-name",
  "id": "auto-generated-id",
  "decisionType": "manual"
}
```

**Properties:**
- `type`: Always `"exclusiveGateway"`
- `name`: String name of the gateway
- `id`: Auto-generated unique identifier
- `decisionType`:
  - `"manual"`: User assigned to previous userTask decides by button click
  - `"automatic"`: Decision computed based on transition conditions
  - `"notset"`: (Skip for documentation purposes)

#### EndEvent
Based on BPMN 2.0 standard for workflow termination points.

```json
{
  "type": "endEvent",
  "name": "",
  "id": "auto-generated-id"
}
```

**Properties:**
- `type`: Always `"endEvent"`
- `name`: Optional string
- `id`: Auto-generated unique identifier
- **Variants**: Basic end events, intermediate timer events, intermediate link events

## Transitions Array

### `transitions` (required)
- **Type**: `Array<Transition>`
- **Description**: Defines the flow connections between activities
- **Constraints**: For logical workflows, all transitions require `fromId`, `toId`, and `id`

#### Basic Transition
```json
{
  "id": "auto-generated-id",
  "fromId": "source-activity-id",
  "toId": "target-activity-id"
}
```

#### Conditional Transition
```json
{
  "id": "auto-generated-id",
  "fromId": "gateway-id",
  "toId": "target-activity-id",
  "condition": {
    "type": "equals",
    "left": {
      "expression": "variable-id"
    },
    "right": {
      "type": {
        "name": "choice",
        "options": [
          {
            "id": "option-id",
            "name": "option-name",
            "deleted": false
          }
        ]
      },
      "value": "option-id"
    }
  }
}
```

**Properties:**
- `id`: Auto-generated unique identifier
- `fromId`: Source activity ID
- `toId`: Target activity ID
- `condition`: Optional condition object for exclusive gateways
  - `type`: Condition type (e.g., `"equals"`)
  - `left.expression`: References a variable ID
  - `right.value`: References a choice option ID
  - `right.type`: Contains full choice definition with options

**Behavior:**
- Conditions evaluate if variable value equals specified choice option
- If no condition matches on exclusive gateway, workflow stops
- Multiple condition types may be available beyond "equals"

## Variables Array

### `variables` (required)
- **Type**: `Array<Variable>`
- **Description**: Defines workflow variables used in conditions and forms

#### Choice Variable
```json
{
  "id": "auto-generated-id",
  "name": "variable-name",
  "type": {
    "name": "choice",
    "options": [
      {
        "id": "auto-generated-id",
        "name": "option-name",
        "deleted": false
      }
    ]
  },
  "isManualDecision": true
}
```

**Properties:**
- `id`: Auto-generated unique identifier
- `name`: Variable name
- `type.name`: Type of variable (e.g., `"choice"`)
- `type.options`: Array of choice options with ID, name, and deletion status
- `isManualDecision`: Boolean indicating if this is used for manual gateway decisions

## Metadata Properties

### Timestamps and Ownership
- `lastUpdated`: ISO timestamp of last modification
- `editorId`: ID of user who last edited
- `editorLock`: ISO timestamp of edit lock
- `ownerId`: ID of workflow owner
- `changed`: Boolean indicating if workflow has unsaved changes
- `published`: Boolean indicating publication status

### User Objects
- `editor`: User object with `id`, `firstName`, `lastName`, `emailAddress`, `groupIds`, `organizationIds`
- `owner`: User object with same structure as editor

### Organization and Permissions
- `involvedUserIds`: Array of user IDs involved in workflow
- `involvedGroupIds`: Array of group IDs involved in workflow
- `enableCases`: Boolean for case management features
- `labelIds`: Array of label identifiers
- `labels`: Array of label objects

### Case Management
- `caseColumns`: Array of case column definitions with binding expressions
  - Standard bindings include: `"case.creatorId"`, `"case.milestone"`, `"case.dueDate"`

### Core Information
- `coreInformation.fields`: Array of core information fields (structure varies)

## Diagram Object

### `diagram` (required)
- **Type**: `Object`
- **Description**: Contains visual layout information for workflow diagram
- **Properties**:
  - `version`: Version number of diagram format
  - `canvas`: Canvas bounds and child element positioning
  - `edges`: Visual edge routing information between activities

#### Canvas Structure
```json
{
  "canvas": {
    "bounds": {
      "upperLeft": {"x": 40.0, "y": 108.0},
      "lowerRight": {"x": 881.03125, "y": 348.0}
    },
    "children": [
      {
        "id": "visual-element-id",
        "bounds": {
          "upperLeft": {"x": 40.0, "y": 213.0},
          "lowerRight": {"x": 70.0, "y": 243.0}
        },
        "children": [],
        "elementId": "activity-id"
      }
    ]
  }
}
```

#### Edge Routing
```json
{
  "edges": [
    {
      "id": "visual-edge-id",
      "dockers": [
        {"x": 15.0, "y": 15.0},
        {"x": 50.0, "y": 40.0}
      ],
      "fromId": "source-visual-element-id",
      "toId": "target-visual-element-id",
      "transitionId": "logical-transition-id"
    }
  ]
}
```

## Schema Constraints

- All ID fields are auto-generated upon creation
- Arrays can be empty but not null/undefined
- Required string fields cannot be null/undefined
- Visual diagram coordinates use floating-point precision
- ISO timestamps follow standard format
- Email addresses in user objects should be valid format

## Workflow Execution Behavior

- Follows BPMN 2.0 token-based execution semantics
- Start events initiate workflow execution
- User tasks pause execution until completion
- Exclusive gateways route based on conditions or manual decisions
- End events terminate workflow execution
- Failed condition matching stops workflow execution
