# REST Contract: `/api/actions`

## General Information

**Endpoint:** `/api/actions`

**Description:** Provides access to the list of available actions in the system. Each action contains metadata about its execution and configuration properties.

---

## GET /api/actions

**Description:** Retrieve a list of all available actions that can be executed in the system.

### Query Parameters

_No query parameters are required for this endpoint._

### Sample Response

```json
{
  "actions": [
    {
      // "name": "HARVESTING_ACTION",
      "description": "Harvesting",
      // "workers": ["harvestingWorker"],
      "incremental": true,
      "properties": [
        {
          "name": "FORCE_FULL_HARVESTING",
          "description": "Force full harvesting?"
        }
      ],
      "runOnSchedule": true,
      "allwaysRunOnSchedule": true
    },
   
  ]
}
```

### Response Codes

| Code | Description             |
|------|-------------------------|
| 200  | Successful retrieval    |

---

## GET /api/actions/{name}

**Description:** Retrieve the definition of a specific action by its `name`.

### Path Parameters

| Parameter | Type   | Description            | Required |
|-----------|--------|------------------------|----------|
| `name`    | string | Action name identifier | Yes      |

### Sample Response

```json
{
  // "name": "HARVESTING_ACTION",
  "description": "Harvesting",
  // "workers": ["harvestingWorker"],
  "incremental": true,
  "properties": [
    {
      "name": "FORCE_FULL_HARVESTING",
      "description": "Force full harvesting?"
    }
  ],
  "runOnSchedule": true,
  "allwaysRunOnSchedule": true
},
```

### Response Codes

| Code | Description             |
|------|-------------------------|
| 200  | Successful retrieval    |
| 404  | Action not found        |

---

## Future Endpoints (Optional)

- `POST /api/actions`: Create a new action
- `PATCH /api/actions/{name}`: Update an action
- `DELETE /api/actions/{name}`: Delete an action

*These operations can be documented in future expansions of the contract.*
