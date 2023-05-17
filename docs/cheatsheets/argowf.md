
## Workflow Resource:

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Workflow
metadata:
  name: my-workflow
spec:
  entrypoint: my-entrypoint
  templates:
    - name: my-entrypoint
      steps:
        - - name: step1
            template: step1-template
        - - name: step2
            template: step2-template
    - name: step1-template
      container:
        image: my-image
        command: [command1]
    - name: step2-template
      container:
        image: my-image
        command: [command2]
```
## Workflow Controller Commands:

#### Create or Submit a Workflow:

```yaml
argo submit <workflow-file.yaml>
```
#### List Workflows:
```yaml
argo list
```
#### Get Workflow Details:
```yaml
argo get <workflow-name>
```
#### Delete a Workflow:
```yaml
argo delete <workflow-name>
````
#### Resubmit a Workflow:
```yaml
argo resubmit <workflow-name>
```
#### Retry a Failed Step:
```yaml
argo retry <workflow-name>
```

## Workflow Template Variables:

### Inputs:

Define inputs in the workflow template's inputs section.
Access inputs within a template using {{inputs.parameters.<parameter-name>}}.

#### Outputs:

Define outputs in the workflow template's outputs section.
Access outputs within a template using {{outputs.parameters.<parameter-name>}}.
#### Workflow Control Structures:

### If Condition:

```yaml
steps:
  - - name: condition-check
      template: condition-template
      arguments:
        parameters:
          - name: my-condition
            value: "{{inputs.parameters.my-parameter}} == true"
  - - name: step1
      template: step1-template
      when: "{{steps.condition-check.outputs.result}}"
  - - name: step2
      template: step2-template
      when: "{{steps.condition-check.outputs.result}}"
```
### Loop:

```yaml
steps:
  - - name: loop
      template: loop-template
      arguments:
        parameters:
          - name: iterations
            value: "3"
  - - name: loop-step
      template: loop-step-template
      withParam: "{{steps.loop.outputs.parameters.iterations}}"
```

## Workflow Outputs:

###Passing Outputs to Next Step:
```yaml
steps:
  - - name: step1
      template: step1-template
      outputs:
        parameters:
          - name: my-output
            valueFrom: "{{steps.step1.outputs.parameters.my-output}}"
  - - name: step2
      template: step2-template
      inputs:
        parameters:
          - name: my-input
            value: "{{steps.step1.outputs.parameters.my-output}}"
```
## Advanced Features:

DAG Workflows: Argo Workflows supports defining complex Directed Acyclic Graph (DAG) workflows using the dag template.
Sub-Workflows: Argo allows defining reusable sub-workflows to encapsulate and reuse common logic.
Suspend and Resume: Workflows can be suspended using the suspend directive and resumed using the resume command.
Retry Policies: Specify retry policies for individual steps using the
