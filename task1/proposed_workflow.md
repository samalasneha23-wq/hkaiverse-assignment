# Task 1: HostelClear — Proposed Workflow

## 1. Overview

HostelClear is a proposed workflow for improving the tracking of hostel vacating and no-dues clearance requests. The purpose is to make pending checks visible, reduce unnecessary follow-up, and clarify which department is responsible for each step.

The proposal is based on the workflow investigation documented in the evidence log. Details that have not been confirmed through an official procedure are treated as assumptions requiring further validation.

## 2. Problem Identified

The current process may require students to visit multiple departments to obtain no-dues confirmations. This can make it difficult to know which checks have been completed, which remain pending, and whom to contact when a step is delayed.

A centralized tracker could provide a single view of request progress without removing the authority of individual departments to verify dues or approve clearance.

## 3. Proposed Solution

HostelClear would maintain one clearance request for each student and track the required departmental checks through defined statuses.

The proposed process is:

1. **Submit request:** The student submits the required information and identifies the hostel vacating request.
2. **Validate information:** The designated coordinator checks whether required fields and documents are present.
3. **Create tracking record:** A unique request ID is generated, and the request status is set to Submitted.
4. **Department verification:** The relevant departments review their respective checks and record their outcomes.
5. **Resolve exceptions:** Missing information, discrepancies, or outstanding dues are assigned to the appropriate responsible person.
6. **Review completion:** The designated authority checks whether all required departmental verifications and approvals have been completed.
7. **Close request:** The request is marked Completed only after the required approvals are recorded.
8. **Notify the student:** The student receives a status update and any applicable next steps.

This is a proposed design. The exact department sequence and mandatory checks must be confirmed against the institution's current procedure before implementation.

## 4. Required Inputs

| Input | Purpose |
|---|---|
| Request ID | Uniquely identifies the clearance request |
| Student identifier | Links the request to the correct student through an authorised system |
| Request type | Identifies the hostel vacating or clearance request |
| Submission date | Records when the request was created |
| Required documents/checklist | Helps identify missing information |
| Department verification status | Tracks the outcome of each required check |
| Assigned owner | Identifies who must take the next action |
| Remarks or exception reason | Explains missing information, discrepancies, or pending actions |
| Approval record | Records the required authorised decision |
| Completion date | Records when all required steps are complete |

Personal student information should only be accessed by authorised personnel and should not be placed in a public demonstration.

## 5. Proposed Statuses

| Status | Meaning |
|---|---|
| Draft | Request has not yet been submitted |
| Submitted | Request has been submitted |
| Pending Validation | Required information is being checked |
| Action Required | Information or corrective action is needed |
| Pending Department Verification | One or more required checks remain incomplete |
| Pending Final Approval | Departmental checks are complete, but final approval is outstanding |
| Approved | The authorised approval has been recorded |
| Completed | All required steps are complete and the request is closed |
| On Hold | Processing cannot continue until a defined issue is resolved |
| Rejected | An authorised decision has rejected the request, with a reason recorded |

A request must not be marked Approved or Completed merely because all departments have been contacted. The required checks and approvals must be recorded.

## 6. Responsibilities and Accountability

| Role | Responsibility |
|---|---|
| Student | Submits correct information and responds to requests for missing information |
| Workflow coordinator | Checks completeness, creates the tracking record, and monitors pending steps |
| Department representative | Performs the department's own verification and records the outcome |
| Hostel representative | Completes the hostel-related checks assigned under the official procedure |
| Authorised approving officer | Makes the final decision where formal approval is required |
| System administrator or support person | Handles technical issues and access problems without making departmental approval decisions |

The specific job titles and approval authority must be confirmed with the institution. These roles describe the proposed design, not verified current staff assignments.

## 7. Approval Boundaries

- Each department remains responsible for verifying its own dues and records.
- The workflow coordinator can track progress but cannot approve another department's checks.
- Only an authorised person can provide a required final approval.
- A missing approval must remain visible as pending.
- The system must retain a record of status changes and the person responsible for each action.
- Any disagreement or disputed record must be referred to the appropriate authorised department.
- The tracker must not automatically waive dues or issue clearance based only on incomplete information.

## 8. Exception Handling

### Missing Information

Set the status to Action Required. Identify the missing item, notify the student, and resume processing after the information has been received and checked.

### Duplicate Request

Check whether an active request already exists. Link the duplicate submission to the existing request or mark it as a duplicate after authorised review. Do not create conflicting clearance decisions.

### Outstanding Dues or Discrepancy

Keep the relevant verification pending and assign the issue to the responsible department. Record the reason and the next action. Do not bypass the required check.

### Unavailable Department Representative

Keep the department verification pending, identify the responsible department, and follow the institution's approved escalation or alternate-contact procedure. Do not treat an unavailable representative as an approval.

### Unauthorised Request or Action

Restrict access or reject the unauthorised action according to the approved access rules. Record the reason and refer the case to an authorised person when necessary.

### Technical Failure

Record the failure, preserve the last confirmed status, and notify the responsible support person. If the tracker is unavailable, use an authorised manual fallback and reconcile the records after service is restored.

## 9. Fallback Procedure

If the proposed tracker is unavailable:

1. The responsible coordinator records the request using an approved manual register or form.
2. Department representatives continue to perform their authorised checks through the existing approved procedure.
3. Pending approvals remain pending until confirmed.
4. Once the tracker is available, the coordinator enters the manual updates and checks for duplicate records.
5. The final status is confirmed against the recorded departmental checks and approvals.

The manual process should follow the institution's authorised procedure. HostelClear must not become the sole source of approval unless the institution formally adopts it.

## 10. Expected Benefits

The proposed workflow may:

- Give students a clearer view of request progress.
- Make pending departmental checks easier to identify.
- Clarify who is responsible for the next action.
- Reduce repeated follow-up caused by unclear status information.
- Improve the traceability of exceptions and approvals.
- Support process review using recorded request dates and completion dates.

These are expected benefits, not measured outcomes. Actual improvements would need to be evaluated through a permitted pilot or a controlled test.

## 11. Success Measures

If the proposal is evaluated in a future pilot, useful measures could include:

- Average elapsed time from request submission to completion.
- Average student time spent on visits and follow-up.
- Number of requests returned because of missing information.
- Number of duplicate requests.
- Number of requests waiting for departmental verification.
- Number of requests requiring manual recovery after a technical failure.
- Additional time spent on review and support.

Measurements should use comparable requests and a defined observation period. Any pilot would require appropriate institutional permission.

## 12. Limitations and Assumptions

- The proposed sequence and required departmental checks need confirmation against the current official procedure.
- The roles listed here are proposed responsibilities and do not confirm the institution's existing staff assignments.
- The workflow has not been deployed in a production environment.
- Benefits and time savings are expected rather than proven.
- Any real implementation would require appropriate permissions, access controls, privacy safeguards, and approval from the institution.

## Conclusion

HostelClear proposes a structured way to track hostel vacating and no-dues clearance requests while retaining departmental responsibility and formal approval boundaries. It provides a basis for synthetic testing and future evaluation, subject to verification of the actual college procedure.
