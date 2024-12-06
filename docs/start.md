 # About

Annual reviews can be tough and expensive. 

Here are some options and their tradeoffs: 

# Tool Comparisons

## 1. Leadr.com

### What it does:
Leadr is a people development software focused on leadership, performance, and employee engagement. It helps organizations streamline 1:1 meetings, goal setting, feedback, and leadership development through a simple interface.

### Key Features:
- 1:1 meeting scheduling and tracking.
- Goal-setting and progress monitoring.
- Real-time feedback and coaching tools.
- Employee engagement tracking.

### Tradeoffs:

#### Pros:
- Focuses heavily on leadership development, not just performance metrics.
- Easy-to-use and intuitive UI.

#### Cons:
- Limited integration with larger HR systems.
- May lack depth in analytics compared to competitors like Lattice or BambooHR.

### Cost:
Pricing is not publicly available but typically depends on organization size and features. Estimated at $7-$12 per user/month, based on reviews.

---

## 2. Trakstar.com

### What it does:
Trakstar offers a performance management suite with tools for employee reviews, goal tracking, and learning management. It's designed for HR teams to manage talent development and evaluations.

### Key Features:
- Goal setting and tracking.
- 360-degree feedback and performance reviews.
- Learning management system (LMS) integration.
- Analytics and reporting dashboards.

### Tradeoffs:

#### Pros:
- Comprehensive performance and feedback management tools.
- Offers both reviews and learning management in one platform.
- Highly customizable.

#### Cons:
- May be overkill for smaller teams that don’t need LMS or advanced analytics.
- Interface can feel outdated compared to newer tools like 15Five.

### Cost:
Starts at $5,000/year for up to 50 users (~$8/user/month for larger teams). Add-ons for LMS can increase pricing.

---

## 3. Jotform

### What it does:
Jotform is an online form builder that allows users to create forms, collect responses, and automate workflows. It’s popular for surveys, event registration, payment collection, and more.

### Key Features:
- Drag-and-drop form builder.
- Advanced logic and conditional formatting.
- Payment integrations (Stripe, PayPal, etc.).
- Workflow automation and third-party app integrations.

### Tradeoffs:

#### Pros:
- Highly customizable forms with plenty of templates.
- Affordable pricing and free tier for small projects.
- Strong integration with payment processors.

#### Cons:
- Advanced features (e.g., HIPAA compliance, workflows) are only in higher-tier plans.
- May lack advanced analytics compared to Typeform or SurveyMonkey.

### Cost:
- **Free**: 5 forms, 100 submissions/month.
- **Bronze Plan**: $34/month (25 forms, 1,000 submissions/month).
- **Silver Plan**: $39/month (50 forms, 10,000 submissions/month).
- **Gold Plan**: $99/month (unlimited forms, 100,000 submissions/month).

## 4. Custom App Solution

### Tradeoffs:

#### Pros:
- A simpler feature set tailored to the use case makes things less expensive and easier for new users. 
- Own it! 
- Yours to give away - make it open source even!
- Onboarding is simple; very shallow learning curve when learning to use an app that only does 3+/- things!

#### Cons:
- Blindspots in development are difficult to overcome. 
- Development time is much longer than paying for a SASS solution.
- Decision Fatigue is real! Everything from rounded corners or squre corners, sql servers or mongo db, react or vue. 
- Maintanence is an internal responsibility now. 

### Potential Feature Set: 

#### Boss's Create Guides
Admin users (bosses) have the ability to create and manage guides, which serve as templates or instructions for performance reviews, goal-setting, or other processes within the app.

#### Users Fill Out Forms
Employees (users) are assigned specific guides and fill out forms accordingly. These forms can include performance reviews, feedback, self-assessments, etc., tailored to the assigned guide.

#### Email Notifications
The app sends automatic email notifications to users, informing them of new tasks, updates, or reminders related to their assigned guides and forms.

#### Dashboard View
Users and admins can access a dashboard that provides an overview of their tasks, progress, and pending actions. Admins can see a comprehensive view of all users and their current statuses.

#### Show Pages Per User
Individual user pages display their relevant information, such as submitted forms, completed tasks, and progress toward goals. Admins can access these pages to review the user’s performance and provide feedback.

---

 


## 5. Open Source Solutions 

### Generic Feature Set

Apps that have been built braodly and with generic feature sets might have some utility but require reworking. It can be diff to recognize where these sets of apps might have working solutions, where they need amendment and then the time/resource it takes to execute on.  

### 1. Odoo || Performance Appraisals

- An open-source performance management software that can create appraisals quickly and efficiently review employees' performances.

### Tradeoffs:

#### Pros:
- Comprehensive and customizable appraisal process with automated scheduling.
- Flexible goal-setting and survey creation for different departments and roles.
- Integration with other Odoo modules for a complete HR management solution.
- User-friendly interface with various views (Kanban, list, Gantt, calendar).
- YouTube Tutorials

#### Cons: 
- Steep learning curve for new users, especially those unfamiliar with ERP systems.
- Complex customizations may require technical expertise or third-party assistance and Odoo is famously expensive.
- Potential performance issues with large-scale implementations.
- Upgrading between versions can be challenging, especially with extensive customizations.
- Need to set up a server to keep costs low I believe. 

#### Cost:
- Community Edition: Free, but limited to one app and its dependencies.
- Enterprise Edition: Pricing based on number of users, which may impact scalability costs.

#### Repo:
[odoo/odoo](https://github.com/odoo/odoo.git)

#### Link: 
[YouTube Demo](https://www.youtube.com/watch?v=0doS9RfqS-4)

### 2. Employee Performance Review Feedback Management System

- A MERN stack project offering features for both administrators and employees, including managing performance reviews and submitting feedback.

### Tradeoffs:

#### Pros:
- Built on modern MERN stack (MongoDB, Express.js, React, Node.js)
- Separate features for administrators and employees
- Customizable for specific organizational needs
- Potential for real-time updates and responsive design

#### Cons:
- Has the wrong naming conventions, "Feedbacks" instead of "Reviews"
- Doesn't have email built in - would need to build that on top of
- Doesn't have dynamic quiestions built out, currently a simple single input field 


#### Cost:
- Free and open-source
- Hosting and maintenance costs may apply depending on deployment $20 - $60 monthly +/- or Turn it on Nov-Mar and buy a really fast server, then shut it down?

#### Repo:
[https://github.com/ParmodKumar28/Employee-Review-System]

#### Link:
[Working Demo](https://employee-review-system-r8tw.onrender.com/api/employee/register)<br/>
[Video Demo](https://www.youtube.com/watch?v=mvHhUozvC0w&feature=youtu.be)



### 3. Monica

- A personal CRM built with Laravel 11 that can be adapted for performance reviews, using the latest Laravel version with Jetstream Inertia stack.

### Tradeoffs:

#### Pros:
- Built on the latest Laravel framework, ensuring modern development practices
- Jetstream Inertia stack provides a robust frontend
- Highly customizable for various use cases, including performance reviews
- Active development and community support

#### Cons:
- Primarily designed as a personal CRM, requiring adaptation for corporate use
- May need significant modifications for comprehensive performance review features
- Learning curve for developers unfamiliar with Laravel or Inertia.js

#### Cost:
- Free for self-hosted version
- Hosting and customization costs may apply

#### Links: 
[monicahq/monica](https://github.com/monicahq/monica)<br/>

[monica hq](https://www.monicahq.com/)

### 4. InvoiceShelf

- An open-source invoicing solution built with Laravel 10 that could be customized for annual reviews.

### Tradeoffs:

#### Pros:
- Built on Laravel 10, offering a solid foundation for customization
- Open-source, allowing for extensive and absolute modifications
- Potential for integration with existing Laravel-based systems or libraries for example the mail notification feature

#### Cons:
- Primarily designed for invoicing, requiring significant adaptation for performance reviews
- May lack specific features needed for comprehensive employee evaluations
- Customization could be time-consuming and require Laravel expertise

#### Cost:
- Free and open-source
- Development and hosting costs for customization and deployment

### 5. Krayin Laravel CRM

- A free and open-source Laravel CRM solution that can be adapted for complete customer lifecycle management, including performance reviews.

### Tradeoffs:

#### Pros:
- Built on Laravel, offering flexibility and scalability
- Modular approach allows for easy customization
- Includes features like custom attributes that could be adapted for reviews
- Active development and community support
- Famously championed 
- Incredible UI, Dashboard, Modals // LOOKS EXPENSIVE!

#### Cons:
- Designed for customer management, requiring significant significant modifications for employee reviews - will need to rip out maybe %95 of the code
- Learning curve for those unfamiliar with Laravel, but i like Laravel

#### Cost:
- Free and open-source
- Hosting and potential customization costs may apply

#### Links: 
[Krayin HQ](https://krayincrm.com/) <br/>
[Demo](https://demo.krayincrm.com/)
