# Snyk CLI for Snyk Code

The [Snyk Command Line Interface](../../) (CLI) enables you to bring the functionality of Snyk Code into your development workflow. Using the Snyk CLI, you can run Snyk Code tests locally or incorporate them into your CI/CD pipeline to scan your source code for security vulnerabilities.

## Prerequisites for using the Snyk CLI with Snyk Code

Before using the Snyk CLI for testing your source code with Snyk Code, verify you have the following prerequisites:

* A Snyk account.\
  For more information, see [Create a Snyk account](../../../getting-started/quickstart/create-or-log-in-to-a-snyk-account.md).
* Repositories with code in a supported language and framework.\
  For more information, see [Snyk Code - Supported languages and frameworks](../../../scan-using-snyk/supported-languages-and-frameworks/supported-languages-frameworks-and-feature-availability-overview.md).
* The **Snyk Code** option [enabled in your Snyk Org settings](../../../scan-using-snyk/snyk-code/scan-code/enable-the-snyk-code-option.md).
* The Snyk CLI installed and authenticated.
  * For instructions, see [Install or update the Snyk CLI](../../install-or-update-the-snyk-cli/) and [Authenticate the Snyk CLI](../../authenticate-the-cli-with-your-account.md).
  * The minimum Snyk CLI version for Snyk Code, version 1.716.0. Snyk recommends using the latest version of the CLI.

## Using the Snyk CLI for Snyk Code tests

To test your repository code using the Snyk CLI, use the [`snyk code test`](../../commands/code-test.md) command.\
For more information, see [Testing your source code via the CLI](testing-your-source-code-using-the-cli.md).

Before running Snyk Code tests with the CLI, you may want to do the following:

* [Update your Snyk CLI version](../../install-or-update-the-snyk-cli/).
* [Set the Organization for the CLI tests](set-the-snyk-organization-for-the-cli-tests.md).
* [Exclude directories and files from the Snyk Code test](excluding-directories-and-files-from-the-snyk-code-cli-test.md).

After running a Snyk Code test, you can do the following:

* [Explore the Snyk Code CLI results](https://github.com/taranvohra/SnykDocs/blob/main/docs/snyk-cli/scan-and-maintain-projects-using-the-cli/using-snyk-code-from-the-cli/broken-reference/README.md).
* [Filter the CLI results, and display only issues with a specific severity level and higher](https://github.com/taranvohra/SnykDocs/blob/main/docs/snyk-cli/scan-and-maintain-projects-using-the-cli/using-snyk-code-from-the-cli/broken-reference/README.md).
* [Output the CLI results to a JSON or SARIF format in the terminal](https://github.com/taranvohra/SnykDocs/blob/main/docs/snyk-cli/scan-and-maintain-projects-using-the-cli/using-snyk-code-from-the-cli/broken-reference/README.md).
* [Export the CLI results to a JSON or SARIF format file](https://github.com/taranvohra/SnykDocs/blob/main/docs/snyk-cli/scan-and-maintain-projects-using-the-cli/using-snyk-code-from-the-cli/broken-reference/README.md).
* [Display the CLI results in an HTML format using the Snyk-to-HTML feature](../cli-tools/snyk-to-html/).
