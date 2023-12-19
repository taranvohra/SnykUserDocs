# Apex

{% hint style="info" %}
Snyk for Apex is supported only for Snyk Code.
{% endhint %}

## Code analysis

Interfile is currently not supported. The data flow is monitored within a single file, not between multiple files.

`.trigger` and `.cls` files are supported.

## Getting started with Snyk for Apex across environments

### Snyk CLI

#### Prerequisites

* [Create a Snyk account](../../getting-started/quickstart/create-or-log-in-to-a-snyk-account.md)
* [Install Snyk CLI and authenticate your machine](../../snyk-cli/getting-started-with-the-snyk-cli.md#install-the-snyk-cli-and-authenticate-your-machine)
* [Set the default Organization for all Snyk tests](https://github.com/taranvohra/SnykDocs/blob/main/docs/scan-applications/supported-languages-and-frameworks/broken-reference/README.md) (code analysis)

#### Code analysis

To start testing your code using Snyk Code open your repository in a terminal and run the following command:

```javascript
snyk code test
```

To customize test options, run other commands, exclude directories and files, and explore the results in different formats, see the following:

* [Snyk CLI commands](../../snyk-cli/commands/#available-commands)
* [Exclude directories and files from the Snyk tests](../../snyk-cli/scan-and-maintain-projects-using-the-cli/using-snyk-code-from-the-cli/excluding-directories-and-files-from-the-snyk-code-cli-test.md)
* [Explore test results in a JSON or SARIF format in the terminal](https://github.com/taranvohra/SnykDocs/blob/main/docs/scan-applications/supported-languages-and-frameworks/broken-reference/README.md)
* [Exporting the test results to a JSON or SARIF file](https://github.com/taranvohra/SnykDocs/blob/main/docs/scan-applications/supported-languages-and-frameworks/broken-reference/README.md)

#### What's next?

* [Open a Fix PR](apex.md#open-a-fix-pr)
* [Configure PR Checks](../run-pr-checks/configure-pr-checks.md)

### Snyk integrations

:link: For integrated development environments, see [Use Snyk in your IDE](../../integrate-with-snyk/ide-tools/).

:link: If you prefer continuous integration/continuous delivery workflows, you can scan with Snyk based on the integration with your automation software (see [Snyk CI/CD](../../integrate-with-snyk/snyk-ci-cd-integrations/) and [Snyk API](../../snyk-api/)).

## Troubleshooting

If you need help, [contact Snyk Support](https://support.snyk.io/hc/en-us).
