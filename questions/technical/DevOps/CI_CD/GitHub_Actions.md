# GitHub Actions Interview Questions and Answers

## 1. What is GitHub Actions?

**Answer:**  
GitHub Actions is a CI/CD (Continuous Integration/Continuous Delivery) platform provided by GitHub. It allows developers to automate software workflows directly from their repositories. With GitHub Actions, you can build, test, and deploy code automatically when a repository event (like a push or pull request) occurs. Workflows are defined using YAML files that dictate which actions to run, when to trigger them, and the overall automation pipeline.

---

## 2. What is a workflow in GitHub Actions?

**Answer:**  
A workflow in GitHub Actions is a configurable automation process defined in a YAML file. It consists of jobs, steps, and events. The workflow file is stored in the `.github/workflows/` directory of a repository. You can use workflows to automate a variety of tasks, such as running tests, building projects, or deploying applications. A workflow is triggered by specific events (like `push`, `pull_request`, etc.), and it can run on GitHub-hosted or self-hosted runners.

---

## 3. What are runners in GitHub Actions?

**Answer:**  
A runner is a server that executes the tasks defined in a GitHub Actions workflow. GitHub offers two types of runners:

- **GitHub-hosted runners:** These are managed by GitHub and run on virtual machines. They automatically scale, and GitHub takes care of maintaining the environment.
- **Self-hosted runners:** These are managed by the user and run on their own infrastructure. They offer more control over the environment and can be customized to suit specific needs.

---

## 4. What is an action in GitHub Actions?

**Answer:**  
An action is a reusable, modular unit of code that performs a specific task in a GitHub Actions workflow. Actions can be developed by the community or yourself, and they allow for code reusability within workflows. You can include an action in a step of your workflow, and it may be written in different languages such as JavaScript or Docker.

---

## 5. How are events used in GitHub Actions?

**Answer:**  
Events are triggers that start workflows in GitHub Actions. When certain activities occur in a repository, such as pushing code, opening a pull request, or creating a release, an event is fired, and the corresponding workflows are initiated. Examples of events include:

- `push`
- `pull_request`
- `release`
- `schedule` (for cron jobs)

---

## 6. Explain the structure of a GitHub Actions workflow YAML file.

**Answer:**  
A typical GitHub Actions workflow YAML file has the following structure:

```yaml
name: CI Workflow

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: "14"

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
```

- **name:** Describes the name of the workflow.
- **on:** Defines the events that will trigger the workflow (like `push`, `pull_request`, etc.).
- **jobs:** Contains one or more jobs, which run in parallel by default.
- **steps:** Each job contains multiple steps, where each step can run actions or commands.

---

## 7. What are job dependencies, and how can they be defined?

**Answer:**  
Job dependencies allow you to specify the execution order of jobs in a workflow. By default, all jobs run in parallel, but if you want a job to run only after the successful completion of another job, you can use the `needs` keyword.

Example:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Building project"

  test:
    runs-on: ubuntu-latest
    needs: build
    steps:
      - run: echo "Running tests"
```

---

## 8. What is the difference between `uses` and `run` in GitHub Actions?

**Answer:**

- **`uses`**: This keyword is used to run a pre-built action from the GitHub Marketplace or a custom action. For example, `actions/checkout@v2` is a commonly used action to check out the code from the repository.
- **`run`**: This keyword is used to execute a shell command directly in the workflow. For example, you might use `run: npm install` to install Node.js dependencies.

---

## 9. How do you pass environment variables to a GitHub Actions workflow?

**Answer:**  
You can pass environment variables to jobs or steps using the `env` keyword. These variables can be accessed in your commands or actions.

Example:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    env:
      NODE_ENV: production
    steps:
      - run: echo "Running in $NODE_ENV mode"
```

---

## 10. How can secrets be securely used in GitHub Actions?

**Answer:**  
GitHub Actions allows you to store sensitive information (like API keys or tokens) as **secrets** in your repository settings. You can access these secrets in your workflow using the `secrets` context.

Example:

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to production
        run: deploy.sh
        env:
          API_KEY: ${{ secrets.API_KEY }}
```

---

## 11. How can you debug a failed GitHub Actions workflow?

**Answer:**  
To debug a failed GitHub Actions workflow:

1. **Check the logs**: Each step in a workflow has its own log, which you can inspect in the GitHub Actions interface.
2. **Add debug output**: You can print additional information using `run: echo` or `run: printenv` to output environment variables and other diagnostic data.
3. **Enable step debugging**: You can enable GitHub Actions step debugging by setting the following secrets:
   - `ACTIONS_RUNNER_DEBUG`: Set to `true` for more verbose runner logs.
   - `ACTIONS_STEP_DEBUG`: Set to `true` for step-level debugging.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Debug information: $RUNNER_DEBUG"
```

---

## 12. Can you explain matrix builds in GitHub Actions?

**Answer:**  
Matrix builds in GitHub Actions allow you to run the same job multiple times with different configurations, such as different versions of a programming language or operating systems. You can define a matrix strategy using the `matrix` keyword.

Example:

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [10, 12, 14]
    steps:
      - name: Use Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v2
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm install
      - run: npm test
```

---

## 13. How can you reuse workflows across multiple repositories?

**Answer:**  
You can reuse workflows across multiple repositories by using **reusable workflows**. To do this, define a workflow in one repository and reference it from other repositories using the `uses` keyword.

Example of calling a reusable workflow:

```yaml
jobs:
  call-workflow:
    uses: organization/repo/.github/workflows/workflow.yml@main
    with:
      param1: value1
    secrets:
      secret1: ${{ secrets.secret1 }}
```

---

## 14. What are artifacts in GitHub Actions?

**Answer:**  
Artifacts in GitHub Actions are files or data generated during the execution of a workflow that can be shared or persisted for future use. Artifacts can be uploaded during a job and downloaded by subsequent jobs or saved for later analysis.

Example:

```yaml
steps:
  - name: Upload test results
    uses: actions/upload-artifact@v2
    with:
      name: test-results
      path: test-results/
```

---

## 15. How do you schedule workflows in GitHub Actions?

**Answer:**  
You can schedule workflows in GitHub Actions using the `schedule` event and cron syntax. This allows you to run workflows at regular intervals without manual intervention.

Example:

```yaml
on:
  schedule:
    - cron: "0 0 * * *"
```
