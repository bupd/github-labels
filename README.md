# github-labels

This project provides a standardized set of labels necessary for organizing issues, pull requests, and workflows on your GitHub repositories. By using the provided JSON file, you can quickly install or remove these labels across multiple projects.

## Features

- Pre-defined labels for various workflows such as triaging, issue management, and release tracking.
- Simple installation of labels using `git-label-cli`.
- Fast and easy removal or updating of labels in any GitHub repository.
- Configurable via JSON files for custom label setups.

## Prerequisites

You need to have `git-label-cli` installed to add or remove labels from a repository.

## Installation of `git-label-cli`

Install `git-label-cli` globally via npm by running:

```bash
sudo npm install -g git-label-cli
```

Once installed, you can use the CLI to manage labels on your GitHub repositories.

## How to Use

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/bupd/github-labels.git
cd github-labels
```

### 2. Add Labels to Your GitHub Repository

To add labels to your repository using the `git-label-cli`, follow these steps:

1. Navigate to your terminal and run the following command:
   ```bash
   git-label --repo=<your-username/repo> add --token=<your-token> --pattern ./labels.json --api https://api.github.com
   ```
   For Interactive Use
   ```bash
   git-label --repo=<your-username/repo> add --token=<your-token> --pattern ./labels.json --api https://api.github.com --interactive
   ```

2. Example of running the command:
   ```bash
   git-label --repo=bupd/github-labels add --token="ghp_OeMb4W6g2nF...." --pattern ./labels.json --api https://api.github.com --interactive
   ```

3. You will be prompted to provide additional information:
   - API URL: `https://api.github.com`
   - Repo name: `<username/repo>`
   - API Token: GitHub personal access token (PAT) with repo access.
   - Globbing pattern to the label packages: `labels.json`.

4. Upon completion, you should see a success message like:
   ```
   Successfully created 33 labels
   ```

### 3. Remove Labels from Your GitHub Repository

To remove the labels from a repository, use the following command:

   ```bash
   git-label --repo=<your-username/repo> remove --token=<your-token> --pattern ./labels.json --api https://api.github.com
   ```

Example:

```bash
git-label --repo=bupd/github-labels remove --token="ghp_OeMb4W6g2nF...." -p ./labels.json -a https://api.github.com
```

You should see a success message indicating that the labels were removed:
```
Successfully deleted 33 labels
```

## JSON Label Configuration

The labels used in this project are defined in the `labels.json` file. You can edit this file to customize the labels as per your project needs. Here’s a sample format:

```json
[
  { "name": "Status: In Progress", "color": "#cccccc" },
  { "name": "Type: Bug", "color": "#d73a4a" },
  { "name": "Priority: High", "color": "#e11d21" },
  // Add more labels here
]
```

### Customizing Labels

To customize or add new labels:
1. Edit the `labels.json` file to fit your project needs.
2. Run the `git-label` commands as shown above to apply these changes.

## Troubleshooting

If you encounter an error like:

```
TypeError: Reduce of empty array with no initial value
```

Ensure that the `labels.json` file is properly formatted and contains valid label entries. Also, double-check the globbing pattern provided to match the correct file.

## Resources

- [git-label-cli Documentation](https://github.com/jasonbellamy/git-label-cli)
- [GitHub Labels API](https://docs.github.com/en/rest/issues/labels)

## Contributing

Feel free to submit issues or pull requests for new features, label suggestions, or bug fixes.
