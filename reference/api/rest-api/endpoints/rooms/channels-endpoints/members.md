# Channel Members List

Lists all channel users. It supports the [#pagination](../../../#pagination "mention") parameters.

{% hint style="info" %}
The list of elements a user can use to sort the list is limited. The current sortable element is:`username`
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/channels.members` | `yes`         | `GET`       |

## Query Parameters

| Argument            | Example                    | Required                  | Description                                                                                      |
| ------------------- | -------------------------- | ------------------------- | ------------------------------------------------------------------------------------------------ |
| `roomId`            | `ByehQjC44FwMeiLbX`        | Required (if no roomName) | The channel's id                                                                                 |
| `roomName`          | `general`                  | Required (if no roomId)   | The channel's name                                                                               |
| `status`            | `['online', 'away']`       | Optional                  | The user's status (search filter).                                                               |
| `filter`            | `my-nickname`              | Optional                  | Extra search filters to be applied to the fields defined in the `Accounts_SearchFields` setting. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.members?roomId=ByehQjC44FwMeiLbX&count=2
```

## Example Result

```javascript
{
    "members": [
        {
            "_id": "Loz7qh9ChSqHMPymx",
            "username": "customField_apiuser.test.1529436896005",
            "name": "customField_apiuser.test.1529436896005",
            "status": "offline"
        },
        {
            "_id": "Zc3Y3cRW7ZtS7Y8Hk",
            "username": "customField_apiuser.test.1529436997563",
            "name": "customField_apiuser.test.1529436997563",
            "status": "offline"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 35,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.59.0  | Added       |
