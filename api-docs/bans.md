# Bans

{% api-method method="get" host="https://fbans-api.madebythepins.tk" path="/bans/:id" %}
{% api-method-summary %}
Getting an user's status by ID
{% endapi-method-summary %}

{% api-method-description %}
This method will query an user ID against our database if that user is banned or not. Requires User permissions. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
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

