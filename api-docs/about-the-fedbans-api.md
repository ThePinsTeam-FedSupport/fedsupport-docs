# About the FedBans API

{% hint style="warning" %}
**The API is currently under heavy deployment.** Follow its development on [GitLab](https://gitlab.com/RetardedCasesOnTG/FedBans-API).
{% endhint %}

The Federation Bans API is a RESTful API \(with GraphQL API coming soon\) that uses our own list of users who banned in our federation.

## How to get an API key?

Currently, there's no way to generate an API key on your own yet. In meanwhile, [join the Federation Support chat](https://t.me/ThePinsTeam_FedSupport) and mention one of our FedAdmins to help you get one.

## Rate-limiting

To prevent downtimes and to protect the integrity of our API server, we implemented some rate-limiting procotols in both REST API and GrapQL API.

| API Type | Per IP address/hour | Per-user/hour |
| :--- | :--- | :--- |
| REST | 15,000 requests | 5,000 requests |
| GraphQL | 15,000 points | 5,000 points |

### Why rate-limits in both REST and GraphQL are different? 

