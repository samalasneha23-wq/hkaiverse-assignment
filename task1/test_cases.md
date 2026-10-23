# Task 1: HostelClear — Synthetic Test Cases

## 1. Purpose

These synthetic test cases evaluate how the proposed HostelClear workflow should respond to normal requests, incomplete information, duplicate requests, unauthorised actions, and failed steps.

These are simulated scenarios, not real student cases or results from a deployed system.

## 2. Test Case 1: Normal Request

**Scenario:** A student submits a complete hostel vacating request. All required departments complete their checks and the authorised officer approves the final clearance.

**Input:** Complete request details and all required clearances.

**Expected result:**
- A unique request ID is generated.
- Required departments receive their clearance tasks.
- Each department updates its status after completing its check.
- Final approval is available only after all required checks are complete.
- The student receives a completion confirmation.

**Recovery required:** No, unless an unexpected issue occurs.

**Pass condition:** The request is marked complete only after the required checks and final approval are recorded.

## 3. Test Case 2: Missing Information

**Scenario:** A student submits a request without a required field, such as the planned vacating date.

**Input:** Request with a required field missing.

**Expected result:**
- The request is flagged as incomplete.
- The student is told which information is missing.
- The request is not marked fully cleared.
- The student can correct and resubmit the information.

**Recovery required:** The student provides the missing information.

**Pass condition:** The incomplete request is not incorrectly approved, and the missing information is clearly identified.

## 4. Test Case 3: Duplicate Request

**Scenario:** A student submits the same vacating request twice.

**Input:** Two requests with matching identifying details and the same intended vacating event.

**Expected result:**
- The workflow flags a possible duplicate.
- It does not automatically create conflicting clearance tasks.
- An authorised coordinator reviews the duplicate.
- The valid request and its existing progress are preserved.

**Recovery required:** The coordinator confirms whether the second request is a duplicate or a genuinely separate request.

**Pass condition:** The duplicate does not lead to conflicting approvals or accidental loss of progress.

## 5. Test Case 4: Unauthorised Approval

**Scenario:** A person without the required permission attempts to approve a department clearance or final clearance.

**Input:** An approval attempt from an unauthorised account or role.

**Expected result:**
- The approval attempt is rejected.
- The clearance status remains unchanged.
- The action is recorded for appropriate review.
- The request remains pending until an authorised person completes the approval.

**Recovery required:** The assigned authorised person reviews and completes the required check.

**Pass condition:** An unauthorised person cannot approve or bypass a required clearance.

## 6. Test Case 5: Failed Step or Unavailable Staff

**Scenario:** A required department cannot complete its check because the responsible staff member is unavailable, or the workflow system becomes temporarily unavailable.

**Input:** A required clearance remains incomplete, or the system fails during processing.

**Expected result:**
- The request is not incorrectly marked complete.
- The outstanding clearance is shown as Pending.
- The responsible department and next follow-up action are identified.
- If staff are unavailable, follow-up or an authorised alternate is arranged where permitted.
- If the system fails, the approved paper fallback is used and records are reconciled when the system returns.

**Recovery required:** The authorised department completes the check, or the workflow is restored and any fallback records are reconciled.

**Pass condition:** The process can recover without losing required checks, records, or approval controls.

## 7. Test Summary

| Test | Expected outcome | Main control |
|---|---|---|
| Normal request | Correct completion | All required checks and final approval |
| Missing information | Request remains incomplete | Input validation |
| Duplicate request | Duplicate flagged for review | Duplicate detection |
| Unauthorised approval | Approval rejected | Role-based access |
| Failed step / unavailable staff | Request remains pending and can recover | Follow-up and fallback procedure |

## 8. Testing Limitations

These cases describe expected system behaviour. They have not been executed against a deployed application. They are design-level tests for the proposed workflow and should be tested with a prototype before real implementation.
