# Enterprise implementation guide

Each business and environment is different. With that in mind, this guide aims to help an enterprise business to implement Snyk. We provide recommendations to implement a large-scale rollout, focusing on the stages needed to help get towards an ideal rollout.

We start with the awareness that most businesses:

* Have a backlog of issues in their existing software.
* Are continuously creating new software, and need to secure new code.

**Typical timelines**

If your business is small and nimble, Snyk implementation can be achieved in days. You can start scanning with Snyk soon after purchasing, often using the Git integration and [API Import Tool](../../snyk-api/other-tools/tool-snyk-api-import/). See the [Getting started](../../getting-started/) and [Start scanning](../../scan-using-snyk/start-scanning-using-the-cli-web-ui-or-api.md) sections for details of this type of process

However, for larger, more process-oriented enterprises, this process may take weeks or months, and it requires more detailed planning to succeed.

## Implementation strategy overview

This guide is composed of multiple phases, outlining a series of actions that align with three goals:

* [Achieve visibility](./#achieve-visibility)
* [Achieve prevention and drive developer adoption](./#achieve-prevention-and-drive-developer-adoption)
* [Fix the backlog and triage issues](./#fix-the-backlog-and-triage-issues)

### Achieve visibility

For large businesses, we recommend you first focus on visibility - getting a clear sense of the security issues, but without always fixing them.

{% hint style="warning" %}
This does not stop you from fixing issues using Snyk. You can start fixing issues early, but the emphasis is to avoid blocking development early on, build trust, and slowly introduce gating in later phases, usually the prevention phase.
{% endhint %}

Visibility achieves a broad view of security across your application portfolio, avoids Snyk scans being seen as a blocker, and minimizes impact on development processes.

This visibility helps build trust while rolling out Snyk.

### Achieve prevention and drive developer adoption

Next is the prevention stage; stopping new security issues from being added to your applications. During this stage, you can put controls in place to allow developers to see issues in their pipelines using Pull Request (PR)/Merge Request (MR) checks, and checks in the pipeline that may block.

As part of this, developers may use IDE plugins and other tools like [Snyk Advisor](https://snyk.io/advisor) to select secure packages, and [Snyk Learn](https://learn.snyk.io/) to educate on secure coding, security, and the product.

### Fix the backlog and triage issues

Finally, you can focus on fixing your backlog of security issues. This can take several forms:

* As part of the initial rollout, security or initial stakeholder may triage the initial results for the existing portfolio, create tickets for priority items to investigate or address, or have the teams do that for their applications as part of the weekly triage process.
* After getting visibility and achieving prevention, you can look at your backlog of issues. For example, a weekly triage process with the key stakeholders can guide the teams on what to address.

## Use enhanced resources with Snyk

Snyk was built with developers in mind, providing:

* Tools to create secure applications using integrations for IDE, Git, and CI/CD.
* [Snyk Advisor](https://snyk.io/advisor) and other tools to make decisions.
* [Snyk Learn](https://learn.snyk.io) training materials on products, securing code, and best practices.
* [Policies](../../manage-risk/policies/) that allow security and compliance teams to provide direction.
