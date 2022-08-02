# HCL OneTest Server

This enables you to run test assets that are available in a project of a HCL OneTest™ Server from a Github action.

## Prerequisites to run this action

1. Create a github repository
2. Create a folder named ".github/workflows" in the root of the repository
3. Create a .yml file with any name inside the ".github/workflows" folder 
4. Then you need to code thta yml file as mentioned in the following example.

## Example usage

```yaml
name: HCL OneTest Server

on: workflow_dispatch

jobs:
    OTS-Action:
        runs-on: self-hosted
        name: HCL OneTest Server
        steps:
         - name: Execute Test
           uses: anuraag-k/ServerAction@main
           with:
            serverUrl: 
            offlineToken: 
            teamspace: 
            project: 
            branch: 
            assetId: 
            environment: 
            datasets:
            labels: 
            secretsCollection:
            variables:

```
5. Push it into the main branch
6. To configure agent:
    1. Go to settings (Repo).
    2. Select action -> runner.
    3. Click Create self-hosted runner, follow the download and configure instructions
7. Go to the Actions section in the repository and select the workflow.
8. Click the Run workflow dropdown and the list of input text boxes are displayed.
9. After entering the input values click on run workflow button

## List of Inputs

### `serverUrl`

URL of the HCL OneTest Server where the tests are located. URL should be of the format - https://hostname

### `offlineToken`

**Required** Input the offline user token for the corresponding HCL OneTest Server

### `teamspace`

**Required** Team Space name of the project.

### `project`

**Required** Project name of the test.

### `branch`

**Required** Project name of the test.

### `assetId`

**Required** AssetId of the test file in HCL OneTest Server.

### `environment`

**Optional**. Test environment corresponding to the test. Mandatory to input the value if you want to run API test.

### `datasets`

**Optional**. Semicolon (;) delimited list of source:replacement datasets for the job to run. For example, dataset1:dataset2;dataset3:dataset4

### `labels`
Optional. Labels to add to test results when the test run is complete. You can add multiple labels to a test result separated by a comma. For example, label1, label2.

### `secretsCollection`

Optional. Secrets collection name for the job to run.

### `variables`

Optional. Variables corresponding to the test. The format is name_of_the_variable=value_of_the_variable. You can add multiple variables to the test run separated by a semicolon.
