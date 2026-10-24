# Capstone Proposal: CampusFlow — College Clearance Workflow Automation

## 1. Project Overview

**CampusFlow** is a proposed workflow-management solution designed to simplify the college clearance process, including hostel vacating and no-dues approvals. It brings multiple departmental clearance steps into one organised workflow, helping students track progress and helping authorised staff manage pending requests.

## 2. Problem Statement

The existing clearance process requires students to approach multiple departments for signatures and confirmations. This can involve repeated visits, uncertainty about pending approvals, and delays when the responsible staff member is unavailable.

CampusFlow proposes a centralised process to improve visibility, accountability, and coordination while retaining the approval authority of the relevant departments.

## 3. Project Objectives

- Provide a single request reference for each clearance application.
- Display the clearance status of each department.
- Identify missing information and duplicate requests.
- Assign responsibility for pending actions.
- Preserve approval boundaries and an auditable status history.
- Provide a fallback process when the digital workflow is unavailable.

## 4. Proposed Workflow

1. The student submits the clearance request and required details.
2. The system checks for missing information and possible duplicate requests.
3. A unique request ID is created for a valid submission.
4. Departmental clearance tasks are assigned to authorised staff.
5. Staff review the request and update the status.
6. Any outstanding requirement is communicated to the student.
7. The authorised official reviews the completed clearances and confirms final approval.
8. The student receives the final status and clearance record.

## 5. Core Features

| Feature | Purpose |
|---|---|
| Request registration | Record student and request details |
| Status dashboard | Show pending, cleared, and action-required tasks |
| Departmental task list | Display each department's responsibility |
| Duplicate detection | Flag possible repeated requests |
| Missing-information checks | Prevent incomplete requests from progressing |
| Role-based access | Restrict actions to authorised users |
| Status history | Record updates and decisions |
| Exception handling | Provide a recovery path for failed steps |
| Final clearance record | Summarise departmental decisions and final approval |

## 6. Inputs, Outputs, and Accountability

**Inputs:** Student identifier, required application details, relevant clearance records, and departmental decisions.

**Outputs:** Request ID, departmental status summary, outstanding-action list, decision history, and final clearance status.

**Accountability:**
- Students provide accurate information.
- Departmental staff verify matters within their responsibility.
- The designated authorised official retains final approval authority.

## 7. Exception Handling

| Scenario | Expected response |
|---|---|
| Missing information | Mark the request as requiring action and identify the missing details |
| Duplicate submission | Flag the possible duplicate for authorised review |
| Unauthorised approval attempt | Reject the action and preserve the existing status |
| Staff member unavailable | Keep the task pending and route it through an approved reassignment process |
| System failure | Preserve available records and use the approved manual fallback |
| Department reports an outstanding issue | Keep the relevant clearance pending until resolved |

## 8. Proposed Evaluation

The workflow can be evaluated using synthetic test cases representing normal submissions, missing information, duplicate requests, unauthorised actions, and failed steps.

Evaluation measures include:

- Time spent by the student on active follow-ups.
- Total elapsed time from submission to final clearance.
- Number of repeated visits or follow-ups.
- Number of incomplete or duplicate submissions detected.
- Time spent by staff on reviews and support.
- Correct handling of approval boundaries and exceptions.

Net time saved should account for review and support effort rather than considering only the student's reduced effort.

## 9. Proposed Implementation

A prototype could use Python with Streamlit for the interface and SQLite for storing request records and status history. Role-based permissions, validation rules, and status transitions would be implemented before testing the workflow with synthetic data.

The prototype would not replace official university records or approvals without institutional authorisation.

## 10. Expected Outcome

CampusFlow aims to make the clearance process easier to track, reduce avoidable follow-ups, and clarify responsibility for each pending action. Its effectiveness would be assessed through controlled test cases and a comparison of effort before and after the proposed workflow.

## 11. Scope and Limitations

This proposal describes a potential lab or capstone implementation. It does not assume that the university has approved or deployed the system. Actual implementation would require confirmation of departmental requirements, data-access permissions, privacy controls, and approval procedures.
