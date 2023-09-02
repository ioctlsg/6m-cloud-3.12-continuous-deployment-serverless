# serverless with Github-action

The main.yml in .github/workflow/ runs 4 pipeline with the 4th to deploy in the AWS lamada. 

![alt text](https://github.com/ioctlsg/6m-cloud-3.12-continuous-deployment-serverless/blob/main/Screenshot%202023-09-02%20at%205.25.11%20PM.png)

This YAML code defines a GitHub Actions workflow named "CICD for serverless" that automates the Continuous Integration and Continuous Deployment (CICD) process for a serverless application. Here's a breakdown of its main components:

1. **Workflow Name and Run Name**: The workflow is named "CICD for serverless," and it dynamically sets the run name to include the name of the GitHub actor (user or bot) triggering the workflow.

2. **Trigger**: The workflow is triggered on "push" events to the "main" branch and any other branch ("*").

3. **Jobs**: There are four jobs defined within the workflow:

   a. **pre-deploy**: This job runs on an Ubuntu environment and echoes a message indicating that it's triggered by a specific GitHub actor.

   b. **install-dependencies**: This job checks out the repository code, installs Node.js dependencies using npm, and depends on the "pre-deploy" job.

   c. **unit-testing**: This job checks out the repository code, installs Node.js dependencies, and runs unit tests using npm. It depends on the "install-dependencies" job.

   d. **deploy**: This job is responsible for deploying the serverless application. It checks out the repository, sets up Node.js, installs dependencies, and deploys the serverless application using the Serverless Framework. It depends on the "unit-testing" job.

Each job specifies the operating system it runs on, the dependencies it needs, and a series of steps to execute, including checking out code, setting up Node.js (if needed), installing dependencies, and running specific commands.

index.js - code for the lamada. 
index.test.js - code for unit-testing for the index.js




