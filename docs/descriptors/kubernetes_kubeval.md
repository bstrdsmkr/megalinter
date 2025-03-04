---
title: kubeval configuration in MegaLinter
description: How to use kubeval (configure, ignore files, ignore errors, help & version documentations) to analyze KUBERNETES files
---
<!-- markdownlint-disable MD033 MD041 -->
<!-- @generated by .automation/build.py, please do not update manually -->
# kubeval
![deprecated](https://shields.io/badge/-deprecated-red) [![GitHub stars](https://img.shields.io/github/stars/instrumenta/kubeval?cacheSeconds=3600)](https://github.com/instrumenta/kubeval) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/instrumenta/kubeval?sort=semver)](https://github.com/instrumenta/kubeval/releases) [![GitHub last commit](https://img.shields.io/github/last-commit/instrumenta/kubeval)](https://github.com/instrumenta/kubeval/commits) [![GitHub commit activity](https://img.shields.io/github/commit-activity/y/instrumenta/kubeval)](https://github.com/instrumenta/kubeval/graphs/commit-activity/) [![GitHub contributors](https://img.shields.io/github/contributors/instrumenta/kubeval)](https://github.com/instrumenta/kubeval/graphs/contributors/)

> This linter has been deprecated.
>
> Kubeval project is no longer maintained, you should use KUBERNETES_KUBECONFORM.
>
> You should disable kubeval by adding it in DISABLE_LINTERS property.
>
> It will be maintained at least until the next major release.

## kubeval documentation

- Version in MegaLinter: **0.16.1**
- Visit [Official Web Site](https://www.kubeval.com/){target=_blank}

[![kubeval - GitHub](https://gh-card.dev/repos/instrumenta/kubeval.svg?fullname=)](https://github.com/instrumenta/kubeval){target=_blank}

## Configuration in MegaLinter

- Enable kubeval by adding `KUBERNETES_KUBEVAL` in [ENABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)
- Disable kubeval by adding `KUBERNETES_KUBEVAL` in [DISABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)

| Variable                                       | Description                                                                                                                                                                                  | Default value                |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| KUBERNETES_KUBEVAL_ARGUMENTS                   | User custom arguments to add in linter CLI call<br/>Ex: `-s --foo "bar"`                                                                                                                     |                              |
| KUBERNETES_KUBEVAL_FILTER_REGEX_INCLUDE        | Custom regex including filter<br/>Ex: `(src\|lib)`                                                                                                                                           | Include every file           |
| KUBERNETES_KUBEVAL_FILTER_REGEX_EXCLUDE        | Custom regex excluding filter<br/>Ex: `(test\|examples)`                                                                                                                                     | Exclude no file              |
| KUBERNETES_KUBEVAL_CLI_LINT_MODE               | Override default CLI lint mode<br/>- `file`: Calls the linter for each file<br/>- `project`: Call the linter from the root of the project                                                    | `file`                       |
| KUBERNETES_KUBEVAL_FILE_EXTENSIONS             | Allowed file extensions. `"*"` matches any extension, `""` matches empty extension. Empty list excludes all files<br/>Ex: `[".py", ""]`                                                      | `[".yml", ".yaml", ".json"]` |
| KUBERNETES_KUBEVAL_FILE_NAMES_REGEX            | File name regex filters. Regular expression list for filtering files by their base names using regex full match. Empty list includes all files<br/>Ex: `["Dockerfile(-.+)?", "Jenkinsfile"]` | Include every file           |
| KUBERNETES_KUBEVAL_PRE_COMMANDS                | List of bash commands to run before the linter                                                                                                                                               | None                         |
| KUBERNETES_KUBEVAL_POST_COMMANDS               | List of bash commands to run after the linter                                                                                                                                                | None                         |
| KUBERNETES_KUBEVAL_DISABLE_ERRORS              | Run linter but consider errors as warnings                                                                                                                                                   | `false`                      |
| KUBERNETES_KUBEVAL_DISABLE_ERRORS_IF_LESS_THAN | Maximum number of errors allowed                                                                                                                                                             | `0`                          |
| KUBERNETES_DIRECTORY                           | Directory containing KUBERNETES files                                                                                                                                                        | `kubernetes`                 |

## MegaLinter Flavours

This linter is available in the following flavours

|                                                                         <!-- -->                                                                         | Flavor                                                             | Description                                           | Embedded linters |                                                                                                                                                                                                   Info |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------|:------------------------------------------------------|:----------------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/mega-linter-square.png" alt="" height="32px" class="megalinter-icon"></a> | [all](https://megalinter.io/beta/supported-linters/)               | Default MegaLinter Flavor                             |       112        |                             ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/cupcake.ico" alt="" height="32px" class="megalinter-icon"></a>       | [cupcake](https://megalinter.io/beta/flavors/cupcake/)             | MegaLinter for the most commonly used languages       |        80        |             ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-cupcake/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-cupcake) |
|    <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/documentation.ico" alt="" height="32px" class="megalinter-icon"></a>    | [documentation](https://megalinter.io/beta/flavors/documentation/) | MegaLinter for documentation projects                 |        47        | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-documentation/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-documentation) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/dotnet.ico" alt="" height="32px" class="megalinter-icon"></a>        | [dotnet](https://megalinter.io/beta/flavors/dotnet/)               | Optimized for C, C++, C# or VB based projects         |        59        |               ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-dotnet/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-dotnet) |
|         <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/go.ico" alt="" height="32px" class="megalinter-icon"></a>          | [go](https://megalinter.io/beta/flavors/go/)                       | Optimized for GO based projects                       |        49        |                       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-go/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-go) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/java.ico" alt="" height="32px" class="megalinter-icon"></a>         | [java](https://megalinter.io/beta/flavors/java/)                   | Optimized for JAVA based projects                     |        50        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-java/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-java) |
|     <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/javascript.ico" alt="" height="32px" class="megalinter-icon"></a>      | [javascript](https://megalinter.io/beta/flavors/javascript/)       | Optimized for JAVASCRIPT or TYPESCRIPT based projects |        56        |       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-javascript/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-javascript) |
|         <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/php.ico" alt="" height="32px" class="megalinter-icon"></a>         | [php](https://megalinter.io/beta/flavors/php/)                     | Optimized for PHP based projects                      |        50        |                     ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-php/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-php) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/python.ico" alt="" height="32px" class="megalinter-icon"></a>        | [python](https://megalinter.io/beta/flavors/python/)               | Optimized for PYTHON based projects                   |        57        |               ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-python/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-python) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/ruby.ico" alt="" height="32px" class="megalinter-icon"></a>         | [ruby](https://megalinter.io/beta/flavors/ruby/)                   | Optimized for RUBY based projects                     |        47        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-ruby/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-ruby) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/rust.ico" alt="" height="32px" class="megalinter-icon"></a>         | [rust](https://megalinter.io/beta/flavors/rust/)                   | Optimized for RUST based projects                     |        47        |                   ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-rust/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-rust) |
|     <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/salesforce.ico" alt="" height="32px" class="megalinter-icon"></a>      | [salesforce](https://megalinter.io/beta/flavors/salesforce/)       | Optimized for Salesforce based projects               |        50        |       ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-salesforce/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-salesforce) |
|      <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/security.ico" alt="" height="32px" class="megalinter-icon"></a>       | [security](https://megalinter.io/beta/flavors/security/)           | Optimized for security                                |        21        |           ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-security/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-security) |
|        <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/swift.ico" alt="" height="32px" class="megalinter-icon"></a>        | [swift](https://megalinter.io/beta/flavors/swift/)                 | Optimized for SWIFT based projects                    |        47        |                 ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-swift/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-swift) |
|      <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/terraform.ico" alt="" height="32px" class="megalinter-icon"></a>      | [terraform](https://megalinter.io/beta/flavors/terraform/)         | Optimized for TERRAFORM based projects                |        52        |         ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-terraform/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-terraform) |

## Behind the scenes

### How are identified applicable files

- Activated only if sub-directory `kubernetes` is found. (directory name can be overridden with `KUBERNETES_DIRECTORY`)
- File extensions: `.yml`, `.yaml`, `.json`
- Detected file content (regex): `apiVersion:`, `kustomize\.config\.k8s\.io`, `tekton`

<!-- markdownlint-disable -->
<!-- /* cSpell:disable */ -->
### How the linting is performed

- kubeval is called one time by identified file (`file` CLI lint mode)

### Example calls

```shell
kubeval -strict myfile.yml
```


### Help content

```shell
Validate a Kubernetes YAML file against the relevant schema

Usage:
  kubeval <file> [file...] [flags]

Flags:
      --additional-schema-locations strings   Comma-seperated list of secondary base URLs used to download schemas
  -n, --default-namespace string              Namespace to assume in resources if no namespace is set in metadata:namespace (default "default")
  -d, --directories strings                   A comma-separated list of directories to recursively search for YAML documents
      --exit-on-error                         Immediately stop execution when the first error is encountered
  -f, --filename string                       filename to be displayed when testing manifests read from stdin (default "stdin")
      --force-color                           Force colored output even if stdout is not a TTY
  -h, --help                                  help for kubeval
      --ignore-missing-schemas                Skip validation for resource definitions without a schema
      --ignored-filename-patterns strings     An alias for ignored-path-patterns
  -i, --ignored-path-patterns strings         A comma-separated list of regular expressions specifying paths to ignore
      --insecure-skip-tls-verify              If true, the server's certificate will not be checked for validity. This will make your HTTPS connections insecure
  -v, --kubernetes-version string             Version of Kubernetes to validate against (default "master")
      --openshift                             Use OpenShift schemas instead of upstream Kubernetes
  -o, --output string                         The format of the output of this script. Options are: [stdout json tap]
      --quiet                                 Silences any output aside from the direct results
      --reject-kinds strings                  Comma-separated list of case-sensitive kinds to prohibit validating against schemas
  -s, --schema-location string                Base URL used to download schemas. Can also be specified with the environment variable KUBEVAL_SCHEMA_LOCATION.
      --skip-kinds strings                    Comma-separated list of case-sensitive kinds to skip when validating against schemas
      --strict                                Disallow additional properties not in schema
      --version                               version for kubeval
```

### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
RUN ML_THIRD_PARTY_DIR="/third-party/kubeval" \
    && mkdir -p ${ML_THIRD_PARTY_DIR} \
    && wget -P ${ML_THIRD_PARTY_DIR} -q https://github.com/instrumenta/kubeval/releases/latest/download/kubeval-linux-amd64.tar.gz \
    && tar xf ${ML_THIRD_PARTY_DIR}/kubeval-linux-amd64.tar.gz --directory ${ML_THIRD_PARTY_DIR} \
    && mv ${ML_THIRD_PARTY_DIR}/kubeval /usr/local/bin \
    && rm ${ML_THIRD_PARTY_DIR}/kubeval-linux-amd64.tar.gz \
    && find ${ML_THIRD_PARTY_DIR} -type f -not -name 'LICENSE*' -delete -o -type d -empty -delete

```

