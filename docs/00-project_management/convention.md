# Conventions

This document describes rules and conventions used while on this project.


## Git commits

We use the conventional commits :
- https://www.conventionalcommits.org/en/v1.0.0/

Allowed types:
- feat
- doc
- fix
- refacto
- style

Allowed scopes :
- project-management
- research
- architecture
- meetings
- VR
- IoT
- IA
- other

> example :
> doc(project-management): Created convention.md

## Branches

`<TYPE>/<ISSUE NUMBER>-<FEATURE NAME>_<SUFFIX>`

> All in lower caps.

- TYPE : see Git commit Allowed types
- ISSUE NUMBER: number of the issue (Kanban)
- FEATURE NAME : Name of the kanban issue
- SUFFIX : optional :
    a suffix can be added if multiple branches are created for the same feature.

> example :
> doc/1-convention_geoffrey

## Repository handling

- Main protected
- To push on the main branch, a feature must be created and a merge request
(pull request) must be initiated.
- A pull request can be merged into the main if the following conditions are met:
    - No CI pipeline/job failed
    - There is at least 1 approval review

Approving a review should not be underestimated:
    - Different lines should be read by the reviewer.
    - Definition of done should be met.
