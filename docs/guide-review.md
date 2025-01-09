# Dynamic Question Generation Workflow

## Job Role and Guide Setup
- When creating a **JobRole**, the admin defines a set of responsibilities or tasks in the **Guide**.
- Each responsibility in the Guide acts as a "template" for generating review questions.

## Review Creation
- When a review is initiated:
  - The app pulls the Guide for the user's JobRole to dynamically generate the review questions.
  - Universal questions (if any) are added alongside the Guide-based questions.

## Prompt Display
- The app formats the Guide entries into question prompts, e.g.,  
  *"How would you rate your performance in {{ guide.task }}?"*
- Responses are collected as one of the following, depending on the context:
  - **Text**
  - **Multiple choice**
  - **Rating**

## Response Storage
- Pre-generated questions are **not** stored.
- The app only stores:
  - User responses.
  - Ties responses to the **Review**, **Guide**, and **JobRole**.


# User Story: Dynamic Review Question Generation

## Title: Admin Creates and Assigns Job Role Guides for Dynamic Reviews

### As an:
Admin managing employee performance reviews.

### I want to:
Define a set of responsibilities or tasks for each Job Role and have the system dynamically generate review questions based on those responsibilities.

### So that:
Reviews are tailored to the specific duties of each Job Role, ensuring relevant and meaningful feedback is collected.

---

## Title: Employee Completes a Role-Specific Review

### As an:
Employee being reviewed.

### I want to:
Answer dynamically generated questions based on my Job Role responsibilities, along with any universal questions.

### So that:
I can provide feedback and self-assess my performance in a structured and relevant way.

---

## Title: Store Review Responses Without Pre-Generated Questions

### As an:
App developer.

### I want to:
Store only user responses tied to the Review, Guide, and JobRole instead of saving pre-generated questions.

### So that:
The app remains lightweight and flexible, allowing for dynamic question updates without altering stored responses.
