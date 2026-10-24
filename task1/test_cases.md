# Task 1: HostelClear — Synthetic Test Cases

## 1. Purpose

These test cases evaluate the proposed HostelClear workflow under normal and exceptional conditions. They are synthetic scenarios created for design evaluation. They do not represent live tests of an institution's production system.

Each case identifies the starting conditions, test steps, expected result, recovery action, and expected final status.

## 2. Test Case Summary

| Test ID | Scenario | Expected outcome |
|---|---|---|
| TC01 | Normal clearance request | Required checks and approvals are completed before closure |
| TC02 | Missing information | Request is returned for the missing information |
| TC03 | Duplicate request | Duplicate is identified and conflicting records are avoided |
| TC04 | Unauthorised approval attempt | Unauthorised action is blocked and referred appropriately |
| TC05 | Failed department step or technical failure | Request remains pending until the failure is recovered |

## 3. TC01 — Normal Clearance Request

**Objective:** Verify that a complete request can move through all required stages.

**Starting conditions:**
- A student submits a complete request.
- Required departmental checks are available.
- The relevant authorised representatives can perform their checks.

**Test steps:**
1. Submit a request with all required information.
2. Validate the submitted information.
3. Create a unique request ID.
4. Record the result of each required departmental check.
5. Complete the required final approval.
6. Close the request.

**Expected result:**
- The request receives a unique tracking ID.
- Each required verification has a recorded outcome.
- The request progresses through the appropriate statuses.
- The request is marked Completed only after all required checks and approvals are recorded.

**Recovery action:** If any check remains incomplete, keep the request pending and assign the next action to the responsible person.

**Expected final status:** Completed, provided all required checks and approvals succeed.

## 4. TC02 — Missing Information

**Objective:** Verify that incomplete requests are not incorrectly approved.

**Starting conditions:**
- A request is submitted without one required field or document.

**Test steps:**
1. Submit the incomplete request.
2. Run the validation step.
3. Identify the missing information.
4. Notify the student or requester.
5. Supply the missing information.
6. Validate the request again and resume processing.

**Expected result:**
- The missing information is identified.
- The request is marked Action Required.
- The request does not proceed to final approval while the required information is missing.
- The corrected request can resume processing after successful validation.

**Recovery action:** The student supplies the missing information. The coordinator checks it before continuing.

**Expected final status:** Pending Department Verification or a later valid status after the missing information has been supplied and checked.

## 5. TC03 — Duplicate Request

**Objective:** Verify that repeated submissions do not create conflicting clearance records.

**Starting conditions:**
- An active clearance request already exists for the same intended clearance.
- The same request is submitted again.

**Test steps:**
1. Submit the original request.
2. Submit a second request with matching identifying information.
3. Check for an existing active request.
4. Review whether the second submission is a duplicate.
5. Link it to the existing request or record it as a duplicate according to the approved rules.

**Expected result:**
- The duplicate is detected or flagged for review.
- The original request remains the primary active record.
- Conflicting approvals or duplicate completion records are not created.

**Recovery action:** The coordinator reviews uncertain matches before merging, linking, or closing a record.

**Expected final status:** The original request retains its valid status. The duplicate is linked or marked as a duplicate after review.

## 6. TC04 — Unauthorised Approval Attempt

**Objective:** Verify that users cannot approve checks outside their authority.

**Starting conditions:**
- A user without the required approval permission attempts to approve a departmental check or final clearance.

**Test steps:**
1. Create a request with at least one required check still pending.
2. Attempt approval using an unauthorised role.
3. Check whether the workflow rejects the action.
4. Review whether the request status remains unchanged.
5. Refer the pending approval to the authorised representative.

**Expected result:**
- The unauthorised approval is blocked.
- The request does not become Approved or Completed because of that action.
- The pending check remains visible.
- The event is recorded where audit logging is supported.

**Recovery action:** The authorised representative reviews and completes the required approval.

**Expected final status:** Pending Department Verification or Pending Final Approval until the authorised action is completed.

## 7. TC05 — Failed Department Step or Technical Failure

**Objective:** Verify that a failed step does not cause the workflow to lose its status or incorrectly close a request.

**Starting conditions:**
- A request is being processed.
- A department verification cannot be completed, or the tracking service becomes unavailable.

**Test steps:**
1. Begin processing a valid request.
2. Simulate an unavailable department representative or a technical failure.
3. Attempt to continue the workflow.
4. Check whether the incomplete step remains visible.
5. Record the issue and notify the responsible person.
6. Restore the service or resume the authorised manual process.
7. Reconcile the recorded status and continue processing.

**Expected result:**
- The incomplete step is not treated as successful.
- The request remains pending or is placed On Hold as appropriate.
- The last confirmed status is preserved where technically possible.
- Recovery actions are recorded.
- The request resumes only after the failed step has been completed or the issue has been resolved.

**Recovery action:** Use the approved manual fallback during an outage, then reconcile records after service restoration. If a representative is unavailable, follow the approved escalation process.

**Expected final status:** Pending Department Verification or On Hold until the failed step is resolved; the request may proceed afterwards.

## 8. Overall Acceptance Criteria

The proposed workflow is considered to satisfy these design checks if:

1. Complete requests can progress through the required stages.
2. Missing information prevents premature approval.
3. Duplicate submissions do not create conflicting active records.
4. Unauthorised users cannot approve restricted steps.
5. Failed steps remain visible and can be recovered without falsely marking a request complete.
6. Every completed request has the required verification and approval records.

These are expected outcomes for the proposed design. They should be validated through a prototype or authorised pilot before the workflow is used in practice.

## 9. Limitations

The scenarios are synthetic and describe expected behaviour. No claim is made that these tests were executed against a live HostelClear system or an institutional production environment.
