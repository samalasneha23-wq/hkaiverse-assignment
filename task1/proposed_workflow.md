# Task 1: HostelClear — Proposed Improved Workflow

## 1. Objective

HostelClear is a proposed workflow to make hostel vacating and no-dues clearance more organised. It aims to reduce unnecessary office visits, improve visibility of pending clearances, and handle delays when authorised staff are unavailable.

The proposal retains all required departmental checks and approval responsibilities.

## 2. Proposed Workflow

### Step 1: Submit a request

The student submits a hostel vacating request with the planned leaving date and the information required by the institution.

The system creates a unique request ID so the student can track the request.

### Step 2: Identify required clearances

The workflow displays the required clearance sections based on the institution's approved procedure.

The current blank form lists Library, Computer Lab, Academic Office, Chief Security Officer (CSO), Student Service Department (SSD), and Hostel.

No department is removed unless the institution confirms that its clearance is not required for that request.

### Step 3: Assign clearance responsibilities

Each required department receives a clearance task with:
- Request ID
- Department name
- Responsible authorised role
- Current status
- Date of last update
- Reason for any action required

### Step 4: Track clearance status

Each clearance uses one of these statuses:

- **Pending:** The department has not completed its check.
- **Cleared:** The authorised person has completed and approved the check.
- **Action Required:** Additional information or action is needed.
- **Not Applicable:** The check is not required for this case and this status has been approved by an authorised person.

### Step 5: Handle staff unavailability

If a faculty member or authorised staff member is unavailable, the clearance remains Pending.

The workflow records the responsible department and the next follow-up action. It may notify the responsible person or an authorised alternate, where institutional rules permit.

The student should be able to see that the clearance is pending rather than repeatedly visiting offices to discover its status.

A required approval must never be bypassed simply because a staff member is unavailable.

### Step 6: Complete independent checks in parallel

Where the institution confirms that checks are independent and may occur simultaneously, departments can process their clearances in parallel.

This may reduce the overall waiting period compared with visiting departments one by one.

### Step 7: Final review

After all required checks are completed, the designated authorised officer reviews the request.

The system must not mark the request fully cleared while a required approval or action remains outstanding.

### Step 8: Confirm completion

Once the authorised final approval is recorded, the student receives a clearance confirmation with the completion date and request reference.

## 3. Responsibilities

| Role | Responsibility |
|---|---|
| Student | Submit accurate information and complete required actions. |
| Department representative | Verify matters within the department's responsibility and update the clearance status. |
| Workflow coordinator | Monitor pending requests and follow up on delays. |
| Authorised final approver | Review required clearances and approve completion. |
| System administrator | Maintain access permissions and support system availability. |

These are proposed roles. The institution must assign them to its actual authorised personnel.

## 4. Exception Handling

| Situation | Expected response |
|---|---|
| Missing information | Mark Action Required and tell the student what information is needed. |
| Duplicate request | Flag the duplicate and refer it to an authorised coordinator before merging or closing it. |
| Staff member unavailable | Keep the clearance Pending and arrange follow-up or an authorised alternate. |
| Clearance not approved | Keep the request incomplete until the issue is resolved. |
| System failure | Use an institution-approved paper fallback and enter or reconcile the record when service returns. |
| Unauthorised approval attempt | Reject the action and preserve the approval boundary. |

## 5. Access and Privacy

Students should see their own request status. Department representatives should access only the information needed for their assigned checks. Only authorised personnel may approve clearances or change protected statuses.

The workflow should avoid exposing student enrolment numbers, financial details, or other private information to people who do not need it.

## 6. Expected Benefits

- Fewer unnecessary visits to departments.
- Better visibility of outstanding clearances.
- Reduced uncertainty when staff are unavailable.
- Clear ownership of pending tasks.
- Improved tracking of exceptions and completion.
- A record of decisions and final approval.

These are expected benefits, not measured results. They will be evaluated using synthetic test cases and an estimate of net time saved, including review and support effort.

## 7. Limitations

HostelClear is a proposal, not an existing IFHE system. It requires approval from the institution before implementation. The actual required checks, responsible roles, approval rules, and fallback procedure must be confirmed before deployment.
