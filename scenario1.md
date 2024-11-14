

### Mitchel - Overall Scenario 1 - Test Results - AAD group is assigned to a PIM group causes the tool to crash (nested groups)

- Repeat the tests below in each tenant. You are responsible for setting up your own test users and groups with unique names that are specific to your testing.
- Run the ScubaGear main branch code against the tenant for a specific scenario and verify that it crashes under the conditions described. Then run the fix branch associated with this PR. We are running the main branch and observing the crash to ensure that   the fix was successful.

| Branch | Tenant | Scenario | Expected Results | Actual Results |
|----------|----------|----------|----------|----------|
| main    | G5 | Scenario 1 - Nested group assignment in PIM for Groups (Active assigned to role) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| main    | G5 | Scenario 2 - Nested group assignment in PIM for Groups (Eligible assigned to role) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| main    | G5 | Scenario 3 - Nested group assignment in PIM for Groups (PIM group circular reference) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| fix    | G5 | Scenario 1 - Nested group assignment in PIM for Groups (Active assigned to role) | no crash | no crash, reports generated |
| fix    | G5 | Scenario 2 - Nested group assignment in PIM for Groups (Eligible assigned to role) | no crash | no crash, reports generated |
| fix    | G5 | Scenario 3 - Nested group assignment in PIM for Groups (PIM group circular reference) | no crash | no crash, reports generated |


### Mitchel - Overall Scenario 2 - Test Results - AAD user or group is deleted before running ScubaGear causes the tool to crash

- Repeat the tests below in each tenant. You are responsible for setting up your own test users and groups with unique names that are specific to your testing.
- Run the ScubaGear main branch code against the tenant for a specific scenario and verify that it crashes under the conditions described. Then run the fix branch associated with this PR. We are running the main branch and observing the crash to ensure that   the fix was successful.

| Branch | Tenant | Scenario | Expected Results | Actual Results |
|----------|----------|----------|----------|----------|
| main    | G5 | Scenario 1 - Deleted user (Active role assignment) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| main    | G5 | Scenario 2 - Deleted user (Eligible role assignment) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| main    | G5 | Scenario 3 - Deleted group (Active role assignment) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| main    | G5 | Scenario 4 - Deleted group (Eligible role assignment) | crash 404 error | 404 (NotFound), Errorcode: Request_ResourceNotFound |
| fix    | G5 | Scenario 1 - Deleted user (Active role assignment) | no crash | no crash, reports generated |
| fix    | G5 | Scenario 2 - Deleted user (Eligible role assignment) | no crash | no crash, reports generated |
| fix    | G5 | Scenario 3 - Deleted group (Active role assignment) | no crash | no crash, reports generated; tried with owner role and same result |
| fix    | G5 | Scenario 4 - Deleted group (Eligible role assignment) | no crash | no crash, reports generated |


