# Admin

## Search User 搜索社区用户

<mark style="color:green;">`POST`</mark> <mark style="color:purple;">`Captcha`</mark> `/searchUser`

```
本接口需要鉴权, 仅允许 ["super", "root", "dev", "admin"] 访问
```

**Headers**

| Name           | Value              |
| -------------- | ------------------ |
| Content-Type   | `application/json` |
| X-Access-Token | `<token>`          |

**Body**

<table><thead><tr><th width="144">Name</th><th width="111">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td>string</td><td>用户名称</td></tr><tr><td><code>type</code></td><td>string</td><td>搜索类型, 支持 id, eaPID, thirdParty</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success": 1,
    "code": "searchUser.success",
    "data": [
        {
            "id": 2,
            "username": "test",
            "name": null,
            "privilege": [
                "normal"
            ],
            "originName": "",
            "originEmail": "",
            "originUserId": "",
            "originPersonaId": "",
            "qq": null,
            "kook": null,
            "createTime": "2024-06-29T02:53:24.000Z",
            "updateTime": "2024-07-04T03:52:42.000Z",
            "signoutTime": null,
            "valid": 1,
            "score": 0
        }
    ]
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "error": 1, 
    "code": "searchUser.error", 
    "message": "error"
}
```
{% endtab %}
{% endtabs %}

## Edit User Info 编辑社区用户

<mark style="color:green;">`POST`</mark> <mark style="color:purple;">`Captcha`</mark> `/editUserInfo`

```
本接口需要鉴权, 仅允许 ["super", "root", "dev", "admin"] 访问
```

**Headers**

| Name           | Value              |
| -------------- | ------------------ |
| Content-Type   | `application/json` |
| X-Access-Token | `<token>`          |

**Body**

<table><thead><tr><th width="144">Name</th><th width="111">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>id</code></td><td>int</td><td>用户社区ID</td></tr><tr><td><code>privilege</code></td><td>array</td><td>权限组</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success":1,
    "code":"editUserInfo.success"
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "error": 1, 
    "code": "e.error", 
    "message": "error"
}
```
{% endtab %}

{% tab title="403" %}

{% endtab %}
{% endtabs %}

