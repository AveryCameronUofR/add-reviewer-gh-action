# add-reviewer-gh-action
 GitHub Action to add reviewer(s) to a pull request. 
 
GitHub will add CODEOWNERS as reviewers at the start of a pull request, before any steps of the workflow have run or passed. This action allows reviewers to be specified so that they will be added when this step of the workflow runs, such as at the end of a workflow, instead of at the start to avoid early notifications while work is not ready.

## Usage
```
- name: Add Pull Request Reviewer
      uses: AveryCameronUofR/add-reviewer-gh-action@1.0.3
      with: 
        reviewers: "AveryCameronUofR"
        token: ${{ secrets.GITHUB_TOKEN }}
 ```
 
### Action Inputs

| Name | Description | Default |
| --- | --- | --- |
| `token` | `GITHUB_TOKEN` or a `repo` scoped [PAT](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line). | `GITHUB_TOKEN` |
| `reviewers` | The email or user name of the reviewer(s) to add. If more than one use a comma separated list. | none |

### Action Outputs
None

### Action Result
Fails workflow when invalid reviewer added, this may be the result of an incorrect name or email.
  
### Modification
To use and modify the action for yourself:
Make sure that node is installed on your computer. Then run ``` npm install ``` to update node_modules.

Make configuration modifications to the ``` actions.yml ``` file as needed.

Updated the dist/index.js file using [zeit/ncc](https://www.npmjs.com/package/@zeit/ncc)

Install ncc with: ``` npm i -g @zeit/ncc ```

Run ncc with: ``` ncc build index.js ```

Create a new release tag and publish.
