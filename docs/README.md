# Home

Welcome to the Kontent.ai wiki! You can find some useful guidelines here that might help you get your OS project right.

---

## General Guidelines

- [Checklist for publishing a new OS project](Checklist-for-publishing-a-new-OS-project)
- [Guidelines for GitHub permissions in Kontent.ai organization](Guidelines-for-GitHub-permissions-in-Kontent-ai-organization)
- [Naming conventions](Naming-conventions)
- [Guidelines for SDK developers](Guidelines-for-SDK-developers)
- [Guidelines for Kontent related tools](Guidelines-for-Kontent-related-tools)
- [Duties of a Repository Maintainer](Duties-of-a-Repository-Maintainer)
- [New REST API feature](https://github.com/kontent-ai/.github/wiki/New-REST-API-feature)
- [CI, Automation, and Specific Stack Guidelines](CI-and-Automation-Guidelines)
    - .NET Specific Guidelines
        - [.NET GitHub Actions Guidelines](.NET-GitHub-Actions-Guidelines)
        - [Release & version management of .NET projects](Release-&-version-management-of-.NET-projects)
        - [Kontent.ai best practices for .csproj files](Kontent.ai-best-practices-for-.csproj-files)
    - [JavaScript & Node.js GitHub Actions Guidelines](JavaScript-Node.js-GitHub-Actions-Guidelines)
    - [Java GitHub Actions Guidelines](Java-GitHub-Actions-Guidelines)
    - [PHP GitHub Actions Guidelines](PHP-GitHub-Actions-Guidelines)
    - [Ruby GitHub Actions Guidelines](Ruby-GitHub-Actions-Guidelines)
    - [Swift GitHub Actions Guidelines](Swift-GitHub-Actions-Guidelines)

---

# Checklist for publishing a new OS project

Before you publish any repository under Kontent.ai organization on GitHub, please go through this checklist and make sure the repository is up to standards.

* [Repository name](#Repository-name)
* [Dedicate a maintainer](#dedicate-a-maintainer)🔒
* [Fulfill Community profile](#community-profile)🔒
* [Set up GitHub features](#github-features)🔒
* [Set Expectations](#expectations)🔒
* [Add badges](#badges)
* [Add automatic tests](#tests)❔
* [Set up Continuous Integration](#continuous-integration)❔
* [Protect Master Branch](#protect-the-master-branch)
* [Add collaborating teams](#add-collaborating-teams)🔒
* [Define release process](#releases)

## Repository name

Set repository name according to the [Naming conventions](./Naming-conventions).

## Dedicate a maintainer
- _🔒 Required for private repositories too_

It's essential to decide who's going to be responsible for the repository. Every repository needs to have an owner (a person or a team) who will actively:
- set the right expectations about the project
- keep the repository in a good shape

Read more on [the duties of a maintainer](Duties-of-a-Repository-Maintainer).

Mark this user into the [CODEOWNERS](https://help.github.com/articles/about-code-owners/) file. See an [example](https://github.com/kontent-ai/KInspector/blob/master/.github/CODEOWNERS).

# [Community profile](https://help.github.com/articles/about-community-profiles-for-public-repositories/)
- should be "all green"
- please note that it's available only for public repos and not for forked repos
![Green community profile](https://i.imgur.com/DVRjA41.png)

## Description, website, and topics
- _🔒 Required for private repositories too_

Fill in basic information about the project to make it easy to find it.
![Topics](https://i.imgur.com/4lNqMK6.png)

⚠ Tag the repository based on the division according to [Naming conventions](https://github.com/kontent-ai/.github/wiki/Naming-conventions#github-repositories).

In the case of private repositories, add a "private-repository" tag.

## README (Documentation)
- _🔒 Required for private repositories too_

README should contain:

- installation instructions
- basic demonstration of usage
- code examples (if applicable)

More complex topics and examples can be covered in separate articles in GitHub Wiki (or an external system such as ReadTheDocs).

> The template of the README file is stored in [repo-template](https://github.com/kontent-ai/repo-template).

## Contributing
From the README or CONTRIBUTING files, it should be clear:

- how to set up the project in order to contribute
  - this may include creating a PowerShell or other (e.g. build) script to make it easy for the contributors
- what kind of contributions are accepted and welcome
- what's the definition of done (use PR templates)
- which communication channels should be used to get in touch with the maintainer

> The template of CONTRIBUTING file is stored in [repo-template](https://github.com/kontent-ai/repo-template).

## License

Use the MIT license and set "Kontent.ai" as the copyright holder. If you want to use a different license, please contact the [DevRel team](mailto:devrel@kontent.ai).

Store the license in the "LICENSE.md" file in the root of the repository because it is being linked from "CONTRIBUTING.md" document.

> The template of the LICENSE file is stored in [repo-template](https://github.com/kontent-ai/repo-template).

## Issue & pull request templates & Code of Conduct

Use [repo-template](https://github.com/kontent-ai/repo-template) for the templates and Code of Conduct.

## GitHub features
- _🔒 Required for private repositories too_
Decide which features you turn on or off. This will help set expectations.

![GH Features](https://i.imgur.com/i6PICQv.png)

## Expectations
- _🔒 Required for private repositories too_

You should make clear:
- what kind of support users can expect (README)
  - GH issues vs. StackOverflow, etc.
- how to submit bugs (README + Issue/PR templates)
- what the future of the project is and whether it's actively developed (set up a [project/backlog](https://github.com/kontent-ai/delivery-sdk-net/projects) or [archive](https://help.github.com/articles/archiving-a-github-repository/) a repo that's no longer being developed)

In case of private repos, please add the following note to the top of the README:
> 🛈 This repository contains Kontent.ai's internal code that is of no use to the general public. Please explore our [other repositories](https://github.com/kontent-ai).

Set up an issue tracker. Most likely, you'll use GitHub issues. Take your time to set up labels and milestones.

## Badges
Use badges to make it easy to find basic information about the status of the project.

Pro tip: generate custom badges via https://shields.io/ ![Custom Badge](https://img.shields.io/badge/hellow-world-yellowgreen.svg?style=popout&logo=github)

Examples:
* Continuous Integration
    * [![Build & Test](https://github.com/kontent-ai/kontent-delivery-sdk-net/actions/workflows/integrate.yml/badge.svg)](https://github.com/kontent-ai/kontent-delivery-sdk-net/actions/workflows/integrate.yml)
* Test coverage
    * [Code Climate](https://codeclimate.com/github/codeclimate/codeclimate/badges) ![Code Climate Coverage](https://api.codeclimate.com/v1/badges/a99a88d28ad37a79dbf6/test_coverage)
* Static code analysis result
    * [Code Climate](https://codeclimate.com/github/codeclimate/codeclimate/badges) ![Code Climate](https://api.codeclimate.com/v1/badges/a99a88d28ad37a79dbf6/maintainability)
    * [SonarCloud](https://sonarcloud.io/documentation/user-guide/project-page/)
* Deployment/Package status
    * [Netlify](https://www.netlify.com/blog/2019/01/29/sharing-the-love-with-netlify-deployment-badges/)
    * [npm](https://docs.npmjs.com/)
    * [nuget](https://docs.microsoft.com/en-us/nuget/)
* Chat
    * [Stack Overflow](https://stackoverflow.com/) [![Stack Overflow](https://img.shields.io/badge/Stack%20Overflow-ASK%20NOW-FE7A16.svg?logo=stackoverflow&logoColor=white)](https://stackoverflow.com/tags/kontent-ai)
    * [Discord](https://discord.gg/SKCxwPtevJ) [![Discord](https://img.shields.io/discord/821885171984891914?label=Discord&logo=Discord&logoColor=white)](https://discord.gg/SKCxwPtevJ) (![Konten Discord](https://img.shields.io/discord/821885171984891914?color=%237289DA&label=Kontent%20Discord&logo=discord))

## Tests
- _❔ Optional, but highly recommended._

Include at least a basic set of (unit) tests.

## Review
- Ask your colleagues to do a code review, basic testing, and proofreading before you publish any project. The [DevRel team](mailto:devrel@kontent.ai) may also help.

# Continuous Integration
- _❔ Optional, but highly recommended._

Setting up CI, makes it easy for contributors to know whether their code works as expected. You can find more info about CI practices in the [separate article](https://github.com/kontent-ai/.github/wiki/CI-and-Automation-Guidelines).

- Set up a build agent - [GitHub Actions](https://docs.github.com/en/actions)
  - Make it run tests
  - Fail builds on failed tests
- Set up [status checks](https://docs.github.com/en/github/administering-a-repository/about-protected-branches#require-status-checks-before-merging) via webhooks

## Protect the master branch
You can learn more about branch protection in the [documentation](https://docs.github.com/en/github/administering-a-repository/managing-a-branch-protection-rule#about-branch-protection-rules).
![Branch protection](https://i.imgur.com/B4LVfUu.png)

## Add collaborating teams
- _🔒 Required for private repositories too_
![Collaborators](https://i.imgur.com/0qkbWe1.png)
>In most cases, it'll be `Admin` permission for the Developer Relations team and `Write` permission for the Employees team.

## Releases
- Create an initial release
- **Always** follow [Semantic Versioning](http://semver.org/)

## Want to make the repo even more friendly?
- Read the [Pre-launch checklist](https://opensource.guide/starting-a-project/#your-pre-launch-checklist).

# Guidelines for GitHub permissions in Kontent.ai organization
## Current Team Structure 

- Integrations
- Developer Relations
- .NET Maintainers
- JavaScript Maintainers

## Adding new members
New members should be assigned to one of the above teams based on their affiliation. Contact developer relations team at devrel@kontent.ai if you feel like a new team is required.

> For all Kontent.ai employees - your GitHub profile should have your real name filled (nickname/handle is up to you) and ideally a real-life profile picture.

⚠️ It's strictly forbidden to add users directly to repos. Only teams (roles) can be assigned to repos. This will allow us to manage [RBAC](https://en.wikipedia.org/wiki/Role-based_access_control).

# Naming conventions
## GitHub Repositories

* Repository name:
  * `kontent-ai-<project-name>` for [Kontent.ai](http://kontent.ai/) projects under the [Kontent.ai Github organization](https://github.com/kontent-ai/)
    * If the repository has any requirements for name, at least provide `kontent-ai` somewhere in the repository name (i.e. `sourcebit-source-kontent-ai`)
  * `kontent-ai-<project-name>` for any externally maintained Kontent.ai projects outside the Kontent.ai Github organization
* `<project-name>` guidelines:
  * Use a broad-to-specific convention to keep similar projects grouped together
    * e.g. kontent-ai-delivery-sdk-js + kontent-ai-delivery-sdk-net
  * If a particular project is a plugin/module/etc. for an existing technology with specific naming conventions, use those 
    * e.g. gatsby-source-kontent-ai or gridsome-source-kontent-ai
* Tagging
  * Tag with the `kontent-ai`
  * Use any other appropriate tags for the repo. (e.g. gatsby, gatsbyjs, source-plugin, etc.)

## Code

### Namespaces

We stick to [Microsoft's conventions](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/names-of-namespaces) `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`. Some examples:

  * `Kontent.ai.*` for Kontent.ai projects under the [Kontent.ai Github organization](https://github.com/kontent-ai/)
  * `<YourCompany>.Kontent.ai.*` for any externally maintained Kontent.ai projects 
  * `Kontent.ai.<Technology>*` for non-product related code. Eg. `Kontent.ai.AspNetCore.Http` if the code is related to `Microsoft.AspNetCore.Http`.

### Packages

* The name of the package should reflect the repo name
* When it makes sense use organization prefixes
  * e.g. @kontent-ai/kontent-ai-deliver-sdk-js
* For projects under the [Kontent.ai Github organization](https://github.com/kontent-ai/) ONLY:
  * Use appropriate icons from https://github.com/kontent-ai/.github/tree/master/images

# Guidelines for SDK developers
These guidelines cover all the requirements needed to create SDKs for the [Kontent.ai Delivery API](https://kontent.ai/learn/reference/delivery-api/) and should give you a solid starting point for developing SDKs in the framework of your choice.

The guidelines cover the following topics:

* [Expected SDK functionality](#expected-functionality)
* [Ensuring backward compatibility](#ensuring-backward-compatibility)
* [Format of the returned data](#returned-data)
* [Sending HTTP headers](#sending-http-headers)
* [Delivery API limits](#delivery-api-limits)
* [Naming conventions](#naming-conventions)
* [OS project requirements](#os-project-requirements)

## Expected functionality

### Required endpoints

The SDK must support the following Delivery API endpoints:

Method | Endpoint
---------|----------
GET | Retrieve a list of content items <br/> `https://deliver.kontent.ai/{project_id}/items`
GET | Retrieve a content item <br/> `https://deliver.kontent.ai/{project_id}/items/{item_codename}`
GET | Retrieve a list of content types <br/> `https://deliver.kontent.ai/{project_id}/types`
GET | Retrieve a content type <br/> `https://deliver.kontent.ai/{project_id}/types/{type_codename}`
GET | Retrieve a content type element <br/> `https://deliver.kontent.ai/{project_id}/types/{type_codename}/elements/{element_codename}`
GET | Retrieve a list of taxonomy groups <br/> `https://deliver.kontent.ai/{project_id}/taxonomies`
GET | Retrieve a taxonomy group <br/> `https://deliver.kontent.ai/{project_id}/taxonomies/{taxonomy_group_codename}`

### Feature support

The SDK should also support the following features:

Feature | Description
---------|----------
Delivery Preview API | Support for [previewing unpublished content items](https://kontent.ai/learn/tutorials/develop-apps/build-strong-foundation/set-up-preview/) via the Delivery Preview API.
Content filtering | Support for the [filtering parameters](https://kontent.ai/learn/reference/delivery-api/#tag/Filtering-content) when making queries to the Delivery API.
Localization | Support for retrieving localized content, that is using the `language` query parameter when retrieving content items.
Rendering Rich text elements | Support for rendering content (in other words, transforming HTML 5 fragments) of the built-in Rich text elements. This content includes links, images, components, and other content items.
Resolving links | Support for resolving hypertext links to other content items within the built-in Rich text elements.
Retrieving linked items | Support for retrieving content items and components that are used within other content items.

### Dynamic vs. static typing

We recommend that you use statically typed models for the SDK, if supported by a given stack. Otherwise, use dynamically typed models if your stack supports only those.

For information about content elements and their data types, see [Content element data types](#content-element-data-types) below.

## Ensuring backward compatibility

The Delivery API evolves in a way that is backward compatible. This means that, as long as SDKs and client applications follow a few rules, changes in the Delivery API won't break them.

The following changes to the Delivery API are **NOT** considered breaking changes and you should cope with them in your SDK.

* Add a new property to JSON objects.
* Change the order of JSON object properties (with exceptions, see below).
* Add a new type of content element.
* Add a new HTML element to the Rich text elements.
* Add a new attribute to HTML element in the Rich text elements.
* Add a new value to HTML element attribute in the Rich text elements.
* Change the order of HTML element attributes in the Rich text elements.
* Represent some characters as HTML entities.

**Note**: If a breaking change should happen, we will provide a new version of the Delivery API (alongside the current version of the API) together with new SDK guidelines. We will let you know in time before this happens.

You can always rely on the following features:

* Elements in content types are in the same order as in Kontent.ai UI.
* Elements in content item variants are in the same order as in content types.
* Options in Multiple choice elements in content types are in the same order as in Kontent.ai UI.
* Selected options in Multiple choice elements in content item variants are in the same order as in content types.

Here are a few tips to help you deal with backward-compatible changes in the Delivery API:

* Ignore unknown content elements.
* Parse HTML with HTML 5 parses. If possible, do not use regular expressions.
* Ignore unknown HTML elements – keep their content, but ignore their opening and closing tags.

## Returned data

The Delivery API returns data in the JSON format both for successful and [unsuccessful](#errors) requests.

### Object model descriptions of the returned data

When you query endpoints for retrieving all `/items`, `/types`, or `/taxonomies`, the Delivery API returns a paginated listing response with content that matches your specific query. In each case, the listing response contains a pagination object with information about the number of retrieved items, and a link to the next page of results.

You can find [descriptions and examples of the listing responses](https://kontent.ai/learn/reference/delivery-api/#operation/list-content-items) for content items, content types, and taxonomy groups in our API reference.

For details on the structure of the individual objects returned by the Delivery API (such as content items, content types, and taxonomy groups), see these pages in the API reference:

* [Content item model](https://kontent.ai/learn/reference/delivery-api/#section/Content-item-object)
* [Content type model](https://kontent.ai/learn/reference/delivery-api/#section/Content-type-object)
* [Taxonomy group model](https://kontent.ai/learn/reference/delivery-api/#section/Taxonomy-group-object)

### Content element data types

Content element | Data type | Limitation
--- | --- | ---
Text | string | Hard limit of 100,000 characters.
Rich text | string | Hard limit of 100,000 characters. **Note**: The limit includes HTML markup and whitespace characters.
Multiple choice | array of strings (selected options) | Can contain up to 250 predefined options.
Number | decimal | Numbers have the following format: "##########.##########" – 10 numbers before and after the decimal separator.
Date & time | string | [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) formatted string in the following format: YYYY-MM-DDTHH:MM:SSZ.
Asset | asset reference | The maximum asset size is 2 GB.
Modular content | array of strings (codenames of selected content items) | No limitation.
URL slug | string | Hard limit of 100,000 characters.
Custom element | string | Hard limit of 100,000 characters. **Note**: Custom elements behave as simple text-based elements.

You can find [example JSON values for each of the content elements](https://kontent.ai/learn/reference/delivery-api/#tag/Content-elements) in our API reference.

### Empty response vs. 404 error

The Delivery API differentiates between a query that doesn't bring any results (and gives a 200 OK response) and a query that gives a 404 Not found response.

For example, when you request a single item by codename and the item doesn't exist, the Delivery API responds with a 404 Not found. On the other hand, if you request items (with optional filter) and no item (or items matching the filtering criteria) exists, the Delivery API responds with 200 OK and returns an empty array of items. This applies to endpoints such as `/items`, `/types`, and `/taxonomies`.

### Errors

The Delivery API returns errors in the JSON format. Every error message has the same format. Here's an example of a general error message:

```json
{
  "message": "No HTTP resource was found that matches the request. Please read API documentation at https://kontent.ai/learn/reference/delivery-api.",
  "request_id": "|38a7b46fc8597a4aa1ab0169449cac54.c37263a1_",
  "error_code": 1,
  "specific_code": 0
}
```

The `message` property in the error message provides a clear specification of what went wrong when making the request.

## Sending HTTP headers

### Analytics

To gauge how much your SDK is used, we strongly recommend that the SDK sends a `X-KC-SDKID` header with each request to the API. The value of the header should be formatted like this `<SDK package origin>;<SDK name>;<SDK version>`, for example, `nuget.org;Kontent.Delivery;9.0.0` for version 9 of the [Delivery .NET SDK](https://github.com/kontent-ai/delivery-sdk-net).

This way we can identify the requests coming from your SDK and later provide you with information about its usage.

### Requesting latest content

By default, the Delivery API might serve stale content (if cached by the Fastly CDN) for performance reasons. In some cases, such as when [reacting to webhook notifications](https://kontent.ai/learn/reference/webhooks-reference/), you might want to request the latest content from your Kontent.ai project.

To do this within your SDK, include a `X-KC-Wait-For-Loading-New-Content` header and set it to `true` when sending requests to the API.

Including the header will cause the Delivery API to explicitly fetch new content from the specified Kontent.ai project.

## Delivery API limits

### Rate limitation

Delivery API requests are primarily served from a CDN network. For such requests, no rate limiting is in place. For uncached requests, a rate limitation of 100 per second and 2000 per minute is enforced. If a limit is reached, server responds with a 429 error and provides a `Retry-After` header, which tells you how long to wait before a request can be reattempted. All failed requests are safe to retry.

### URL length

The length of URLs for the GET requests is limited to 2048 characters. The Delivery API returns an [error](#errors) for URLs longer than 2048 characters.

## Naming conventions

Here are some recommendations on naming conventions for the SDK project name, the namespaces in your project, and package names. Following these recommendations will help others find the SDK more easily.

### Namespaces

* Main namespace: Kontent.ai
* Sub namespace: Name of the API (e.g., Delivery)
* Namespace separator: as per target platform
* Letter case: as per target platform

### Project name (GitHub repo name)

We recommend that the project for your SDK uses the following naming pattern: `[Main namespace] <Sub Namespace> <Platform> [Paradigm] SDK`. For example, for the Delivery .NET SDK, the project name would be _Kontent.ai Delivery .NET SDK_.

## OS project requirements

For your SDK to be included within the list Kontent.ai SDKs, the SDK project has to comply with our checklist for [Publishing an OS project](https://github.com/kontent-ai/.github/wiki/Checklist-for-publishing-a-new-OS-project). You can also read [Guidelines for building tools around Kontent.ai APIs](https://github.com/kontent-ai/.github/wiki/Guidelines-for-Kontent-related-tools) that should help you meet the requirements for creating a successful tool.

# Guidelines for Kontent.ai related tools
Welcome to Kontent.ai, developers! These guidelines should help you meet all the requirements for creating successful tools around Kontent APIs aligned with our values. It should also give you a solid starting point for development using the framework of your choice.

First of all, you should visit the [Kontent.ai Docs](https://docs.kontent.ai) which gives you overall knowledge about Kontent.ai possibilities and existing tools. Then check out the values of [Kontent.ai GitHub organization](https://github.com/kontent-ai/.github#readme).

## Guides

Once you know what you want to achieve and you haven't found an existing tool for that, read through the [naming conventions](https://github.com/kontent-ai/.github/wiki/Naming-conventions) and pick the right name for your tool. 

Before you publicly offer any tool, it is recommended to read through the [Kontent.ai Github checklist for publishing an OS project](https://github.com/kontent-ai/.github/wiki/Checklist-for-publishing-a-new-OS-project) to be aware of all enhancements you could implement to make the project more credible and well-perceived by the community.

## Analytics

To be able to better measure the adoption of your project, the tool should include the `X-KC-SOURCE` header with each request sent to Kontent.ai API ([Delivery](https://docs.kontent.ai/reference/delivery-api), [Management](https://docs.kontent.ai/reference/management-api-v2), and [Assets](https://docs.kontent.ai/reference/image-transformation)). The value of the header should be formatted as follows: `<Tool identification>;<Tool version>`. For example, `Acme.Kontent.Ai.AwesomeTool;1.0.0` or `@kontent-ai/awesome-tool-kontent-ai;0.1.42`. The version itself is not required, you can use just `Tool identification` like `kontent-ai-nuxt-module`. However, we strongly recommend including the version to be able to track adoption among multiple versions.

If you follow this recommendation, we can provide you with aggregated analytic data about your tool's usage later on.

---

If you have any additional questions or comments, you can contact us directly at devrel@kontent.ai.


# Duties of a Repository Maintainer

## The main duties
The maintainer is responsible for:
- [setting **the right expectations** about the project](#setting-expectations)
- [keeping the repository **in a good shape**](#keeping-the-repository-in-a-good-shape)

Repository ownership doesn't mean that the owner needs to do all the required work, it means that they ensure the work gets done.

## Setting expectations
### Responding to issues and pull requests
To set the expectations correctly, the maintainer will make sure that when an issue or a pull request is submitted, the issuer gets notified that a **human has seen the submission** and **what happens next**. This can mean:
  - telling the consumer whether the issue/PR will be fixed/merged or not
  - ETA of how long it will take until the next response or until the issue resolution/PR review
  - asking for more details

### Defining and communicating the vision
It's necessary to clearly express what's the **future of the project**. A good idea is to groom the backlog and decide on what the next major steps will be. A good tool to communicate the vision is the [GitHub Milestones](https://docs.github.com/en/github/managing-your-work-on-github/about-milestones) or [GitHub Projects](https://github.com/features/project-management/).

#### Obsolete projects
If the project is not to be maintained any longer, it's necessary to [archive](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/archiving-a-github-repository) it and ideally, add a disclaimer explaining why the repo is archived.

### SLA
**The first response** time and **any follow-up to a customer's reply** should not exceed **5 business days**. If a reply will take longer, it's necessary to update the expectation of the person waiting for the reply.

**The resolution time** depends on an actual issue/PR. Again, keep customer's expectations about the resolution time up to date.

## Keeping the repository in a good shape
The maintainer must ensure the repository is in a healthy state. This includes:
- the CI is present, running, and tests are passing
- there are no stale pull requests - they either get merged (after a review and testing) or closed
- the backlog of issues is accurate, up-to-date
  - the issue is labeled correctly, the descriptions are sufficient for anyone from the community to pick them up and process
- the repo is well documented (READMEs and Wikis are up to date and correspond with the latest version)
- adherence to standards and platform idioms (e.g. semantic versioning, using the right code style, targeting the right platform versions, adhering to conventions)
- making sure obsolete and broken packages are marked as deprecated and unlisted from package repositories (such as NuGet, npm, etc.)
- adherence to [internal standards checklist](Checklist-for-publishing-a-new-OS-project)

## Managing the releases and keeping them in sync with product development
The maintainer is responsible for making sure:
- critical issues get planned and addressed within the standard development process (e.g. bring issues to grooming/sprint planning)
- any product updates affecting the OS project get reflected (e.g. a new API endpoint should be reflected in SDKs and samples) - see [New REST API feature](https://github.com/kontent-ai/.github/wiki/New-REST-API-feature) for more information.
- versions of the OS project are being released regularly to reflect the needs of customers

The release process consists of two steps:

1. Publishing new version on the package manager (.NET -> Nuget, node/js -> npm, ...)
1. Ensuring the proper announcement
    * New feature is described in release changelog
    * Decide whether to announce new version in [product changelog](https://docs.kontent.ai/changelog/product-changelog)/discord/newsletter

## 💡 Make your life easier
Many of the tasks can be automated - e.g. [stale pull requests can be closed automatically](https://probot.github.io/apps/stale/), version management to be automated to a large extent, keeping things in sync with other systems like Jira can be automated. Be smart and automate!

# New REST API feature

SDK implementation is part of the feature opportunity. The new functionality should be covered by tests and reviewed by the maintainers (ideally primary contact) defined in the [CODEOWNERS](https://help.github.com/articles/about-code-owners/) file in the SDK repo.

## Ideal process of the submission

Let's image a new entity in Kontent.ai - let's call it a "note". As a part of the opportunity, the development team wants to introduce new endpoints connected to this entity to the Delivery REST API (to allow fetching user's notes) and adjust one other endpoint connected to the new entity - user entity will have a list of notes' IDs in the response. The ideal workflow would look like this:

> When you want to create a new branch right in the SDK repository, you need write access. In that case, contact anybody from the DevRel team to add according to [Adding new member section](https://github.com/kontent-ai/.github/wiki/Guidelines-for-GitHub-permissions-in-Kontent-ai-organization#adding-new-members).

* Development team decides to implement new opportunity
* Dev team contacts the maintainers of the respective SDKs. In this case .NET and JS SDKs.
    * They introduce the idea to the maintainer to get early feedback and information about SDK implementation.
* Once the feature is defined and the REST API contract is known (not implemented), the development team [submits the GitHub issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue) based on [feature request template](https://github.com/kontent-ai/repo-template/blob/master/.github/ISSUE_TEMPLATE/feature_request.md) describing the new feature to the respective SDK repositories listed in [develop apps overview](https://kontent.ai/learn/tutorials/develop-apps/overview) (such as this one for [.NET](https://github.com/kontent-ai/kontent-management-sdk-net/issues/120) and [JS](https://github.com/kontent-ai/kontent-management-sdk-js/issues/58)). *You can split the functionality into logical parts as separate issues - it is up to maintainer<->dev team agreement.*
    * For primary stacks - **Javascript and .NET** - assigns issue to dev team members -> see [Implementation checklist](#implementation-checklist) for scope.
* After the implementation part is done (implemented and successfully reviewed) - the maintainer will handle the release process.

## Implementation checklist

> Based on https://github.com/kontent-ai/repo-template/blob/master/.github/PULL_REQUEST_TEMPLATE.md

* Code follows coding conventions held in this repo
    * For .NET repositories the [standard Microsoft coding conventions appies](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
    * [Kontent.ai specific guidelines for repositories](https://github.com/kontent-ai/.github/wiki#general-guidelines) applies
    * If there are any other repo-specific requirements - they are described in the repo's README.
*  Automated tests have been added
    * Sufficient state is that happy path is covered.
        * Ideal state is to have the code fully covered (happy and unhappy path).
    * We do not test implementation of the REST API itself, it is possible to use Mocked server responses.
    * Repositories might contain tests for [Documentation code samples](https://github.com/Kontent-ai-Learn/kontent-ai-learn-code-samples)
* Docs have been updated
    * If new functionality in REST API is being showcased in [API reference](https://kontent.ai/learn/reference)
        * Create a pull request with a code sample based on the SDK you are implementing and for REST (as i.e. [this pull request for REST](https://github.com/Kontent-ai-Learn/kontent-ai-learn-code-samples/pull/42), [example for Javascript pull request](https://github.com/Kontent-ai-Learn/kontent-ai-learn-code-samples/pull/18)), or alternatively sync with the Customer Education to handle this separately. 
            * **⚠ Mind that the code samples should be published after the feature is released in the SDK.**
    * Validate whether there is a need for adjusting README in respective SDK repositories
* Temporary settings (e.g. variables used during development and testing) have been reverted to defaults
    * no sensitive keys have been committed to the codebase
    * no temporary project ID is being set in the pull request


## Release process

> Release process is being handled by maintainers (ideally primary contact) defined in the [CODEOWNERS](https://help.github.com/articles/about-code-owners/) file in the SDK repo.

See [Managing the releases and keeping them in sync with product development](https://github.com/kontent-ai/.github/wiki/Duties-of-a-Repository-Maintainer#managing-the-releases-and-keeping-them-in-sync-with-product-development) for more information.

# Continuous Integration and Continuous Delivery
> GitHub Actions are our primary automation platform - whenever it's possible, we recommend using [GitHub Actions](https://github.com/features/actions) - this will helps us with better maintenance. This page contains general info about GitHub Actions and their usage. Subpages focus on the specific stacks.

**Continuous integration** is the automation of building and testing. This means that typically, with some code changes, the machine checks whether it’s possible to build the project and whether your tests are passing. **Continuous delivery** is a little bit broader. To sum it up, this automation process will deploy or publish your code to various environments. This might be a little bit abstract and connected with the nature of your project, but you can visualize it as publishing to package registries like NPM or Nuget—or deploying your site to a staging or production environment.

For most Kontent.ai repositories, [we highly recommend](https://github.com/kontent-ai/.github/wiki/Checklist-for-publishing-a-new-OS-project#continuous-integration) adding automation workflows. With some basic automation, we want to perform automatic checks, tests and builds. Moreover, when it makes sense, it's a good practice to automate deploying or publishing processes to the respective registry. With this initiative, we aim to reduce human errors and increase productivity.

## GitHub Actions
GitHub Actions are the feature of GitHub that consists of the API and an environment for running your tasks. You just need to create a YAML file at a specific location in the repository. The configuration .yml file contains all the specific information about the environment, such as [trigger events](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions), [jobs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobs), or [strategies](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstrategy). Additionally, you can choose the environment where you want to run your tasks—it might be Linux, Windows, or even macOS.

## The anatomy of the Action
Each action is represented by a `.yml` file located directly in the repository at the `.github/workflows` location. To be able to run it, you need to allow the Actions feature in the repository’s Settings section.

## Secrets
It's common, the Action needs API keys or secrets to be able to release the version or perform some automation tasks. The practice is to use the [Repository](https://docs.github.com/en/actions/reference/encrypted-secrets) or [Organization secrets](https://github.blog/changelog/2020-05-14-organization-secrets/).

## YAML Cheatsheet
If you are not familiar with the `YAML` format, for the purposes of the GitHub Actions, you just need to know that key-value pairs are represented by `key: value`. The quotes for string values are optional. Nesting of objects is done by indentation (typically two spaces), and items of the array are denoted by a dash.

```yaml
key: value
  nested_property: Nested value
  my_array:
    - First Item
    - Second Item
```

### GitHub Actions basic syntax keys
* [name](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#name) - The name of the workflow.
* [on](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#on) - Is required, specifies events when you want to run your action.
* [jobs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobs) - A job is a unit of work; jobs run in parallel by default. Each job runs in a runner environment specified by runs-on.
* [jobs.<job_id>.runs-on](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on) - Is required, specifies the type of the machine to run the job.
* [jobs.<job_id>.steps](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idsteps) - A step is an individual task that can run commands in a job. A step can be either an action or a shell command. Each step in a job executes on the same runner, allowing the actions in that job to share data with each other ([definition by GitHub](https://docs.github.com/en/actions/learn-github-actions/introduction-to-github-actions#steps)).
* [jobs.<job_id>.steps[*].uses](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepsuses) - Selects an action to run as part of a step in your job. This is beneficial for reusing existing actions. You can check existing actions in the official [actions repository](https://github.com/actions) or on the [marketplace](https://github.com/marketplace?type=actions).
* [jobs.<job_id>.runs-on](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on) - Provides a shell where you can run your commands.

### Hello World Action
Let’s write the action that runs the code analysis tool every week. This action will run on Ubuntu, build the project, and will analyze code from our repository. The explanation of each line is described in the respective comment directly in the code. This example comes from the [.NET Delivery SDK repository](https://github.com/kontent-ai/kontent-delivery-sdk-net/blob/master/.github/workflows/codeql-analysis.yml).
```yaml
name: "Code scanning - action"   # Represents the name of the whole action.
on:   # Specifies the section where we describe our build triggers.
  push: # The action runs with push.
  pull_request: # The action runs with a pull request.
  schedule: # Specifies the section where we describe the schedule of running the action.
    - cron: '0 18 * * 1' # The CRON expression describing when to run the action.
jobs: # Specifies the section where we describe our jobs.
  CodeQL-Build: # Specific job section.
    runs-on: ubuntu-latest   # Describes the environment.
    steps: # Specifies the section where we describe the job's steps.
    - name: Checkout repository # The name of the step.
      uses: actions/checkout@v2 # Using already existing action actions/checkout@v2. This action provides us with access to the code of the repository.
      with: # Configuration of the action.
        fetch-depth: 2 # We must fetch at least the immediate parents so that if this is a pull request then we can checkout the head.
    - run: git checkout HEAD^2   # If this run was triggered by a pull request event, then checkout the head of the pull request instead of the merge commit.
      if: ${{ github.event_name == 'pull_request' }}   
    - name: Initialize CodeQL   # Initializes the CodeQL tools for scanning.
      uses: github/codeql-action/init@v1
      with:   # Override language selection by uncommenting this and choosing your languages
        languages: csharp
    - name: Setup .NET Core
      uses: actions/setup-dotnet@v1
      with:
        dotnet-version: 5.0.x
    - name: Install dependencies
      run: dotnet restore   # Command for the shell environment.
    - name: Build
      run: dotnet build --configuration Release --no-restore
    - name: Perform CodeQL Analysis
      uses: github/codeql-action/analyze@v1
```

### Real-world examples and syntax
It’s not possible to cover all capabilities and combinations for each stack here. Nevertheless, in the subpages, you can find some real-world examples—you can choose them for scaffolding your Action quickly for your specific stack and use case. They showcase configuration for various languages, platforms, and publishing to external package repositories. However, before you start with more advanced Actions, you'll need some more commands.
* [on.release.types](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#release) - Runs the action when a specific release event occurs.
* [on.<push|pull_request>.<branches|tags>](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#onpushpull_requestbranchestags) - Runs an action when push or pull request event occurs on a specific branch.
* [jobs.<job_id>.strategy.matrix](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstrategymatrix) - Allows to set different job configurations.
* [env](https://docs.github.com/en/actions/reference/context-and-expression-syntax-for-github-actions#env-context) - Context for specified environment variables.
* [env.NODE_AUTH_TOKEN](https://docs.github.com/en/actions/guides/publishing-nodejs-packages#publishing-packages-to-the-npm-registry) - Specifies the location of stored [NPM_TOKEN](https://docs.npmjs.com/creating-and-viewing-access-tokens). It’s a good practice to store secrets and keys to [Encrypted Secrets](https://docs.github.com/en/actions/reference/encrypted-secrets) storage of the repository.
* [jobs.<job_id>.if](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idif) - The job will run if the condition is met.

## Resources
* GitHub Actions [documentation](https://docs.github.com/en/actions)
* An article about GitHub Actions containing Kontent.ai specific examples: [With GitHub Actions, you don’t have to do boring tasks manually ever again](https://hackernoon.com/with-github-actions-you-dont-have-to-do-boring-tasks-manually-ever-again-301p356e)

# Specific Stack Guidelines

## .NET Specific Guidelines

### .NET GitHub Actions Guidelines

#### What the Action does 
The action gets the tag version, restores dependencies, and builds the project with a given configuration. Then the tests and code coverage tools are run. Eventually, the artifact is packaged and uploaded to the [Nuget](https://www.nuget.org/) and [GitHub Releases](https://docs.github.com/en/github/administering-a-repository/about-releases).
#### Notes
- Setting up of .NET environment is performed by [actions/setup-dotnet@v1](https://github.com/actions/setup-dotnet) action.
- Version tag is extracted using 3rd party [battila7/get-version-action@v2](https://github.com/battila7/get-version-action) action.
- Dependencies are restored by `run: dotnet restore` command.
- Build is performed by `dotnet build` command provided with configuration info and extracted tag version.
- Tests are performed by `dotnet test` command with respective parameters.
- Nuget packages artifacts are uploaded using [actions/upload-artifact@v2](https://github.com/actions/upload-artifact) action.
- Publishing of the Nuget Package is Performed by `dotnet nuget push` command with respective parameters and API keys.
- Package versions are set using `${{ steps.get_version.outputs.version-without-v }}` - you can find more info in the [documentation of the Action](https://github.com/marketplace/actions/get-version#version-without-v).
- Artifact is uploaded to GitHub Releases by [Roang-zero1/github-upload-release-artifacts-action@v2.1.0](https://github.com/Roang-zero1/github-upload-release-artifacts-action) action.
- Tokens and secrets are stored in the [Organization Secrets](https://github.blog/changelog/2020-05-14-organization-secrets/).

#### [GitHub Action example](https://github.com/kontent-ai/kontent-delivery-sdk-net/blob/master/.github/workflows/release.yml)
```yaml
name: Publish to NuGet
on:
  release:
    types: [published]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Setup .NET
      uses: actions/setup-dotnet@v1
      with:
        dotnet-version: 5.0.x
    - name: Extract version from tag
      id: get_version
      uses: battila7/get-version-action@v2
    - name: Restore dependencies
      run: dotnet restore
    - name: Build
      run: dotnet build --no-restore --configuration Release /p:ContinuousIntegrationBuild=true /p:Version="${{ steps.get_version.outputs.version-without-v }}"
    - name: Test
      run: dotnet test --no-build --verbosity normal --configuration Release /p:CollectCoverage=true /p:CoverletOutputFormat=opencover
    - name: Codecov
      uses: codecov/codecov-action@v1
    - name: Pack
      run: dotnet pack --no-build --include-symbols --verbosity normal --configuration Release --output ./artifacts /p:PackageVersion="${{ steps.get_version.outputs.version-without-v }}"
    - name: Upload artifacts
      uses: actions/upload-artifact@v2
      with:
        name: "NuGet packages"
        path: ./artifacts
    - name: Publish artifacts to NuGet.org
      run: dotnet nuget push './artifacts/*.nupkg' -s https://api.nuget.org/v3/index.json -k ${NUGET_API_KEY} --skip-duplicate
      env:
        NUGET_API_KEY: ${{ secrets.NUGET_API_KEY }}
    - name: Upload artifacts to the GitHub release
      uses: Roang-zero1/github-upload-release-artifacts-action@v2.1.0
      with:
        args: ./artifacts
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
### Release & version management of .NET projects

#### Milestones:
- use [milestones](https://docs.github.com/en/github/managing-your-work-on-github/about-milestones) to track what's about to be released (merged PRs)
  - **Title:**
    - when there is no milestone, create a new one called `vNext`
    - once there are issues/PRs assigned to a milestone, keep the version up to date according to [SemVer](https://semver.org)
  - **Description:** use a milestone's description to keep track of fixed issues and breaking changes (to be used later when releasing a new version)

#### Releasing a new version:
Once you're happy with the state of the `master` branch and want to release a new version:

1. Go to [Releases](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository)
2. [Draft a new release](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository#creating-a-release)
    - **Tag:** version according to [SemVer](https://semver.org), e.g. `4.0.0` or `v4.0.0` - both will work 
    - **Title:** can be a version number or a version number with a codename `4.0.0 - Cannonball`
    - **Description:** copy & past new features, bugfixes, and breaking changes from the milestone's description
    - **Pre-release:** check if the release is a pre-release and contains a [pre-release suffix](https://semver.org/#spec-item-9)
3. Publish the release
4. GitHub Actions will build the source using the `Release` configuration and upload the resulting artifacts to NuGet (and to the GitHub Release)
5. Close the current milestone and create a new one called `vNext`

### Version management

#### DOs:
- Use exclusively the `.csproj`'s `Version` attribute to manage package, assembly, or any other versions.
- Use `<GenerateAssemblyInfo>true</GenerateAssemblyInfo>`

#### DON'Ts:
- Don't use `PackageVersion`, `AssemblyVersion`, `AssemblyFileVersion`,`AssemblyInformationalVersion`, `VersionSuffix`, `VersionPrefix` (neither in the `.csproj` nor in the `AssemblyInfo.cs`)
- Don't use `GenerateAssemblyXYZ` attributes in `.csproj` (e.g. `GenerateAssemblyTitleAttribute`)
- Don't put any version or package information into `AssemblyInfo.cs`

To learn more about the purpose of the various attributes, read:
- https://andrewlock.net/version-vs-versionsuffix-vs-packageversion-what-do-they-all-mean/#fileversion

The `Version` attribute gets propagated to all other version numbers (unless overridden). In case you think you need more granular settings for your project, always contact devrel@kontent.ai.

#### `Version`
In Kontent.ai .NET projects (such as [kontent-ai-delivery-sdk-net](https://github.com/kontent-ai/delivery-sdk-net) or [kontent-ai-management-sdk-net](https://github.com/kontent-ai/kontent-ai-management-sdk-net) we **don't store a version number anywhere in the source files**.

The version of a release is determined by a [tag version](https://help.github.com/en/articles/creating-releases) and promoted to the NuGet package through the combination of [`dotnet build -p:Version=1.2.3`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-build) and [`dotnet pack -p:PackageVersion=1.2.3`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-pack).

#### Directory.build.props
This file lets you set shared properties for multiple `.csproj` files. It's automatically being picked up by MSBuild during the build. It's a good idea to use this file for attributes such as `<RepositoryUrl>`, `<IncludeSymbols>`, `<SymbolPackageFormat>`, or `<GenerateDocumentationFile>` that you typically want to manage in one place for the whole repository.

#### AssemblyInfo.cs

In case you want to get rid of the `AssemblyInfo.cs` completely and the only thing stopping you are the `InternalsVisibleToAttribute`s for tests, then you can [move them to `.csproj` or `.props` file](https://stackoverflow.com/a/49978185/1332034):

```xml
<ItemGroup>
    <AssemblyAttribute Include="System.Runtime.CompilerServices.InternalsVisibleTo">
      <_Parameter1>$(MSBuildProjectName).Test</_Parameter1>
    </AssemblyAttribute>
</ItemGroup>
```

#### SourceLink & Symbol publishing
It's mandatory for Kontent.ai .NET projects to have [SourceLink](https://github.com/dotnet/sourcelink/) enabled. This is the recommended configuration:

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <PublishRepositoryUrl>true</PublishRepositoryUrl>
    <EmbedUntrackedSources>true</EmbedUntrackedSources>
    <IncludeSymbols>true</IncludeSymbols>
    <SymbolPackageFormat>snupkg</SymbolPackageFormat>
  </PropertyGroup>
  <ItemGroup>
      <PackageReference Include="Microsoft.SourceLink.GitHub" Version="1.0.0-*" PrivateAssets="All"/>
  </ItemGroup>
</Project>
```

#### Documentation generation
Always use `<GenerateDocumentationFile>true</GenerateDocumentationFile>`. Don't use the `<DocumentationFile>` attribute if not necessary.

#### Repository & package metadata
The following attributes are required:
```xml
<PropertyGroup>
  <Authors>Kontent.ai</Authors>
  <Product>Kontent.ai</Product>
  <Copyright>© 2022 Kontent.ai. All rights reserved.</Copyright>
  <Description>✏️</Description>
  <PackageLicenseExpression>MIT</PackageLicenseExpression>
  <PackageProjectUrl>https://github.com/kontent-ai/✏️</PackageProjectUrl>
  <PackageIconUrl>https://github.com/kontent-ai/.github/blob/master/images/logo_nuget.png?raw=true</PackageIconUrl>
  <RepositoryUrl>https://github.com/kontent-ai/✏️.git</RepositoryUrl>
</PropertyGroup>
```

#### Target framework

For all [class libraries](https://docs.microsoft.com/en-us/dotnet/standard/class-libraries) target NET Standard 2.0 and .NET 6.

```xml
<TargetFrameworks>netstandard2.0;net6.0</TargetFrameworks>
```

For other types of projects (i.e. test projects, console applications) target .NET 5 and .NET 6.

```xml
<TargetFrameworks>net5.0;net6.0</TargetFrameworks>
```

:warning: [kontent-ai-aspnetcore](https://github.com/kontent-ai/kontent-ai-aspnetcore) targets .NET 5 and .NET 6, despite being a class library. Subject to change after .NET 7 adoption.


## JavaScript Node.js GitHub Actions Guidelines

At this time, the main CI used for building and publishing projects using JavaScript/TypeScript is [CircleCI](https://circleci.com/). The main target is to migrate all automation tasks to GitHub Actions. The research is being conducted, nevertheless, without any specific ETA yet. Right now, releasing the packages is performed manually.

### What the Action does
The Action install [npm](http://npmjs.com/) dependencies and run script defined in packages.json - it might be building testing or publishing of the artifact.

### Notes
- If the project contains browser logic or browser tests,  it might be a good idea to use the Windows environment in `jobs.<name>.runs-on property`. The default virtual environments come with a lot of preinstalled [browsers and tools](https://github.com/actions/virtual-environments/releases).
- The action uses [actions/setup-node@v1](https://github.com/actions/setup-node) action for setting Node.js environment.
- `node-version` array in the `strategy` section can be easily extended with the new versions.

### [GitHub Action example](https://github.com/kontent-ai/kontent-delivery-sdk-js/blob/master/.github/workflows/test.yml)
- The action runs a command defined in the `package.json` file.
```yaml
name: Test
on: [pull_request]
jobs:
  build:
    runs-on: windows-latest
    strategy:
      matrix:
        node-version: [14.x]
    steps:
    - uses: actions/checkout@v2
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v1
      with:
        node-version: ${{ matrix.node-version }}
    - run: npm ci
    - run: npm run test:all
```

## Java GitHub Actions Guidelines
### What the Action does
In this Action, the package is built and published using [Gradle](https://gradle.org/). The package is deployed to the [Nexus registry](https://www.sonatype.com/products/repository-oss).

### Notes
- It's recommended to use a Linux machine for building - `jobs.<name>.runs-on` property.
- For setting up Java environment, the action uses [actions/setup-java@v1](https://github.com/actions/setup-java) action.
- It's essential to grant execute permission for `gradlew` with `chmod +x gradlew`.
- The release is triggered by the `./gradlew publish` command.
- Secrets, keys, and tokens are stored in .env variables and secret properties.

### [GitHub Action example](https://github.com/kontent-ai/kontent-ai-java-packages/blob/master/.github/workflows/publish.yml)
- Build, test, and publish Java project to Nexus registry
```yaml
name: Publish package to the Maven Central Repository
on:
  release:
    types: [created]
jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Java
        uses: actions/setup-java@v1
        with:
          java-version: 1.8
      - name: Grant execute permission for gradlew
        run: chmod +x gradlew
      - name: Version release
        run: echo Releasing verion ${{ github.event.release.tag_name }}
      - name: Publish package
        run: ./gradlew publish
        env:
          RELEASE_TAG: ${{ github.event.release.tag_name }}
          NEXUS_USERNAME: ${{ secrets.NEXUS_USERNAME }}
          NEXUS_PASSWORD: ${{ secrets.NEXUS_PASSWORD }}
          SIGNING_KEY_ID: ${{ secrets.SIGNING_KEY_ID }}
          SIGNING_KEY: ${{ secrets.SIGNING_KEY }}
          SIGNING_PASSWORD: ${{ secrets.SIGNING_PASSWORD }}
```

## PHP GitHub Actions Guidelines
### What the Action does
This action sets up the PHP environment on the Ubuntu machine. It validates and caches [Composer](https://getcomposer.org/) packages. In the end, it runs a code coverage tool by [Codecov](https://about.codecov.io/). The package is then available on the [Packagist](https://packagist.org/) repository.

### Notes
- It's recommended to use a Linux machine for building - `jobs.<name>.runs-on` property.
- PHP versions are specified in `strategy.matrix.destination` property.
- The action uses 3rd party [shivammathur/setup-php@v2](https://github.com/shivammathur/setup-php) action for setting PHP environment.
- Package on Packagist will be automatically crawled periodically. You just have to make sure you keep the composer.json file up to date - for more info take a look at the [Packagist documentation](https://packagist.org/).
- Version of the package on Packagist is automatically fetched from the [tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging).

### [GitHub Action example](https://github.com/kontent-ai/kontent-ai-delivery-sdk-php/blob/master/.github/workflows/integrate.yml)
- PHP project using Composer and Codecov
```yaml
name: Build & Test & Report

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:        
        php-versions: ['7.0', '7.1', '7.2', '7.3']
        phpunit-versions: ['latest']
    steps:
    - uses: actions/checkout@v2
    - name: Setup PHP
      uses: shivammathur/setup-php@v2
      with:
        php-version: ${{ matrix.php-versions }}
        extensions: mbstring, intl
        ini-values: post_max_size=256M, max_execution_time=180
        coverage: xdebug        
        tools: php-cs-fixer, phpunit:${{ matrix.phpunit-versions }}
    - name: Validate composer.json and composer.lock
      run: composer validate --strict
    - name: Cache Composer packages
      id: composer-cache
      uses: actions/cache@v2
      with:
        path: vendor
        key: ${{ runner.os }}-php-${{ hashFiles('**/composer.lock') }}
        restore-keys: |
          ${{ runner.os }}-php-
    - name: Install dependencies
      run: composer install --prefer-dist --no-progress --no-suggest
    - name: Coverage
      run: vendor/bin/phpunit --coverage-clover coverage.xml
    - name: Codecov
      uses: codecov/codecov-action@v1  
```

## Ruby GitHub Actions Guidelines
### What the Action does
The action runs with the GitHub release. The action installs dependencies, runs tests, and publishes gem to [Rubygems](https://rubygems.org/gems/kontent-delivery-sdk-ruby).

### Notes
- It's recommended to use Linux machine for building - `jobs.<name>.runs-on` property.
- For publishing, the action uses 3rd party [dawidd6/action-publish-gem@v1](https://github.com/dawidd6/action-publish-gem) action.
- The SDK uses GitHub releases.

### [GitHub Action example](https://github.com/kontent-ai/kontent-delivery-sdk-ruby/blob/master/.github/workflows/publish-gem.yml)
- Build test and publish gem to Rubygems
```yaml
name: publish-gem

on:
  release:
    types: [published]

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Set up Ruby
      uses: ruby/setup-ruby@v1
      with:
        ruby-version: 2.6
    - name: Install dependencies
      run: bundle install
    - name: Run tests
      run: bundle exec rake
    - name: Publish gem
      uses: dawidd6/action-publish-gem@v1
      with:
        api_key: ${{secrets.RUBYGEMS_API_KEY}}
```

## Swift GitHub Actions Guidelines
### What the Action does
Once the release is triggered, dependencies are installed, then the project is built, tested and a new version is released to [Cocoapods](https://cocoapods.org/).

### Notes
- It is recommended to run builds for Swift/Apple platforms on a macOS machine - `jobs.<name>.runs-on` property.
- Target platforms are specified in `strategy.matrix.destination` property.
- Manual steps for the releasing of the new version - https://github.com/kontent-ai/kontent-delivery-sdk-swift#releasing-a-new-version-of-the-cocoapod-package
- Before building, the [Cocoapods package manager](https://cocoapods.org/) is installed, repo (trunk mirror) is updated and dependencies are installed.
```bash
gem install cocoapods
pod repo update
pod install --project-directory=Example
set -o pipefail && xcodebuild test -enableCodeCoverage YES -workspace Example/KontentAiDelivery.xcworkspace -scheme KontentAiDelivery-Example -sdk iphonesimulator -destination 'name=iPhone 11' ONLY_ACTIVE_ARCH=NO | xcpretty
```
- Built dependency pod is pushed to the [Cocoapod trunk](https://guides.cocoapods.org/making/getting-setup-with-trunk.html).
```bash
pod trunk push
```

### [GitHub Action example](https://github.com/kontent-ai/kontent-delivery-sdk-swift/blob/master/.github/workflows/publish.yml)
- Build test and publish to Cocoapods project written in Swift

```yaml
on:
  release:
    types: [published]
name: publish-to-cocoapods
jobs:
  publish-to-cocoapods:
    name: publish-to-cocoapods
    runs-on: macOS-latest
    strategy:
        matrix:
          destination: ['platform=iOS Simulator,OS=12.2,name=iPhone 11']
    steps:
      - name: Checkout
        uses: actions/checkout@master
      - name: Build and test
        run: |
          gem install cocoapods
          pod repo update
          pod install --project-directory=Example
          set -o pipefail && xcodebuild test -enableCodeCoverage YES -workspace Example/KontentAiDelivery.xcworkspace -scheme KontentAiDelivery-Example -sdk iphonesimulator -destination 'name=iPhone 11' ONLY_ACTIVE_ARCH=NO | xcpretty
      - name: Publish Cocoapod
        run: pod trunk push
        env:
          COCOAPODS_TRUNK_TOKEN: ${{ secrets.COCOAPODS_TRUNK_TOKEN }}
```



