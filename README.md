# Jira Issues Creator

Jira Issues Creator automates the creation of epics, stories, tasks, and sub-tasks in Jira using structured YAML configuration files. It eliminates manual data entry and ensures consistency through predefined configurations.

For more information and feature requests, visit [SOSQE-1730](https://issues.redhat.com/browse/SOSQE-1730).

## Motivation

Managing complex Jira projects often involves creating nested issues like epics, stories, tasks, and sub-tasks. Manual setup can be time-consuming and error-prone. Jira Issues Creator addresses these challenges by automating the process, ensuring efficiency and accuracy through:

- **Templating and Routines**: Streamline recurring tasks with stored templates, reducing manual effort.
- **Procedures and Documentation**: Facilitate Jira issue creation for procedures and documentation using predefined files, which is useful during meetings or planning sessions.
- **Automation**: Simplify issue creation and configure fields like story points, sprints, and links after initial issue creation.

## Features

- **Secure Authentication**: Authenticates with Jira using API tokens.
- **Custom Field Mapping**: Maps Jira’s custom fields to your project needs.
- **YAML-Based Automation**: Automates complex issue structures with YAML files.
- **Post-Creation Configuration**: Sets additional fields after issue creation.
- **Version Control**: Store configuration files in source control for version tracking and integrity.

## Requirements

- Python 3
- Dependencies: `jinja2`, `requests`, `pyyaml` (listed in `requirements.txt`)

## Setup

1. **Clone the Repository and Navigate to It**:

2. **Install and Set Up the Tool**:
   ```sh
   $ make install
   ```
   This command:
   - Sets up a Python virtual environment.
   - Installs required dependencies.
   - Creates a wrapper script `~/.local/bin/` for global tool access.
   - Ensures `~/.local/bin/` is in your PATH.

3. **Configure Jira Settings**:
   - Edit [`jira_config.yaml`](jira_config.yaml):
     - Set `jira_url` to your Jira instance URL.
     - Update `jira_token` with your Jira API token.
     - Customize `jira_special_fields` for your project.

4. **Define Jira Issues**:
   - Edit [`jira_issues.yaml`](jira_issues.yaml):
     - Replace `<YOUR_JIRA_PROJECT_KEY>` with your Jira project key.
     - Define epics, stories, tasks, and sub-tasks as needed.

## Usage

After installation, use the tool from anywhere with:
   ```sh
   $ jira-issues-creator [--help] --issues_list_file ISSUES_LIST_FILE [--jira_config_file JIRA_CONFIG_FILE] [--debug]
   ```

## Explanation of Files

- **jira_issues_creator.py**: Main script for interacting with Jira.
- **jira_handler.py**: Module for Jira API interactions.
- **jira_config.yaml**: Jira instance settings and custom field mappings.
- **jira_issues.yaml**: Structure of epics, stories, tasks, and sub-tasks to be created.

## Example

For detailed examples on configuring [`jira_config.yaml`](jira_config.yaml) and [`jira_issues.yaml`](jira_issues.yaml), refer to the [Example File](example.md).

## Contribution

Contributions are welcome! Please submit pull requests with improvements or additional features.