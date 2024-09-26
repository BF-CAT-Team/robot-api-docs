# Bfv

## Statistics 获取BFV SERVER统计信息

<mark style="color:green;">`GET`</mark> `/statistics`

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "success": 1,
  "code": "servers.success",
  "data": {
    "ALL": {
      "diceServerSoldierCurrent": 7837,
      "diceServerSpectatorCurrent": 7,
      "diceServerQueueCurrent": 38,
      "robotServerSoldierCurrent": 0,
      "robotServerSpectatorCurrent": 0,
      "robotServerQueueCurrent": 0,
      "allServerSoldierCurrent": 15196,
      "allServerSpectatorCurrent": 22,
      "allServerQueueCurrent": 554,
      "serverCount": 447
    }
  }
}
```
{% endtab %}

{% tab title="500" %}
```json
{
  "error": 0,
  "code": "servers.error",
  "message": "Error fetching server statistics"
}
```
{% endtab %}
{% endtabs %}



## Servers 服务器列表

<mark style="color:green;">`POST`</mark> `/servers`

获取服务器列表

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

<table><thead><tr><th>Name</th><th width="133">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>serverName</code></td><td>string</td><td>Name of the server</td></tr><tr><td><code>limit</code></td><td>number</td><td>Limit of search server, default 100</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "success": 1,
  "code": "servers.success",
  "data": [
    {
      "mapName": "",
      "mapMode": "",
      "smallMode": "BT",
      "description": "",
      "gameId": 1,
      "official": false,
      "ownerId": 1,
      "serverName": "",
      "region": "Asia",
      "country": "JP",
      "slots": {
        "Soldier": {
          "current": 64,
          "max": 64
        },
        "Spectator": {
          "current": 0,
          "max": 4
        },
        "Queue": {
          "current": 0,
          "max": 10
        }
      },
      "url": "https://eaassets-a.akamaihd.net/battlelog/battlebinary/gamedata/Casablanca/50/56/1080p_MP_WakeIsland-3238b455.jpg"
    }
  ]
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "error": 1, 
    "code": "servers.error", 
    "message": "error"
}
```
{% endtab %}
{% endtabs %}

## Players 玩家列表

<mark style="color:green;">`POST`</mark> `/players`

获取服务器玩家列表

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

<table><thead><tr><th width="240">Name</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>gameId</code></td><td>number/string</td><td>gameId</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success": 1,
    "message": "players.successful",
    "data": {
        "gameId": 1,
        "serverName": "",
        "description": "",
        "region": "",
        "country": "",
        "slots": {
            "Soldier": {
                "current": 1,
                "max": 64
            },
            "Spectator": {
                "current": 0,
                "max": 4
            },
            "Queue": {
                "current": 0,
                "max": 10
            }
        },
        "players": {
            "team_1": [],
            "team_2": [],
            "team_x": [
                {
                    "personaId": 1,
                    "userId": 1,
                    "join": 1,
                    "locale": 1684358213,
                    "name": "1",
                    "platoon": "1"
                }
            ],
            "loading": [],
            "spectators": []
        },
        "admins": [
            1,
            {
                "low": 19563,
                "high": -1986002944,
                "unsigned": false
            }
        ],
        "playgroundId": ""
    }
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "error": 1, 
    "code": "players.error", 
    "message": "error"
}
```
{% endtab %}

{% tab title="404" %}
```json
{
    "error": 1, 
    "code": "players.error", 
    "message": "players.server not found"
}
```
{% endtab %}
{% endtabs %}

