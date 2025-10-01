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
