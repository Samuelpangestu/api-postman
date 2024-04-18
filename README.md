# Flip Take Home Test Collection

This repository contains a Postman collection designed to answer the take home test Flip. Additionally, it includes GitHub Actions workflows to automate running these tests.

## About the Postman Collection

Below is an explanation of the API test for each scenario
1. Get todos, make sure it shows only 10 items
To get endpoint 'todos' and shows only 10 item, i just adding query param (based on the doc) '?per_page=10'

2. Get users with status inactive, make sure it shows correct data
To get users with inactive status, i just adding query param as well 'page=1&status=inactive' and to make sure it shows correct data, i add a validation in test script to make sure that all of the response have a 'inactive' status.

I also add 'newman test' to github action workflow and also html report if we want to run this test in repo


## How to Run the Tests

### Option 1: Run from Postman
1. Download the `.json` file containing the Postman collection.
2. Import the collection into your Postman.
3. Run the collection.

### Option 2: Run from GitHub
1. Open GitHub Actions in the repository.
2. Choose the appropriate workflow.
3. Click on "Re-run all jobs" to execute the tests.


## GitHub Actions Workflow: Newman Tests

This workflow is set up to run on every `push` or `pull_request` event. It performs the following actions:

1. **Setup:** Checks out the repository and installs Node.
2. **Install Newman:** Installs Newman and the Newman HTML Extra reporter.
3. **Create Results Directory:** Creates a directory to store the test results.
4. **Run Tests:** Executes the Postman collection using Newman and exports the results to an HTML report.
5. **Upload Results:** Uploads the test results to the repository as an artifact.

