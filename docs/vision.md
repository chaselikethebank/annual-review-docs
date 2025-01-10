 # Performance Review App Requirements

## Problem Definition
The organization requires a centralized web application for managing end-of-year performance reviews. This app will allow managers and employees to interact with job-specific review guides, send automated email notifications, complete review forms dynamically, and view a dashboard summarizing all performance data. The app must prioritize rapid development and ease of use, leveraging SQLite for cost-effectiveness and Laravel/Blade for an optimized developer experience.

## Requirements

### Functional Requirements

1. **User Management**
   - Authentication system for employees, managers, and admins.
   - Role-based permissions to control access (admin, manager, employee).

2. **Content Management**
   - CRUD operations for job review guides.
   - Assign job review guides to specific departments or employees.
   - Dynamically link guides to forms based on user roles and departments.

3. **Form Handling**
   - Generate review forms dynamically based on assigned job review guides.
   - Allow managers to fill forms for employees.
   - Allow employees to fill self-review and manager-review forms.
   - Store completed forms for reporting and auditing.

4. **Dashboard and Reporting**
   - Dashboard displaying summarized performance metrics.
   - Highlight flagged scores (below 70%, above 95%) with configurable thresholds.
   - Drill-down functionality to view individual review details.

5. **Data Integrity**
   - Audit logs for admin actions (form creation, deletions).

### Non-Functional Requirements

1. **Performance**
   - The application must handle up to 500 simultaneous users without performance degradation.
   - Use SQLite for low-cost, lightweight data storage.

2. **Usability**
   - Simple, intuitive UI for employees, managers, and admins.
   - Accessibility features for screen readers and keyboard navigation.

3. **Security**
   - Secure authentication and role-based access control.
   - Encrypted data storage and secure communication (TLS).

4. **Scalability**
   - Modular architecture to enable future migration to a more robust database (e.g., MySQL).

5. **Deployment**
   - Single-server deployment with SQLite.
   - Support for running on shared hosting or local servers.

### Scope Management
- Clearly define the scope to include only the features outlined above.
- Avoid feature creep by documenting additional requests for future versions.
- Establish checkpoints to review progress and ensure adherence to scope.

### Sign-Off Process
- Initial "back-of-the-envelope" ideas agreed upon by all stakeholders.
- Develop rough sketches (e.g., Excalidraw) for UI concepts.
- Create comprehensive Figma designs for approval.
- Write code only after final approval of designs and features.
 

 ## Guides as Reviews, A Design Architecture

## Job Role and Guide Setup
- A "Period" is created defining a term for reviews.
- When creating a **JobRole**, the admin defines a set of responsibilities or tasks in the **Guide**.
- Each responsibility in the Guide acts as a "template" for generating review questions.

## Review Creation
Reviews criteria are created 1/2 per the period's universal questions/prompts and 1/2 per the subjective user's role.

- When a review is initiated:
  - The app pulls the Guide for the user's JobRole to dynamically generate the review questions.
  - Universal questions (if any) are added alongside the Guide-based questions.
  - For each guide turned into a question the admin selects whether that response is to be delinated 
- Responses are collected as one of the following, depending on the context:
  - **Text**
  - **Multiple choice**
  - **Rating**
- The app formats the Guide entries into question prompts, e.g.,  
  *"How would you rate your performance in  guide.task ?"*




 
