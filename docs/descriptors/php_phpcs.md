---
title: phpcs configuration in MegaLinter
description: How to use phpcs (configure, ignore files, ignore errors, help & version documentations) to analyze PHP files
---
<!-- markdownlint-disable MD033 MD041 -->
<!-- @generated by .automation/build.py, please do not update manually -->
# phpcs
[![GitHub stars](https://img.shields.io/github/stars/squizlabs/PHP_CodeSniffer?cacheSeconds=3600)](https://github.com/squizlabs/PHP_CodeSniffer) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/squizlabs/PHP_CodeSniffer?sort=semver)](https://github.com/squizlabs/PHP_CodeSniffer/releases) [![GitHub last commit](https://img.shields.io/github/last-commit/squizlabs/PHP_CodeSniffer)](https://github.com/squizlabs/PHP_CodeSniffer/commits) [![GitHub commit activity](https://img.shields.io/github/commit-activity/y/squizlabs/PHP_CodeSniffer)](https://github.com/squizlabs/PHP_CodeSniffer/graphs/commit-activity/) [![GitHub contributors](https://img.shields.io/github/contributors/squizlabs/PHP_CodeSniffer)](https://github.com/squizlabs/PHP_CodeSniffer/graphs/contributors/)

## phpcs documentation

- Version in MegaLinter: **3.7.1**
- Visit [Official Web Site](https://github.com/squizlabs/PHP_CodeSniffer#readme){target=_blank}
- See [How to configure phpcs rules](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#using-a-default-configuration-file){target=_blank}
  - If custom `phpcs.xml` config file is not found, [phpcs.xml](https://github.com/oxsecurity/megalinter/tree/main/TEMPLATES/phpcs.xml){target=_blank} will be used
- See [How to disable phpcs rules in files](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#ignoring-parts-of-a-file){target=_blank}

[![PHP_CodeSniffer - GitHub](https://gh-card.dev/repos/squizlabs/PHP_CodeSniffer.svg?fullname=)](https://github.com/squizlabs/PHP_CodeSniffer){target=_blank}

## Configuration in MegaLinter

- Enable phpcs by adding `PHP_PHPCS` in [ENABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)
- Disable phpcs by adding `PHP_PHPCS` in [DISABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)

| Variable                              | Description                                                                                                                                                                                                         | Default value                                   |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| PHP_PHPCS_ARGUMENTS                   | User custom arguments to add in linter CLI call<br/>Ex: `-s --foo "bar"`                                                                                                                                            |                                                 |
| PHP_PHPCS_FILTER_REGEX_INCLUDE        | Custom regex including filter<br/>Ex: `(src\|lib)`                                                                                                                                                                  | Include every file                              |
| PHP_PHPCS_FILTER_REGEX_EXCLUDE        | Custom regex excluding filter<br/>Ex: `(test\|examples)`                                                                                                                                                            | Exclude no file                                 |
| PHP_PHPCS_CLI_LINT_MODE               | Override default CLI lint mode<br/>- `file`: Calls the linter for each file<br/>- `list_of_files`: Call the linter with the list of files as argument<br/>- `project`: Call the linter from the root of the project | `list_of_files`                                 |
| PHP_PHPCS_FILE_EXTENSIONS             | Allowed file extensions. `"*"` matches any extension, `""` matches empty extension. Empty list excludes all files<br/>Ex: `[".py", ""]`                                                                             | `[".php"]`                                      |
| PHP_PHPCS_FILE_NAMES_REGEX            | File name regex filters. Regular expression list for filtering files by their base names using regex full match. Empty list includes all files<br/>Ex: `["Dockerfile(-.+)?", "Jenkinsfile"]`                        | Include every file                              |
| PHP_PHPCS_PRE_COMMANDS                | List of bash commands to run before the linter                                                                                                                                                                      | None                                            |
| PHP_PHPCS_POST_COMMANDS               | List of bash commands to run after the linter                                                                                                                                                                       | None                                            |
| PHP_PHPCS_CONFIG_FILE                 | phpcs configuration file name</br>Use `LINTER_DEFAULT` to let the linter find it                                                                                                                                    | `phpcs.xml`                                     |
| PHP_PHPCS_RULES_PATH                  | Path where to find linter configuration file                                                                                                                                                                        | Workspace folder, then MegaLinter default rules |
| PHP_PHPCS_DISABLE_ERRORS              | Run linter but consider errors as warnings                                                                                                                                                                          | `false`                                         |
| PHP_PHPCS_DISABLE_ERRORS_IF_LESS_THAN | Maximum number of errors allowed                                                                                                                                                                                    | `0`                                             |

## IDE Integration

Use phpcs in your favorite IDE to catch errors before MegaLinter !

|                                                                   <!-- -->                                                                   | IDE                                                      | Extension Name                                                                      |                                                                              Install                                                                               |
|:--------------------------------------------------------------------------------------------------------------------------------------------:|----------------------------------------------------------|-------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|  <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/atom.ico" alt="" height="32px" class="megalinter-icon"></a>   | [Atom](https://atom.io/)                                 | [linter-phpcs](https://atom.io/packages/linter-phpcs)                               |                                               [Visit Web Site](https://atom.io/packages/linter-phpcs){target=_blank}                                               |
|  <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/atom.ico" alt="" height="32px" class="megalinter-icon"></a>   | [Atom](https://atom.io/)                                 | [atom-phpcs](https://github.com/bpearson/atom-phpcs)                                |                                              [Visit Web Site](https://github.com/bpearson/atom-phpcs){target=_blank}                                               |
|  <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/idea.ico" alt="" height="32px" class="megalinter-icon"></a>   | [IDEA](https://www.jetbrains.com/products.html#type=ide) | [phpcs](https://www.jetbrains.com/help/phpstorm/2019.1/using-php-code-sniffer.html) |                            [Visit Web Site](https://www.jetbrains.com/help/phpstorm/2019.1/using-php-code-sniffer.html){target=_blank}                             |
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/sublime.ico" alt="" height="32px" class="megalinter-icon"></a> | [Sublime Text](https://www.sublimetext.com/)             | [sublime-phpcs](https://github.com/benmatselby/sublime-phpcs)                       |                                           [Visit Web Site](https://github.com/benmatselby/sublime-phpcs){target=_blank}                                            |
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/sublime.ico" alt="" height="32px" class="megalinter-icon"></a> | [Sublime Text](https://www.sublimetext.com/)             | [SublimeLinter-phpcs](https://github.com/SublimeLinter/SublimeLinter-phpcs)         |                                       [Visit Web Site](https://github.com/SublimeLinter/SublimeLinter-phpcs){target=_blank}                                        |
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/vscode.ico" alt="" height="32px" class="megalinter-icon"></a>  | [Visual Studio Code](https://code.visualstudio.com/)     | [vscode-phpcs](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs)   | [![Install in VSCode](https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/btn_install_vscode.png)](vscode:extension/ikappas.phpcs){target=_blank} |

## MegaLinter Flavours

This linter is available in the following flavours

|                                                                         <!-- -->                                                                         | Flavor                                                 | Description                                     | Embedded linters |                                                                                                                                                                                       Info |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------|:------------------------------------------------|:----------------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/mega-linter-square.png" alt="" height="32px" class="megalinter-icon"></a> | [all](https://megalinter.io/beta/supported-linters/)   | Default MegaLinter Flavor                       |       112        |                 ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter) |
|       <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/cupcake.ico" alt="" height="32px" class="megalinter-icon"></a>       | [cupcake](https://megalinter.io/beta/flavors/cupcake/) | MegaLinter for the most commonly used languages |        80        | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-cupcake/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-cupcake) |
|         <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/php.ico" alt="" height="32px" class="megalinter-icon"></a>         | [php](https://megalinter.io/beta/flavors/php/)         | Optimized for PHP based projects                |        50        |         ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter-php/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter-php) |

## Behind the scenes

### How are identified applicable files

- File extensions: `.php`

<!-- markdownlint-disable -->
<!-- /* cSpell:disable */ -->
### How the linting is performed

- phpcs is called once with the list of files as arguments (`list_of_files` CLI lint mode)

### Example calls

```shell
phpcs myfile.php
```

```shell
phpcs --standard=phpcs.xml myfile.php
```

```shell
phpcs --standard=phpcs.xml mydir/ myfile.php
```


### Help content

```shell

Usage: phpcs [-nwlsaepqvi] [-d key[=value]] [--colors] [--no-colors]
  [--cache[=<cacheFile>]] [--no-cache] [--tab-width=<tabWidth>]
  [--report=<report>] [--report-file=<reportFile>] [--report-<report>=<reportFile>]
  [--report-width=<reportWidth>] [--basepath=<basepath>] [--bootstrap=<bootstrap>]
  [--severity=<severity>] [--error-severity=<severity>] [--warning-severity=<severity>]
  [--runtime-set key value] [--config-set key value] [--config-delete key] [--config-show]
  [--standard=<standard>] [--sniffs=<sniffs>] [--exclude=<sniffs>]
  [--encoding=<encoding>] [--parallel=<processes>] [--generator=<generator>]
  [--extensions=<extensions>] [--ignore=<patterns>] [--ignore-annotations]
  [--stdin-path=<stdinPath>] [--file-list=<fileList>] [--filter=<filter>] <file> - ...

 -     Check STDIN instead of local files and directories
 -n    Do not print warnings (shortcut for --warning-severity=0)
 -w    Print both warnings and errors (this is the default)
 -l    Local directory only, no recursion
 -s    Show sniff codes in all reports
 -a    Run interactively
 -e    Explain a standard by showing the sniffs it includes
 -p    Show progress of the run
 -q    Quiet mode; disables progress and verbose output
 -m    Stop error messages from being recorded
       (saves a lot of memory, but stops many reports from being used)
 -v    Print processed files
 -vv   Print ruleset and token output
 -vvv  Print sniff processing information
 -i    Show a list of installed coding standards
 -d    Set the [key] php.ini value to [value] or [true] if value is omitted

 --help                Print this help message
 --version             Print version information
 --colors              Use colors in output
 --no-colors           Do not use colors in output (this is the default)
 --cache               Cache results between runs
 --no-cache            Do not cache results between runs (this is the default)
 --ignore-annotations  Ignore all phpcs: annotations in code comments

 <cacheFile>    Use a specific file for caching (uses a temporary file by default)
 <basepath>     A path to strip from the front of file paths inside reports
 <bootstrap>    A comma separated list of files to run before processing begins
 <encoding>     The encoding of the files being checked (default is utf-8)
 <extensions>   A comma separated list of file extensions to check
                The type of the file can be specified using: ext/type
                e.g., module/php,es/js
 <file>         One or more files and/or directories to check
 <fileList>     A file containing a list of files and/or directories to check (one per line)
 <filter>       Use either the "gitmodified" or "gitstaged" filter,
                or specify the path to a custom filter class
 <generator>    Use either the "HTML", "Markdown" or "Text" generator
                (forces documentation generation instead of checking)
 <patterns>     A comma separated list of patterns to ignore files and directories
 <processes>    How many files should be checked simultaneously (default is 1)
 <report>       Print either the "full", "xml", "checkstyle", "csv"
                "json", "junit", "emacs", "source", "summary", "diff"
                "svnblame", "gitblame", "hgblame" or "notifysend" report,
                or specify the path to a custom report class
                (the "full" report is printed by default)
 <reportFile>   Write the report to the specified file path
 <reportWidth>  How many columns wide screen reports should be printed
                or set to "auto" to use current screen width, where supported
 <severity>     The minimum severity required to display an error or warning
 <sniffs>       A comma separated list of sniff codes to include or exclude from checking
                (all sniffs must be part of the specified standard)
 <standard>     The name or path of the coding standard to use
 <stdinPath>    If processing STDIN, the file path that STDIN will be processed as
 <tabWidth>     The number of spaces each tab represents

```

### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
# Parent descriptor install
RUN wget --tries=5 -q -O phive.phar https://phar.io/releases/phive.phar \
    && wget --tries=5 -q -O phive.phar.asc https://phar.io/releases/phive.phar.asc \
    && PHAR_KEY_ID="0x9D8A98B29B2D5D79" \
    && ( gpg --keyserver keyserver.pgp.com --recv-keys "$PHAR_KEY_ID" \
        || gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$PHAR_KEY_ID" \
        || gpg --keyserver pgp.mit.edu --recv-keys "$PHAR_KEY_ID" \
        || gpg --keyserver hkps://keyserver.ubuntu.com --recv-keys "$PHAR_KEY_ID" ) \
    && gpg --verify phive.phar.asc phive.phar \
    && chmod +x phive.phar \
    && mv phive.phar /usr/local/bin/phive \
    && rm phive.phar.asc \
    && update-alternatives --install /usr/bin/php php /usr/bin/php81 110

ENV PATH="/root/.composer/vendor/bin:$PATH"
# Linter install
RUN phive --no-progress install phpcs -g --trust-gpg-keys 31C7E470E2138192

```

