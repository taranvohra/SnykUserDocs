# Snyk Code - Clone capability with Broker for Docker

{% hint style="info" %}
**Feature availability**

The environment variable to enable Git clone capabilities is in Closed Beta. However, it is the preferred way to run Snyk Code analysis through the Broker and is fully capable. Contact your Snyk account management team to find out more.
{% endhint %}

Brokered Snyk Code enables the Broker to accept code files, and the Broker then scans between the SCM system and Snyk.

By default, the Git clone capabilities required by Snyk Code are disabled.

## Accept configuration

To grant Broker access to perform a Git clone of your repository, add the environment variable: `ACCEPT_CODE=true`

Example:

```
docker run --restart=always \
           -p 8000:8000 \
           -e BROKER_TOKEN=secret-broker-token \
           -e GITHUB_TOKEN=secret-github-token \
           -e PORT=8000 \
           -e BROKER_CLIENT_URL=http://my.broker.client:8000 \
           -e ACCEPT_CODE=true
       snyk/broker:github-com
```

This adds the necessary `accept` rules for your Git server.

After this is done, you can follow the Broker instructions for your SCM system. For details, see [Install and configure Snyk Broker](../)

## Custom accept configuration

The default rules are in the [client templates in the Broker GitHub repository](https://github.com/snyk/broker/tree/master/client-templates).

If custom `accept` rules are required, you can provide a custom `accept.json`.

Example:

```console
docker run --restart=always \
           -p 8000:8000 \
           -e BROKER_TOKEN=secret-broker-token \
           -e GITHUB_TOKEN=secret-github-token \
           -e PORT=8000 \
           -e BROKER_CLIENT_URL=http://my.broker.client:8000 \
           -e ACCEPT=/myFolder/accept.json
       snyk/broker:github-com
```

If you are using a custom `accept` file from a separate folder, with the `ACCEPT` environment variable, you cannot use the `ACCEPT_CODE` mechanism.

You can find the relevant `accept.json` for each of the Git integrations in [Adding custom allowlist for Docker installation](https://github.com/taranvohra/SnykDocs/blob/main/docs/enterprise-setup/snyk-broker/install-and-configure-snyk-broker/advanced-configuration-for-snyk-broker-docker-installation/broken-reference/README.md).

If you want to customize the `accept.json`, add this snippet to your custom `accept.json`

```
{
    "//": "used to redirect requests to snyk git client",
    "method": "any",
    "path": "/snykgit/*",
    "origin": "${GIT_CLIENT_URL}"
}
```

This snippet is valid for all Git integrations.
