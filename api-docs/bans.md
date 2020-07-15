# Bans

{% api-method method="get" host="https://fbans-api.madebythepins.tk" path="/bans" %}
{% api-method-summary %}
Getting a ban
{% endapi-method-summary %}

{% api-method-description %}
This method will query a user ID against our database if that user is banned or not. Requires User permissions. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The target user's ID to lookup against our DB.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Must be in the format of `Bearer $API_TOKEN_HERE`.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
When found on our database, a `200: OK` response will look like this.
{% endapi-method-response-example-description %}

```
{
    "ok": true,
    "result": {
        "userId": 777000,
        "reason": "Creating Telegram",
        "fedAdmin": 705519392
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
If an API key is not provided, a `401 Unauthorized` response will look like this.
{% endapi-method-response-example-description %}

```
{
    "ok": false,
    "description": "API key not provided".
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
If an user is not found to be banned, a `404 Not Found` response will look like this.
{% endapi-method-response-example-description %}

```
{
    "ok": false,
    "description": "That user seems to be not banned here."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://fbans-api.madebythepins.tk" path="/bans" %}
{% api-method-summary %}
Adding or updating a ban
{% endapi-method-summary %}

{% api-method-description %}
This method will add or update a ban. This endpoint can be used for issuing/updating multiple bans. Requires Admin permissions.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Must be in format of `Bearer $API_TOKEN_HERE`.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="reason" type="string" required=false %}
Reason of the ban. If updating the ban, it shouldn't be blank.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=true %}
The target Telegram user's ID to blacklist.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}
When successfully added/updated, the server will send you a `No Content` response with this JSON response.
{% endapi-method-response-example-description %}

```
{
    "ok": true,
    "description": "Added/updated ban/s. The response was nothing."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://fbans-api.madebythepins.tk" path="/bans" %}
{% api-method-summary %}
Delete an ban
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
Target Telegram user's ID to unban.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

