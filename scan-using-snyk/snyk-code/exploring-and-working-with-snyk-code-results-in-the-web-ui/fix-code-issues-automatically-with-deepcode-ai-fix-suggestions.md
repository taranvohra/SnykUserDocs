# Fix code vulnerabilities automatically

{% hint style="warning" %}
DeepCode AI Fix Suggestions is in [Open Beta](../../../more-info/snyk-feature-release-process.md) and fully supports Javascript/Typescript frameworks.

To enable the feature, see [Enable DeepCode AI Fix Suggestions](fix-code-issues-automatically-with-deepcode-ai-fix-suggestions.md#enable-deepcode-ai-fix-suggestions)
{% endhint %}

Fix the security issues and quality flaws in the source code through an automated flow. DeepCode AI Fix Suggestions calculates the most suitable solution for your issues and applies it automatically.

## Why use Fix Suggestions?

Fix Suggestions combines the power of a thorough program analysis engine with the abilities of an in-house deep learning-based large language model. This combination allows for compiling large amounts of unstructured language information [from open-source code](fix-code-issues-automatically-with-deepcode-ai-fix-suggestions.md#what-data-does-deepcode-ai-fix-suggestions-collect).

Key features set Fix Suggestions apart. It has a neural network trained on millions of lines of code, allowing for greater versatility and creativity. The [Snyk Code engine](../snyk-code-key-features/snyk-code-local-engine.md) rigorously checks the suggestions from the neural network, ensuring all automated fixes are small and targeted to each vulnerability or code issue.

## What issues can you fix automatically?

You can address various issues detected by the Snyk Code engine, in terms of quality, promoting best code practices, and security vulnerabilities. DeepCode AI Fix currently does not support inter-file fixes.

## How Fix Suggestions works

A representation of information flow involved in fixing one issue is presented in the following table.

<table><thead><tr><th width="211">Stage</th><th data-type="select">Subsystem</th><th>Details</th></tr></thead><tbody><tr><td>Code scan and discovery of issues</td><td></td><td>Corresponds to a normal flow of scanning the code from IDE.</td></tr><tr><td>Code preprocessing and minimization with respect to the data flow of the particular issue <span class="math">\mathcal{I}</span></td><td></td><td>Data flow of <span class="math">\mathcal{I}</span> is analyzed and code is minimized, keeping the relevant context only.</td></tr><tr><td>Generating <span class="math">k</span> candidate fixes for the given issue <span class="math">\mathcal{I}</span></td><td></td><td>Here, <span class="math">k</span> is an implementation parameter.</td></tr><tr><td>Candidate fixes ranking and self-assessment</td><td></td><td>Each of the <span class="math">k</span> fixes is assessed by the Code Engine, filtering out those rendering invalid code or failing to fix the issue (the issue persists).</td></tr><tr><td>Returning the best candidate fix</td><td></td><td>The system has finished.</td></tr></tbody></table>

## Requirements for Fix Suggestions

* Snyk Security Code, Open Source Dependencies, IaC Configurations IDE plugin. Available for IDE plugins that use Language Server, such as [VS Code](https://marketplace.visualstudio.com/items?itemName=snyk-security.snyk-vulnerability-scanner-preview) and [Eclipse](https://marketplace.eclipse.org/content/snyk-security-code%E2%80%8B-open-source%E2%80%8B-iac-configurations).
* Available in the USA Multi-Tenant region.\
  To learn where Snyk offers data residency, see [What regions are available?](../../../more-info/data-residency-at-snyk.md#what-regions-are-available)

## Fix Suggestions language support

Fix Suggestions supports only [Javascript](https://github.com/taranvohra/SnykDocs/blob/main/docs/scan-using-snyk/snyk-code/exploring-and-working-with-snyk-code-results-in-the-web-ui/broken-reference/README.md) and Typescript.

## Enable DeepCode AI Fix Suggestions

Enable DeepCode AI Fix Suggestions for your Organization in Snyk Web UI by navigating to **Settings** > **Snyk Preview**.

<figure><img src="../../../.gitbook/assets/enable_fix_suggestions_snyk_preview.png" alt="DeepCodeAI Fix Suggestions settings in Snyk Preview"><figcaption><p>DeepCodeAI Fix Suggestions settings in Snyk Preview</p></figcaption></figure>

{% hint style="info" %}
**Prerequisites for enabling Fix Suggestions**

* Save the file before fixing an issue, as it requires clean code (saved code) to provide a fix.
* Snyk recommends that when you save the code, you re-run the analysis to show code actions, such as **Fix this issue**.
* You can request a fix by clicking **Fix this issue** in Code Lense and then saving the file. If your plugin settings are set to test automatically when saving, it will trigger the Snyk Code Analysis, and as a result, the issue disappears.
{% endhint %}

## Example: Fix code issue automatically

Consider the following scenario where hardcoded credentials are fixed using DeepCode AI Fix Suggestions.

Snyk highlights hardcoded credentials as a vulnerability by adding a **Fix this issue** element in the IDE.

<figure><img src="../../../.gitbook/assets/fix_suggestions_discovery (1).png" alt="Discovering a vulnerability in the code"><figcaption><p>Discovering a vulnerability in the code</p></figcaption></figure>

The issue is fixed by replacing the credentials with environment variables.

<figure><img src="../../../.gitbook/assets/fix_suggestions_fix_applied (1).png" alt="Fix applied with DeepCode AI Fix"><figcaption><p>Fix applied with DeepCode AI Fix</p></figcaption></figure>

You can follow the entire sequence in this short (12-second) video.

<figure><img src="../../../.gitbook/assets/fix_hardcoded_secret.gif" alt="Fix hardcoded credentials with DeepCode AI Fix"><figcaption><p>Fix hardcoded credentials with DeepCode AI Fix</p></figcaption></figure>

## What data does DeepCode AI Fix Suggestions collect?

The Large Language Model (LLM) is trained exclusively on public repositories with permissive licenses. If a license for a repository changes after the initial scrape, the repository is immediately excluded from the training data. During the inference, DeepCode AI Fix Suggestions does not collect or send the client data to third parties.

The data collection process is thorough and includes the following:

* Static analysis
* Automated assessment of the suggested fix qualities
* Partial in-house labeling by humans

The training data is ensured to be of the highest quality to optimize the performance of the LLM.

For more information, see [How Snyk handles your data](../../../more-info/how-snyk-handles-your-data.md).
