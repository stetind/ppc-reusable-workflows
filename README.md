## Reusable workflows

### Description
Reusable workflows with pre-defined GitHub actions.

### Usage
Add it directly in a job of your workflow with this syntax:

* TypeScript CI syntax
```yaml
  job_name:
    uses: stetind/ppc-reusable-workflows/.github/workflows/typescript-validation.yaml@main
    secrets: inherit
```
Requires `NPM_TOKEN` and `SONAR_TOKEN` to be defined as secrets at
the repository that calls the reusable workflow.

* Sonar syntax
```yaml
  job_name:
    uses: stetind/ppc-reusable-workflows/.github/workflows/sonar-analysis.yaml@main
    secrets: inherit
```
* Sonar Secret Variable Requirements:
  * SONAR_TOKEN => the sonar project token

* Sonar extra configuration
In order to be able to run the analisys, the repository must has, the `sonar-project.properties` file on root

example

```
sonar.organization=elearningindustry
sonar.projectKey={project key from sonar}
sonar.projectName={title}
sonar.projectVersion=1.0.0
sonar.sources=/*src*/
sonar.tests=/*test*/
# sonar.javascript.lcov.reportPaths=coverage/lcov.info
```

### Avoid executions
* [see the article](https://docs.github.com/en/actions/managing-workflow-runs/skipping-workflow-runs) 
