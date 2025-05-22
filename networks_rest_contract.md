# REST Contract: /api/networks

## General Information

**Endpoint:** `/api/networks`

**Description:** Provides access to the list of networks in the system. Each network contains metadata and snapshot information.

---

## GET /api/networks

**Description:** Retrieve a paginated list of all networks.

### Query Parameters

| Parameter | Type | Description | Required |
|-----------|------|-------------|----------|
| `page`    | int  | Page number (starting from 0) | No |
| `size`    | int  | Number of results per page (default: 25) | No |
| `sort`    | string | Field to sort by | No |

### Sample Response

```json
{
  "networks": [
    {
      "networkID": 17,
      "institutionAcronym": "ANNII",
      "acronym": "UY",
      "name": "Uruguay",
      // "institution": "Agencia Nacional de Investigación e Innovación",
      // "attributes": {
      //   "@class": "org.lareferencia.backend.network.LAReferenciaNetworkAttributes",
      //   "type": "",
      //   "email": "",
      //   "phone": "0",
      //   "url": "",
      //   "country": "",
      //   "software": "",
      //   "stats_source_id": "SITEID::58"
      // },
      "running": [],
      "queued": [],
      "scheduled": ["AllActions(10 days)"],
      "snapshotID": 3107,
      // "datestamp": "2023-09-22 16:36:14",
      "size": 12939,
      "validSize": 12939,
      "transformedSize": 7,
      "lgkSnapshotID": 3107,
      "lgkSnapshotDate": "2023-09-22 16:36:14",
      // "lgkSize": 12939,
      // "lgkValidSize": 12939,
      // "lgkTransformedSize": 7,
      "lstSnapshotID": 3113,
      "lstSnapshotDate": "2023-09-25 14:47:34",
      "lstSnapshotStatus": "HARVESTING_FINISHED_ERROR",
      // "lstIndexStatus": "UNKNOWN",
      // "lstSize": 0,
      // "lstValidSize": 0,
      // "lstTransformedSize": 0
    }
  ]
}
```

### Response Codes

| Code | Description |
|------|-------------|
| 200  | Successful retrieval |

---

## GET /api/networks/{id}

**Description:** Retrieve details of a specific network by its ID.

### Path Parameters

| Parameter | Type | Description | Required |
|-----------|------|-------------|----------|
| `id`      | int  | Network identifier | Yes |

### Sample Response

```json
{
  "networkID": 17,
  "institutionAcronym": "ANNII",
  "acronym": "UY",
  "name": "Uruguay",
  // "institution": "Agencia Nacional de Investigación e Innovación",
  // "attributes": {
  //   "@class": "org.lareferencia.backend.network.LAReferenciaNetworkAttributes",
  //   "type": "",
  //   "email": "",
  //   "phone": "0",
  //   "url": "",
  //   "country": "",
  //   "software": "",
  //   "stats_source_id": "SITEID::58"
  // },
  ...
}
```

### Response Codes

| Code | Description |
|------|-------------|
| 200  | Successful retrieval |
| 404  | Network not found |

---

## Future Endpoints (Optional)

- `POST /api/networks`: Create a new network
- `PATCH /api/networks/{id}`: Update a network
- `DELETE /api/networks/{id}`: Delete a network

*These operations can be documented in future expansions of the contract.*
