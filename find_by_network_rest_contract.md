# REST Contract: `/api/findByNetworkIdOrdered`

## General Information

**Endpoint:** `/api/findByNetworkIdOrdered`

**Description:** Retrieves a paginated list of snapshots associated with a specific network, ordered by time.

---

## GET /api/snapshot/search/findByNetworkIdOrdered

**Description:** Retrieve snapshots by `network_id` in a paginated, ordered manner.

### Query Parameters

| Parameter     | Type   | Description                            | Required |
|---------------|--------|----------------------------------------|----------|
| `network_id`  | int    | ID of the network                      | Yes      |
| `page`        | int    | Page number (starting from 0)          | No       |
| `size`        | int    | Number of results per page (default 20)| No       |

### Sample Response

```json
{
  "_embedded": {
    "snapshot": [
      {
        "id": 1,
        "previousSnapshotId": null,
        "status": "HARVESTING",
        "indexStatus": "UNKNOWN",
        "startTime": "2025-03-17 12:19:31",
        // "lastIncrementalTime": null,
        "endTime": "2025-03-17 16:04:43",
        "size": 595010,
        "validSize": 0,
        "transformedSize": 0,
        // "resumptionToken": null,
        "deleted": false,
      //   "_links": {
      //     "self": {
      //       "href": "http://localhost:8090/rest/snapshot/4"
      //     },
      //     "networkSnapshot": {
      //       "href": "http://localhost:8090/rest/snapshot/4"
      //     },
      //     "network": {
      //       "href": "http://localhost:8090/rest/snapshot/4/network"
      //     }
      //   }
      }
    ]
  },
  // "_links": {
  //   "self": {
  //     "href": "http://localhost:8090/rest/snapshot/search/findByNetworkIdOrdered?network_id=1&page=0&size=20"
  //   }
  // }
}
```

### Response Codes

| Code | Description             |
|------|-------------------------|
| 200  | Successful retrieval    |
| 404  | Network or snapshots not found |
