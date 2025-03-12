<!-- markdownlint-disable MD033 MD041 -->
<h1 align="center">
    Best-of Generator
</h1>

<p align="center">
    <strong>🏆&nbsp; Generates a ranked markdown list of awesome libraries and tools.</strong>
</p>

<p align="center">
    <a href="https://best-of.org" title="Best-of Badge"><img src="http://bit.ly/3o3EHNN"></a>
    <a href="https://pypi.org/project/best-of/" title="PyPi Version"><img src="https://img.shields.io/pypi/v/best-of?color=green&style=flat"></a>
    <a href="https://github.com/best-of-lists/best-of-generator/actions?query=workflow%3Abuild-pipeline" title="Build status"><img src="https://img.shields.io/github/actions/workflow/status/best-of-lists/best-of-generator/build-pipeline.yml?style=flat"></a>
    <a href="https://gitter.im/ml-tooling/best-of" title="Chat on Gitter"><img src="https://badges.gitter.im/ml-tooling/best-of.svg"></a>
    <a href="https://bestoflists.substack.com/subscribe" title="Subscribe for updates"><img src="http://bit.ly/2Md9rxM"></a>
    <a href="https://twitter.com/best_of_lists" title="Best-of on Twitter"><img src="https://img.shields.io/twitter/follow/best_of_lists.svg?style=social&label=Follow"></a>
</p>

<p align="center">
  <a href="#getting-started">Getting Started</a> •
  <a href="#documentation">Documentation</a> •
  <a href="#support--feedback">Support</a> •
  <a href="https://github.com/best-of-lists/best-of-generator/issues/new?labels=bug&template=01_bug-report.md">Report a Bug</a> •
  <a href="#contribution">Contribution</a> •
  <a href="https://github.com/best-of-lists/best-of-generator/releases">Changelog</a>
</p>

The best-of-generator is a CLI tool to generate a markdown page of ranked open-source projects based on a list of projects defined in a `yaml` file. It is integrated with different package managers - such as PyPI, NPM, Conda, and Docker Hub - to automatically collect a variety of project metadata and calculate project-quality scores. It also comes with a GitHub Action workflow for a fully automized update process.

> 🧙‍♂️ Create your own best-of list in just 3 minutes with [this guide](https://github.com/best-of-lists/best-of/blob/main/create-best-of-list.md).

## Highlights

- 📇&nbsp; Generates a beautiful markdown page from a `yaml` list.
- 🔌&nbsp; Integrates various package managers (npm, pypi, conda ...).
- 🥇&nbsp; Calculates a project-quality score based on a variety of metrics.
- 📈&nbsp; Identifies trending projects based on collected metrics.
- 🔄&nbsp; GitHub Action workflow for automated weekly updates.

## Getting Started

> 🧙‍♂️ If you want to create your own best-of list, we strongly recommend to follow [this guide](https://github.com/best-of-lists/best-of/blob/main/create-best-of-list.md) instead of setting up best-of manually. With the guide, it will only take about 3 minutes to get you started. It is already set-up to automatically run the best-of generator via our GitHub Action and includes other useful template files. Installing the best-of CLI tool is not required.

1. Install best-of generator via pip:
    ```bash
    pip install best-of
    ```
2. Create a `projects.yaml` file based on the [documented structure](#projectsyaml-structure). This file should contain at least one project. For example:
    ```yaml
    projects:
       - name: "best-of-ml-python"
         github_id: "ml-tooling/best-of-ml-python"
    ```
3. Run best-of generator via command-line:
   ```bash
   best-of generate -g <GITHUB_API_TOKEN> ./projects.yaml
   ```

You can find further information on how to configure the `projects.yaml` file and additional features in the [documentation section](#documentation) below.

## Support & Feedback

This project is maintained by [Benjamin Räthlein](https://twitter.com/raethlein), [Lukas Masuch](https://twitter.com/LukasMasuch), [Jan Kalkan](https://www.linkedin.com/in/jan-kalkan-b5390284/), and [Johannes Rieke](https://twitter.com/jrieke). Please understand that we won't be able to provide individual support via email. We also believe that help is much more valuable if it's shared publicly so that more people can benefit from it.

| Type                     | Channel                                              |
| ------------------------ | ------------------------------------------------------ |
| 🚨&nbsp; **Bug Reports**       | <a href="https://github.com/best-of-lists/best-of-generator/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+label%3Abug+sort%3Areactions-%2B1-desc+" title="Open Bug Report"><img src="https://img.shields.io/github/issues/best-of-lists/best-of-generator/bug.svg?label=bug"></a>                                 |
| 🎁&nbsp; **Feature Requests**  | <a href="https://github.com/best-of-lists/best-of-generator/issues?q=is%3Aopen+is%3Aissue+label%3Afeature+sort%3Areactions-%2B1-desc" title="Open Feature Request"><img src="https://img.shields.io/github/issues/best-of-lists/best-of-generator/feature.svg?label=feature%20request"></a>                                 |
| 👩‍💻&nbsp; **Usage Questions**   |  <a href="https://github.com/best-of-lists/best-of-generator/issues?q=is%3Aopen+is%3Aissue+label%3Asupport+sort%3Areactions-%2B1-desc" title="Open Support Request"> <img src="https://img.shields.io/github/issues/best-of-lists/best-of-generator/support.svg?label=support%20request"></a> <a href="https://gitter.im/ml-tooling/best-of" title="Chat on Gitter"><img src="https://badges.gitter.im/ml-tooling/best-of.svg"></a> |
| 📢&nbsp; **Announcements** | <a href="https://gitter.im/ml-tooling/best-of" title="Chat on Gitter"><img src="https://badges.gitter.im/ml-tooling/best-of.svg"></a> <a href="https://bestoflists.substack.com/subscribe" title="Subscribe for updates"><img src="http://bit.ly/2Md9rxM"></a> <a href="https://twitter.com/best_of_lists" title="Best-of on Twitter"><img src="https://img.shields.io/twitter/follow/best_of_lists.svg?style=social&label=Follow"> |
| ❓&nbsp; **Other Requests** | <a href="mailto:best-of@mltooling.org" title="Email best-of team"><img src="https://img.shields.io/badge/email-best of-green?logo=mail.ru&logoColor=white"></a> |

## Documentation

<p align="center">
  <a href="#projectsyaml-structure">YAML Structure</a> •
  <a href="#projects">Projects</a> •
  <a href="#categories">Categories</a> •
  <a href="#labels">Labels</a> •
  <a href="#configuration">Configuration</a> •
  <a href="#project-quality-score">Project Quality Score</a> •
  <a href="#trending-projects">Trending Projects</a> •
  <a href="#generation-via-cli">CLI</a> •
  <a href="#generation-via-github-action">GitHub Action</a> •
  <a href="#generation-via-python-api">Python API</a>
</p>

The best-of generator is a CLI tool to generate a markdown page from a list of projects configured in a `yaml` file. The documentation sections below will provide information on the [`projects.yaml` structure](#projectsyaml-structure), on its different sections ([projects](#projects), [labels](#labels), [categories](#categories) & [configuration]((#configuration))), on some of the best-of features (e.g. [project-quality score](#project-quality-score) & [trending projects](#trending-projects)), and instructions on how to run the markdown generation [via the command-line interface](#generation-via-cli) or [via GitHub Actions](#generation-via-github-action).

### `projects.yaml` Structure

The `projects.yaml` file has the following structure:

- `configurations` (optional): Can be used to overwrite the default configuration of the best-of list. More information in the [configuration section](#configuration).
- `categories` (required): All used categories should be listed here with at least a descriptive title. More information in the [categories section](#categories).
- `labels` (optional): Used labels can be added here to extend the label with additional aspects (e.g. URL, image, description). More information in the [labels section](#labels).
- `projects` (required): All projects that are supposed to be shown in the generated markdown page should be listed here. More information in the [projects section](#projects).

The following `yaml` shows a small example:

```yaml
# Optional: change the default configuration
configuration:
    markdown_header_file: "config/header.md"
    markdown_footer_file: "config/footer.md"

# Optional: add categories
categories:
  - category: "data-engineering"
    title: "Machine Learning & Data Engineering"
    subtitle: "Best-of lists about machine learning, data engineering, data science, or other topics related to big data."

# Optional: add labels
labels:
  - label: "python"
    image: "https://www.python.org/static/favicon.ico"
    description: "Best-of list with Python projects"

# Required: list of all projects
projects:
  - name: "best-of-ml-python"
    github_id: "ml-tooling/best-of-ml-python"
    labels: ["python"]
    category: "data-engineering"
```

### Projects

A project is the main component of a best-of list. In most cases, a project is hosted on GitHub and released on different package managers. Such a project should be added with the `github_id` and the IDs of all the package managers it is released to. However, it is also possible to add projects which are not hosted on GitHub or released on a package manager, as shown in the example below.

#### Project Examples

```yaml
projects:
  # Projects with different package managers:
  - name: "Tensorflow"
    github_id: "tensorflow/tensorflow"
    pypi_id: "tensorflow"
    conda_id: "conda-forge/tensorflow"
    dockerhub_id: "tensorflow/tensorflow"
  - name: "Best-of Generator"
    pypi_id: "best-of"
    github_id: "best-of-lists/best-of-generator"
  # Link to another project collection:
  - name: "Best-of Overview"
    homepage: "https://best-of.org"
    resource: True
  # Project that is not on GitHub:
  - name: "Quart"
    pypi_id: "quart"
    homepage: "https://gitlab.com/pgjones/quart"
    description: "Quart is a Python ASGI web microframework with the same API as Flask."
    license: "MIT"
    star_count: 772
    show: True
```

The example above will be rendered as shown below:

![Projects Example](./docs/images/best-of-generated-projects-framed.png)

Every project can also be expanded to show additional project information (by clicking on the project), for example:

![Project Body Example](./docs/images/best-of-project-body-framed.png)

#### Project Properties

<table>
    <tr>
        <th>Property</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>name</code></td>
        <td>Name of the project. This name is required to be unique on the best-of list.</td>
    </tr>
    <tr>
        <td colspan="2"><b>Optional Properties:</b></td>
    </tr>
    <tr>
        <td><code>github_id</code></td>
        <td>GitHub ID of the project based on user or organization  and the repository name, e.g. <code>best-of-lists/best-of-generator</code>. If the project is hosted on GitLab, please use the <code>gitlab_id</code> property.</td>
    </tr>
    <tr>
        <td><code>category</code></td>
        <td>Category that this project is most related to. You can find all available category IDs in the <code>projects.yaml</code> file. The project will be sorted into the <code>Others</code> category if no category is provided.</td>
    </tr>
    <tr>
        <td><code>labels</code></td>
        <td>List of labels that this project is related to. You can find all available label IDs in the projects.yaml file.</td>
    </tr>
    <tr>
        <td><code>license</code></td>
        <td>License of the project. If set, license information from GitHub or package managers will be overwritten. Can be a custom URL pointing to more information in case it is not a standard license. `allowed_licenses` must be set to "all" or contain the URL in order to show the project.</td>
    </tr>
    <tr>
        <td><code>description</code></td>
        <td>Short description of the project. If set, the description from GitHub or package managers will be overwritten.</td>
    </tr>
    <tr>
        <td><code>homepage</code></td>
        <td>Homepage URL of the project. Only use this property if the project homepage is different from the GitHub URL.</td>
    </tr>
    <tr>
        <td><code>docs_url</code></td>
        <td>Documentation URL of the project. Only use this property if the project documentation site is different from the GitHub URL.</td>
    </tr>
    <tr>
        <td><code>resource</code></td>
        <td>If <code>True</code>, the project will be marked as a resource. Resources are not ranked and will always be shown on top of the category. You can use this to link to another best-of list section or website that contains additional projects.</td>
    </tr>
    <tr>
        <td><code>group</code></td>
        <td>If <code>True</code>, the project will be used as top project for grouping a set of related projects. <code>group_id</code> also needs to be set to the shared group ID.</td>
    </tr>
    <tr>
        <td><code>group_id</code></td>
        <td>Group ID that can be used to group this project to other projects. For every group, there needs to be one project with <code>group</code> set to <code>True</code>.</td>
    </tr>
    <tr>
        <td><code>show</code></td>
        <td>If <code>True</code>, the project will always be shown even when the project would be actual hidden (e.g. dead project, risky licenses, to few stars...). Only use this property if you are sure that this project needs to be shown.</td>
    </tr>
    <tr>
        <td><code>ignore</code></td>
        <td>If <code>True</code>, the project will be ignored. This also means that it will not be included in the hidden projects section. However, the project metadata will still be collected.</td>
    </tr>
    <tr>
        <td colspan="2"><b>Supported Integrations:</b></td>
    </tr>
    <tr>
        <td><code>pypi_id</code></td>
        <td>Project ID on the Python package index (<a href="https://pypi.org">PyPi</a>).</td>
    </tr>
    <tr>
        <td><code>conda_id</code></td>
        <td>Project ID on the <a href="https://anaconda.org">conda package manager</a>. If the main package is provided on a different channel, prefix the ID with the given channel: e.g. <code>conda-forge/tensorflow</code></td>
    </tr>
    <tr>
        <td><code>npm_id</code></td>
        <td>Project ID on the Node package manager (<a href="https://www.npmjs.com">npm</a>).</td>
    </tr>
    <tr>
        <td><code>dockerhub_id</code></td>
        <td>Project ID on the <a href="https://hub.docker.com">Docker Hub container registry</a>. </td>
    </tr>
    <tr>
        <td><code>maven_id</code></td>
        <td>Artifact ID on <a href="https://mvnrepository.com">Maven central</a>, e.g. <code>org.apache.flink:flink-core</code>. </td>
    </tr>
    <tr>
        <td><code>github_id</code></td>
        <td>GitHub ID of the project based on user or organization  and the repository name, e.g. <code>best-of-lists/best-of-generator</code>.</td>
    </tr>
    <tr>
        <td><code>gitlab_id</code></td>
        <td>GitLab ID of the project based on user or organization  and the repository name, e.g. <code>best-of-lists/best-of-generator</code>.</td>
    </tr>
    <tr>
        <td><code>greasy_fork_id</code></td>
        <td>Greasy Fork ID of the project. This is the number in script's URL, e.g. <code>299792458</code> for <code>https://greasyfork.org/scripts/299792458-speed-of-light</code>. If set, homepage and description on Greasy Fork will take precedence over those on GitHub.</td>
    </tr>
</table>

While you can theoretically overwrite all project metadata, we suggest to only set the properties which the best-of generator is not able to find on GitHub or the configured package managers. There are also other undocumented properties, but for most projects those properties should not be overwritten.

<details>
<summary><b>Additional undocumented project metadata </b> (click to expand...)</summary>

- created_at
- update_at
- github_url
- github_release_downloads
- github_dependent_project_count
- last_commit_pushed_at
- star_count
- commit_count
- dependent_project_count
- contributor_count
- fork_count
- monthly_downloads
- open_issue_count
- closed_issue_count
- release_count
- latest_stable_release_published_at
- latest_stable_release_number
- trending
- helm_id
- brew_id
- apt_id
- yum_id
- snap_id
- maven_id
- dnf_id
- yay_id
- <PACKAGE_MANAGER>_url
- <PACKAGE_MANAGER>_latest_release_published_at
- <PACKAGE_MANAGER>_dependent_project_count

</details>

### Categories

A category allows to add additional structure to the best-of list by grouping related projects into a shared category. Thereby, every project is grouped into exactly one category. If no category is provided with the project metadata, the project will be categorized into `Others`.

#### Category Example

```yaml
categories:
  - category: "data-engineering"
    title: "Machine Learning & Data Engineering"
    subtitle: "Best-of lists about machine learning, data engineering, data science, or other topics related to big data."

projects:
  - name: "best-of-ml-python"
    github_id: "ml-tooling/best-of-ml-python"
    category: "data-engineering"
```

The example above will be rendered as shown below:

![Category Example](./docs/images/best-of-category-example-framed.png)

#### Category Properties

<table>
    <tr>
        <th>Property</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>category</code></td>
        <td>ID of the category. This ID should also be used for adding a project to this category.</td>
    </tr>
    <tr>
        <td><code>title</code></td>
        <td>Category name used as the header of the category section.</td>
    </tr>
    <tr>
        <td colspan="2"><b>Optional Properties:</b></td>
    </tr>
    <tr>
        <td><code>subtitle</code></td>
        <td>Short description about the category shown under the title.</td>
    </tr>
    <tr>
        <td><code>ignore</code></td>
        <td>If <code>True</code>, the category and all its projects will be ignored.</td>
    </tr>
</table>

### Labels

A label allows to highlight similarities or special features shared between projects. Compared to categories, a project can have any number of labels. The labels are shown as badges attached to the project description. It can have only an image (favicons are recommended), only a name, or both. We recommend to use image labels (or only very short labels) since the usage of labels will shorten the visible description text of a project.

#### Label Example

```yaml
labels:
  - label: "python"
    image: "https://www.python.org/static/favicon.ico"
    description: "Best-of list with Python projects"
  - label: "libraries"
    name: "libraries"

projects:
  - name: "best-of-ml-python"
    github_id: "ml-tooling/best-of-ml-python"
    labels: ["libraries", "python"]
    category: "data-engineering"
```

The example above will be rendered as shown below:

![Label Example](./docs/images/best-of-label-example-framed.png)

#### Label Properties

<table>
    <tr>
        <th>Property</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><code>label</code></td>
        <td>ID of the label. This ID should also be used for adding the label to a project.</td>
    </tr>
    <tr>
        <td colspan="2"><b>Optional Properties:</b></td>
    </tr>
    <tr>
        <td><code>image</code></td>
        <td>URL to an image. If a valid URL is provided, the image will be shown wherever the label is used.</td>
    </tr>
    <tr>
        <td><code>name</code></td>
        <td>Name of the label. If a name is provided, the name will be shown wherever the label is used.</td>
    </tr>
    <tr>
        <td><code>description</code></td>
        <td>Short description of the label. If <code>show_labels_in_legend</code> configuration is <code>True</code> and an <code>image</code> is set, this description will also be shown in the legend (explanations).</td>
    </tr>
    <tr>
        <td><code>ignore</code></td>
        <td>If <code>True</code>, the l