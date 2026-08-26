# How GitHub Repository Management Works

Clone, create, fork, and manage GitHub repositories, remotes, and releases.

![Detailed systems blueprint for GitHub Repository Management](../assets/system-blueprint.png)

## Stages

### 1. Confirm owner repository and requested operation

**Primary surface:** `Repository intent`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 2. Inspect local branches remotes and status

**Primary surface:** `Local Git state`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 3. Preview create fork or release changes

**Primary surface:** `GitHub repository API`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 4. Execute the authorized GitHub operation

**Primary surface:** `Remote and release objects`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 5. Fetch repository and remote state again

**Primary surface:** `Verified repository state`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.
### 6. Report URLs SHAs and visibility

**Primary surface:** `Verified repository state`

Record the input, operation, observable output, and any decision that changes scope. Stop here if the output is missing, contradictory, or insufficient for the next stage.

## Failure handling

- **Authorization failure:** do not probe credentials or broaden access; report the missing authority.
- **Target ambiguity:** stop before mutation and request the minimum identifying information.
- **Tool or service failure:** retain error evidence, retry only safe transient failures, and cap retries.
- **Verification failure:** classify the run as incomplete even when the preceding operation returned success.

## Completion evidence

The handoff should contain the original request, inspection state, preview or plan, exact execution result, direct verification, and a final receipt naming limitations and withheld actions.
