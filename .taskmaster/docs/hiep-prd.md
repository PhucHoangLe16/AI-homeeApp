# Overview

The HomEE app is designed specifically for organizations specializing in providing tailored housing and accommodation solutions for employees and businesses. Seamlessly integrated with the HomEE portal, the app empowers the employees to manage their tasks efficiently, stay organized, and deliver their services with ease.
It's for field employees like maintenance staff, cleaning crews, and inspection personnel who need to manage their daily work, access job details, and report progress while on the go, often in environments with limited connectivity.
The HomEE app is valuable because it aims to streamline workflows, improve task management, enhance service delivery efficiency, increase operational productivity, improve data accuracy from the field, and empower employees with a user-friendly mobile tool. This ultimately leads to better resource management for the organization and a more organized, efficient work experience for the employees.

# Core Features

Here are the main features of the HomEE mobile application:

1. **User Authentication & Profile Management:**

   - **What it does:** Allows users to securely log in, including handling for single and multi-tenant accounts, and an initial password reset flow. **Only users who have at least one `RoleMobile` (INSPECTOR, MECHANIC, CLEANER, ADMINISTRATOR) assigned to their profile can log in to the HomEE app.** Users can view and manage their profile information (personal details, language, app settings like default home screen view and photo storage) and update their password.
   - **Why it's important:** Ensures secure access to sensitive job and company data, allows personalization, and keeps user information accurate.
   - **How it works:** Users enter a username, then potentially select a tenant, and finally enter a password. Accounts do not change password after 6 months go through a password reset. Profile data is viewable and partially editable, syncing with the HomEE portal.

2. **Home Screen ("Welcome" / "This Week"):**

   - **What it does:** Serves as the main dashboard after login, providing a daily overview of work. It features a date selector of the current week to view tasks or shopping lists for any chosen day. Users can toggle between a "Shopping list" summary and a "Task" summary.
   - **Why it's important:** Gives users a quick, organized view of their immediate responsibilities and easy access to their primary work areas.
   - **How it works:** A date selector filters content. Tabs switch between shopping list summaries (with different interactions for picked-up vs. not-picked-up items) and task summaries (showing jobs with status indicators). The default view can be set in user profile settings.

3. **Shopping List Management:**

   - **What it does:** Enables employees to view consolidated shopping lists, filter them (by date, warehouse, job type), input quantities of articles picked up, and confirm completion of picking up articles. It includes an overview and a detail screen for allocating picked-up items to specific jobs.
   - **Why it's important:** Ensures employees have all necessary materials for their jobs, improving preparedness and efficiency, and helps in tracking inventory.
   - **How it works:** Users filter lists, input "picked up" quantities on an overview. They can drill down to a detail screen to allocate these quantities to specific jobs. A confirmation process with modal dialogs finalizes the pickup.

4. **Task (Job) Management & Viewing:**

   - **What it does:** Allows users to view their list of assigned jobs (Inspections, Maintenance, Cleaning), filter them (by date range, location, inspection type), and access detailed job information across several screens (General, Location, Needed Articles) before starting work.
   - **Why it's important:** Provides employees with all necessary information about their assigned tasks, helping them understand their workload and prepare effectively.
   - **How it works:** Jobs are displayed in tabs by type (Inspection, Maintenance, Cleaning) with filtering options. Users can toggle to see completed jobs. Visual cues indicate offline-ready or completed jobs. Clicking a job leads to a multi-page detail view.

5. **Create New Task (Maintenance/Cleaning):**

   - **What it does:** Allows authorized users (Mechanics/Cleaners) to create new Maintenance or Cleaning tasks directly in the app, including defining general job information and associating specific work points, potentially using templates.
   - **Why it's important:** Facilitates the documentation and management of ad-hoc or unscheduled work, ensuring all tasks are tracked.
   - **How it works:** A two-step process. Step 1 captures general details (title, location, unit, date, estimated hours). Step 2 involves selecting templates and configuring maintenance/cleaning points with complex logic for point application and management.

6. **Job Execution ("Perform Job"):**

   - **What it does:** This is the core interface for actively working on a job. Users can select unit, review individual inspection/work points, record findings (description, photos), assign review codes (Green/Orange/Red), and optionally add "Cost to bill" items and "Follow up actions."
   - **Why it's important:** Enables detailed recording of work performed, issues found, and actions taken, forming the basis for job completion and reporting.
   - **How it works:** Users navigate through units and their points. Each point allows for input of description, photos, a mandatory review code, and optional costs/follow-up actions via modals. A progress bar tracks completion.

7. **Used, Returned, and Broken Articles Management:**

   - **What it does:** Allows users to document articles consumed from job stock or van stock ("Used"), articles returned to warehouse/van or from location ("Returned"), and articles damaged from job stock or found at location ("Broken").
   - **Why it's important:** Critical for accurate inventory tracking, job costing, and material management.
   - **How it works:** A sequence of screens where users input quantities for different categories of articles, selecting sources (e.g., "From Van") and destinations (e.g., "To Warehouse") from dropdowns. Calculations for "Available" quantities are dynamic based on previous inputs.

8. **Job Summary and Submission:**

   - **What it does:** Provides a comprehensive overview of all work performed, materials used/returned/broken, time spent (editable actual hours), expenditures, follow-up actions, and allows for general feedback before the job is submitted.
   - **Why it's important:** Offers a final review point for the employee and aggregates all job data for submission and record-keeping.
   - **How it works:** Displays expandable/collapsible sections summarizing data from previous steps. The user reviews, can edit actual hours, add feedback, and then "Submit" the job, which marks it as ready on mobile and syncs with the portal.

9. **Offline Mode Capabilities:**

   - **What it does:** Allows the app to function when the user has no internet connectivity. Users can view cached job details, perform jobs, and save progress locally. Data syncs when connectivity is restored.
   - **Why it's important:** Essential for field employees who often work in areas with poor or no signal, ensuring uninterrupted productivity.
   - **How it works:** A network status icon indicates connectivity. Cached data is used for viewing. Job progress is saved to a local database. Specific actions like creating new tasks or saving "additional" articles (from van/location) are restricted offline. Automatic and timed synchronization occurs when online.

# User Experience

## User Personas

- **Employee (Main Worker):** The primary user. Responsible for performing tasks like shopping, inspections, maintenance, and cleaning. Needs to manage their profile, view job details, update job statuses, record findings, manage articles, and potentially create new tasks.
- **Co-worker:** Assists a Main Worker. Has restricted access: can view job details, view the "Perform Job" and "Summary" pages, and edit their "Actual Hours" but cannot start jobs or manage job-specific articles.

## Key User Flows

1. **Login & Initial Setup:**
   - User enters username -\> (if multi-tenant) selects tenant -\> enters password -\> lands on Home screen.
   - If Account does not change password after 6 months: Username -\> Reset Password (set new complex password) -\> Home screen.
2. **Daily Work Overview (Home Screen):**
   - User selects a day from current week -\> views Shopping List summary or Task summary for that day -\> toggles between Shopping/Task views.
   - Interacts with shopping items (navigate for "not picked up", expand for "picked up").
   - Clicks a task to view its details.
3. **Managing Shopping List:**
   - User navigates to Shopping List screen -\> applies filters (date, warehouse, type) -\> views list of articles -\> inputs "picked up" quantity for an article -\> optionally clicks article to go to Shopping List Detail screen -\> allocates picked-up quantity among jobs -\> saves.
   - User clicks "Confirm" on overview -\> confirms in modal -\> shopping list is marked completed.
4. **Managing & Viewing Tasks:**
   - User navigates to Tasks screen -\> selects job type tab (Inspection/Maintenance/Cleaning) -\> applies filters (date range, location, inspection sub-type) -\> views job list -\> toggles "Show Completed Jobs" -\> clicks a job.
   - Navigates through Job Detail pages: General Info -\> Location Info -\> Needed Articles.
5. **Creating a New Task (Maintenance/Cleaning):**
   - User on Tasks screen (Maintenance/Cleaning tab) -\> clicks "+" icon -\> New Task screen (Step 1: General Info - title, location, unit, date, estimated hours, instruction) -\> clicks "Next".
   - Step 2: Template & Points (select template, manage/add/remove/order points with complex logic) -\> clicks "Open" (with potential warnings for no points/empty units) -\> task created.
6. **Performing a Job (Full Cycle):**
   - From "Needed Articles" screen, user clicks "Start" -\> Perform Job screen.
   - Selects Unit/Sub-unit -\> for each Inspection Point: enters Description, selects Review Code (Green/Orange/Red), takes Photos, optionally adds Cost to Bill, optionally adds Follow-up Actions.
   - Clicks "Save" to save progress.
   - Clicks "Used article" -\> Used Article screen (articles job-allocated and additional articles used).
   - Clicks "Returned" tab (to Returned) -\> Returned Article screen (articles returned from job or location).
   - Clicks "Broken" tab (to Broken) -\> Broken Article screen (articles broken from job or location).
   - Clicks "Summary" -\> Summary screen (reviews all job data, edits Actual Hours, adds Feedback).
   - Clicks "Submit" -\> job submitted, navigates to Task List.
7. **Offline Usage:**
   - User loses connection (icon turns red) -\> continues to view cached job details or perform an already started job -\> saves progress locally.
   - User attempts an offline-restricted action (e.g., save additional articles) -\> sees error message.
   - User regains connection -\> data syncs automatically.
8. **Profile Management:**
   - User clicks Profile icon -\> views Profile Detail (info, language, roles, settings) -\> edits editable fields -\> clicks "Save changes".
   - Selects "Password" tab -\> enters Old/New/Confirm Password -\> clicks "Save changes".
   - Clicks "Logout".

## UI/UX Considerations

- **Consistent Layout:** Main application layout with a persistent Header (Screen Title, Network Status, Notification, Profile icons) and a Bottom Navigation Bar (This Week, Shopping List, Task) on key screens.
- **Clear Navigation:** Intuitive navigation between screens and sections. "Previous," "Next," "Cancel," "Save," "Open," "Submit" buttons guide users through flows.
- **Visual Cues:**
  - Network Status Icon: Green (online), Red (offline).
  - Job Status: Green border/checkmark for completed jobs; Green dashed border/offline icon for ready offline jobs.
  - Shopping List: Purple border for picked-up items on Home; Green/Purple background for "Confirm" button based on list status.
  - Progress Bar: Visual feedback on job completion progress.
  - Review Codes: Distinct colors (Green, Orange, Red) for inspection point evaluation.
- **Interactive Elements:** Dropdowns for selections, date pickers, toggle switches (e.g., photo storage, show completed jobs), expandable/collapsible sections in summaries.
- **Modal Dialogs:** Used for confirmations (e.g., completing shopping list), warnings (e.g., no points added to new task), and focused data entry (e.g., Cost to bill, Follow-up actions).
- **Error Handling & Messaging:** Clear, contextual error messages for validation failures, offline restrictions, and other issues. Success messages for key actions.
- **Input Validation:** Client-side validation for required fields, character limits, numeric inputs, password complexity, etc., providing immediate feedback.
- **Read-only Fields:** Clearly distinguish editable fields from read-only information (e.g., username, roles).
- **Offline Experience:** App should clearly communicate its offline status and limitations. Save operations should provide feedback on success/failure.
- **Accessibility:** While not explicitly detailed, standard mobile accessibility considerations (e.g., sufficient font sizes, color contrast, touch target sizes) should be applied.

# Technical Architecture

## System Components

1. **HomEE Mobile Application:**
   - React Native application for iOS and Android devices (React native with typescript).
   - Handles user interface, user input, local data storage, offline logic, and communication with the backend.
2. **Local Database (on Mobile Device):**
   - Realm database.
   - Stores user data, job data, settings, and any offline modifications until synchronized with the backend.
3. **(Backend) HomEE Portal & APIs:**
   - Provides master data, business logic, and data synchronization services for the mobile application. (Note: Details of backend architecture are not the focus of this mobile-centric PRD section, but its existence and role are crucial for the mobile app).

## Data Models (High-Level Overview)

- Response from backend:

  ```typescript
  type APIResponse<T> = {
    message: string;
    statusCode: number;
    data: T;
  };
  ```

- **Profile:**

  ```typescript
  class Profile {
    _id!: string;
    isActive!: boolean;
    username!: string;
    email!: string;
    firstName!: string;
    lastName!: string;
    gender!: string;
    language!: string;
    phone1!: string;
    phone2!: string;
    roles!: Role[];
    thisWeekDefaultDisplay!: string;
  }
  ```

- **Role:**

  ```typescript
  enum RoleMobile {
    INSPECTOR = "inspector",
    MECHANIC = "mechanic",
    CLEANER = "cleaner",
    ADMINISTRATOR = "administrator",
  }
  class Role {
    key!: RoleMobile;
    decimal!: number;
  }
  ```

- **Shopping List:**

  ```typescript
  class Storage {
    _id!: string;
    description!: string;
  }
  class Category {
    _id!: string;
    name!: string;
    identifier?: number;
  }
  class ReservedDetail {
    _id!: string;
    amount!: number;
    pickedUp!: number;
    job!: Job;
    location!: Location;
  }
  class Job {
    _id!: string;
    identifier!: string;
    plannedDate!: string;
    jobType!: string;
    title!: string;
  }
  class Location {
    _id!: string;
    fullAddress!: string;
    isActive?: boolean;
    locationOf?: LocationOf[];
  }
  class LocationOf {
    key!: string;
    value!: string;
    position!: number;
  }
  class ShoppingList {
    _id!: string;
    completed!: boolean;
    storage!: Storage;
    totalAmount!: number;
    totalPickedUp!: number;
    identifier!: string;
    description!: string;
    category!: Category;
    reservedDetails!: ReservedDetail[];
  }
  ```

- **Task:**

  ```typescript
  enum InspectionType {
    BEGIN = "begin",
    END = "end",
    REGULAR = "regular",
  }
  enum JobType {
    INSPECTION = "inspection",
    MAINTENANCE = "maintenance",
    CLEANING = "cleaning",
  }
  enum TaskStatus {
    OPEN = "open",
    IN_PROGRESS = "in_progress",
    COMPLETED = "completed",
    CLOSED = "closed",
  }
  class UnitOfLocation {
    _id!: string;
    name!: string;
    position!: number;
    parent?: string;
    label?: string;
  }
  class Employee {
    _id!: string;
    employee?: string;
    displayName!: string;
    estimatedHours?: number;
    actualHours?: number;
  }
  enum ReportType {
    CUSTOMER = "customer",
    SUPPLIER = "supplier",
    INTERNAL = "internal",
  }
  class Equipment {
    _id!: string;
    description!: string;
    type!: string;
  }
  class TaskDetail {
    _id!: string;
    jobType!: JobType;
    title!: string;
    status!: TaskStatus;
    units!: Omit<UnitOfLocation, "position">[];
    assignee!: Employee;
    employees!: Employee[];
    planner!: Employee;
    plannedDate!: string;
    type!: InspectionType;
    reportType?: ReportType;
    equipments!: Equipment[];
    identifier!: string;
    instructions?: string;
    location!: Location;
    images?: string[];
    feedbacks?: string;
  }
  class Task {
    _id!: string;
    identifier!: string;
    title!: string;
    type!: InspectionType;
    jobType!: JobType;
    location!: Location;
    status!: TaskStatus;
    plannedDate!: Date;
    assignee!: string;
    isDeleted?: boolean;
    isActive?: boolean;

    // from api task detail
    taskDetail!: TaskDetail;

    // from api perform job
    units!: JobUnit[];

    // from needed article detail
    needArticles!: NeededArticle[];

    // from api used/return/broken article of this task
    articleJob!: ArticleJob;

    // from api summary job (optional)
    summaryJob!: SummaryJob;

    // from api summary article (optional)
    summaryArticle!: SummaryArticle;

    // ready job request
    actualHours?: number;
    feedbacks?: string;
    fuaDescriptions?: string;

    // local flag
    isReady?: boolean;
    isStarted?: boolean;
    isJobChanged?: boolean;
    isArticleChanged?: boolean;
    isActualHoursChanged?: boolean;
  }
  ```

- **Article:**

  ```typescript
  class UsedArticle {
    _id!: string;
    identifier!: string;
    description!: string;
    articleId!: string;
    amount!: number;
    pickedUp!: number;
    used!: number;
    unused?: number;
    returned!: number;
    broken!: number;
    totalExistInLocation!: number;
    remaining?: number;
    reason?: string;
    salePrice!: number;
    removalFee!: number;
    priceInclusiveLaborPrice!: number;
  }
  class ReturnedBrokenArticle {
    _id?: string;
    storage?: InventoryStorage | null;
    order?: number;
    type?: StorageType;
    articles!: Article[];
  }
  class Article {
    _id?: string;
    article?: string;
    articleId?: string;
    amount?: number;
    order?: number;
    reason?: string;
    identifier?: string;
    description?: string;
    unused?: number;
    isDelete?: boolean;
    available?: number;
    totalExistInLocation?: number;
    salePrice?: number;
    removalFee?: number;
    priceInclusiveLaborPrice?: number;
  }
  class AdditionalArticle {
    _id?: string;
    order?: number;
    storage!: InventoryStorage;
    articles!: Article[];
    isDelete?: boolean;
  }
  ```

## APIs and Integrations

- Header request:
  `  headers: { 'x-tenant-platform': 'mb', 'x-tenant-id': '123', // if have tenantId }`
- Response from backend:
  `typescript type APIResponse<T> = { message: string; statusCode: number; data: T[]; } `
- **Authentication API:**

  - `GET /auth/tenant-profiles?username={username}` (username) -\> returns tenant profiles.

    ````typescript
    // Response from backend:
    class TenantProfile {
      _id!: string;
      tenant!: {
            _id: string;
            name: string;
      };
    }```
    ````

  - `POST /auth/login` (username, tenantId, password) -\> returns session token, user details, tenant status.

    ````typescript
    // Request from mobile:
    class LoginRequest {
      username: string;
      tenantId: string;
      password: string;
    }

    // Response from backend:
    class LoginResponse {
      accessToken!: string;
      refreshToken!: string;
      profile!: Profile;
      tenantId!: string;
      accessTokenExpiresIn!: number;
      refreshTokenExpiresIn!: number;
      tenantName!: string;
    }```
    ````

  - `POST /auth/login` (token for initial reset, new_password).
  - ````typescript
      // Request from mobile:
      class ResetPasswordRequest {
        username: string;
        tenantId: string;
        password: string;
        newPassword: string;
      }

      // Response from backend:
      class LoginResponse {
        accessToken!: string;
        refreshToken!: string;
        profile!: Profile;
        tenantId!: string;
        accessTokenExpiresIn!: number;
        refreshTokenExpiresIn!: number;
        tenantName!: string;
      }```
    ````

- **User Profile API:**

  - `GET /tenant-profiles/me` -\> returns user profile data.

    - ````typescript
      // Response from backend:
      class Profile {
        _id!: string;
        isActive!: boolean;
        username!: string;
        email!: string;
        firstName!: string;
        lastName!: string;
        gender!: string;
        language!: string;
        phone1!: string;
        phone2!: string;
        roles!: Role[];
        thisWeekDefaultDisplay!: string;
      }```
      ````

  - `PUT /tenant-profiles/me` (updated_fields) -\> updates user profile.

    - ```typescript
      class UpdateProfileRequest {
        email: string;
        firstName: string;
        lastName: string;
        phone1: string;
        phone2: string;
        gender: string;
        language: string;
        thisWeekDefaultDisplay: string;
      }

      // Response from backend:
      class Profile {
        _id!: string;
        isActive!: boolean;
        username!: string;
        email!: string;
        firstName!: string;
        lastName!: string;
        gender!: string;
        language!: string;
        phone1!: string;
        phone2!: string;
        roles!: Role[];
        thisWeekDefaultDisplay!: string;
      }
      ```

  - `POST /tenant-profiles/me/update-password` (old_password, new_password).

    - ```typescript
      class UpdatePasswordRequest {
        password: string;
        oldPassword: string;
      }
      ```

- **Shopping List APIs:**

  - `GET /inventory-management/reserved/shopping-list/{id}?sortBy=updatedAt&sortDir=desc&plannedDate={date}` (shopping list summary - This week page)
  - `GET /inventory-management/reserved/shopping-list/{id}?sortBy=updatedAt&plannedDate={date}&storage={storageId}&jobType={jobType}&completed={false}` (shopping list page - Shopping list page)

    - ```typescript
      class ShoppingList {
        _id!: string;
        completed!: boolean;
        storage!: Storage;
        totalAmount!: number;
        totalPickedUp!: number;
        identifier!: string;
        description!: string;
        category!: Category;
        reservedDetails!: ReservedDetail[];
      }
      ```

  - `GET /inventory-management/storage&pageSize=-1&sortBy=updatedAt&sortDir=desc&type=Warehouse&isActive=true`

    - ```typescript
      class Storage {
        _id!: string;
        description!: string;
      }
      class Warehouse extends Storage {
        _id!: string;
        description!: string;
      }
      ```

  - `PUT /inventory-management/reserved/shopping-list/update-picked-up`

    - ```typescript
      class ReservedDetail = {
        _id: string;
        pickedUp: number;
      }

      class UpdatePickedUpRequest {
        reservedDetails: ReservedDetail[];
      }
      ```

  - `POST /inventory-management/reserved/shopping-list/${_id}/complete`

    - ```typescript
      class ReservedDetail {
        _id: string;
        amount: number;
        pickedUp: number;
      }
      class ShoppingListRequest {
        _id: string;
        totalAmount: number;
        totalPickedUp: number;
        reservedDetails: ReservedDetail[];
      }
      class CompleteShoppingListRequest {
        plannedDate?: Date;
        storage?: string;
        jobType?: string;
        shoppingList: ShoppingListRequest[];
      }
      ```

- **Task (Job) APIs:**

  - `GET /locations?lastSyncedAt={datetime}`
    - ```typescript
      class Location {
        _id!: string;
        fullAddress!: string;
        isActive?: boolean;
        locationOf?: LocationOf[];
      }
      ```
  - `GET /jobs?lastSyncedAt={datetime}`
    - ```typescript
      class Location {
        _id: string;
        fullAddress: string;
      }
      class Job {
        _id: string;
        isDeleted: boolean;
        isActive: boolean;
        identifier: string;
        title: string;
        status: string;
        type: string;
        jobType: string;
        plannedDate: string;
        assignee: string;
        location: Location;
      }
      ```

- **Create Task APIs:**

  - `GET /locations/${locationId}/units`
    - ```typescript
      class UnitOfLocation {
        _id!: string;
        name!: string;
        position!: number;
        parent?: string;
        label?: string;
      }
      ```
  - `GET /job-templates/general`
    - ```typescript
      class Point {
        _id!: string;
        description!: string;
        position!: number;
      }
      class GeneralTemplate {
        _id!: string;
        name!: string;
        points!: Point[];
      }
      ```
  - `POST /jobs`
    - ```typescript
      class Point {
        position: number;
        description: string;
      }
      class UnitRequest {
        _id: string;
        points: Point[];
      }
      class CreateTaskRequest {
        title: string;
        plannedDate: Date;
        instructions: string;
        location: string;
        jobType: "maintenance" | "cleaning";
        estimatedHours: number;
        units: UnitRequest[];
      }
      ```

- **Task Detail APIs:**

  - `GET /jobs/${id}`

    - ```typescript
      class TaskDetail {
        _id!: string;
        jobType!: JobType;
        title!: string;
        status!: TaskStatus;
        units!: Omit<UnitOfLocation, "position">[];
        assignee!: Employee;
        employees!: Employee[];
        planner!: Employee;
        plannedDate!: string;
        type!: InspectionType;
        reportType?: ReportType;
        equipments!: Equipment[];
        identifier!: string;
        instructions?: string;
        location!: Location;
        images?: string[];
        feedbacks?: string;
      }
      ```

  - `GET /inventory-management/reserved/inspection/${id}/needed-article`

    - ```typescript
      class NeededArticle {
        _id!: string;
        category!: Category;
        identifier!: string;
        description!: string;
        totalAmount!: number;
        totalPickedUp!: number;
        completed!: boolean;
      }
      ```

- **Start Job APIs:**

  - `PATCH /jobs/${id}/in_progress`

- **Perform Job APIs:**

  - `GET /jobs/${id}/review`
    - ```typescript
      class Parent {
        _id!: string;
        name!: string;
        position?: number;
      }
      enum JobPointStatus {
        NONE = "none",
        GREEN = "green",
        YELLOW = "yellow",
        RED = "red",
      }
      class FlowUpAction {
        description!: string;
        images!: string[];
        type?: JobType;
      }
      class CostLines {
        position?: number;
        description!: string;
        price!: number;
        quantity!: number;
        totalPrice!: number;
      }
      class JobPoint {
        _id!: string;
        status!: JobPointStatus;
        position!: number;
        description!: string;
        notes?: string;
        images!: string[];
        actions?: FlowUpAction[];
        costLines?: CostLines[];
      }
      class CheckInOut {
        resident!: string;
        reservation!: string;
        checked!: boolean;
      }
      class Reservation {
        bed!: string;
        lastCheckIn!: CheckInOut;
        lastCheckOut!: CheckInOut;
      }
      class JobUnit {
        _id!: string;
        name!: string;
        position!: number;
        parent?: Parent;
        points!: JobPoint[];
        reservations!: Reservation[];
      }
      class JobReview {
        units: JobUnit[];
      }
      ```
  - `POST /upload`
    - ```header
      Content-Type: multipart/form-data
      ```
    - ```typescript
      class UploadRequest {
        folderPath: 'images',
        files: {
          fileName: string;
          base64: string;
        }[];
      }
      ```
  - `PUT /jobs/${id}`
    - ```typescript
      class Action {
        description: string;
        images: string[];
        type: string;
      }
      class CostLine {
        position: number;
        description: string;
        price: number;
        quantity: number;
      }
      class Reservation {
        reservation: string;
        type: string;
        checked: boolean;
      }
      class Point {
        _id: string;
        status: string;
        notes: string;
        images: string[];
        actions: Action[];
        costLines: CostLine[];
      }
      class Unit {
        _id: string;
        points: Point[];
        reservations: Reservation[];
      }
      class JobReviewRequest {
        units: Unit[];
      }
      ```

- **Article APIs:**

  - `GET /inventory-management/storage?pageSize=-1&isActive=true`
    - ```typescript
      enum StorageType {
        VAN = "Van",
        WAREHOUSE = "Warehouse",
      }
      class InventoryStorage {
        _id!: string;
        type!: StorageType;
        identifier!: string;
        description!: string;
        createdAt!: string;
        updatedAt!: string;
      }
      ```
  - `GET /inventory-management/reserved/inspection/${id}/used-article`
    - ```typescript
      class ArticleJob {
        usedArticles!: UsedArticle[];
        returnedArticles!: ReturnedBrokenArticle[];
        brokenArticles!: ReturnedBrokenArticle[];
        additionalUsedArticles!: AdditionalArticle[];
        additionalReturnedArticles!: AdditionalArticle[];
        additionalBrokenArticles!: AdditionalArticle[];
      }
      ```
  - `PUT /inventory-management/reserved/inspection/${id}/used-article`
    - ```typescript
      class UsedArticle {
        _id: string;
        used: number;
      }
      class Article {
        _id: string;
        article: string;
        amount: number;
        reason: string;
      }
      class ReturnedArticle {
        _id: string;
        order: number;
        storage: string;
        articles: Article[];
      }
      class BrokenArticle {
        _id: string;
        order: number;
        articles: Article[];
      }
      class AdditionalArticle {
        _id: string;
        order: number;
        storage: string;
        articles: Article[];
      }
      class ArticleJob {
        usedArticles: UsedArticle[];
        returnedArticles: ReturnedArticle[];
        brokenArticles: BrokenArticle[];
        additionalUsedArticles: AdditionalArticle[];
        additionalReturnedArticles: AdditionalArticle[];
        additionalBrokenArticles: AdditionalArticle[];
      }
      ```

- **Summary APIs:**

  - `GET /jobs/${id}/summary`
    - ```typescript
      class Equipment {
        _id!: string;
        description!: string;
        type!: string;
      }
      class Employee {
        _id!: string;
        employee?: string;
        displayName!: string;
        estimatedHours?: number;
        actualHours?: number;
      }
      class SummaryUnit {
        _id!: string;
        name!: string;
        parent?: Parent;
        points!: SummaryPoint[];
      }
      class SummaryPoint {
        _id!: string;
        actions!: FlowUpAction[];
        costLines!: CostLines[];
      }
      class SummaryJob {
        _id!: string;
        equipments!: Equipment[];
        employees!: Employee;
        units!: SummaryUnit[];
        totalGreenResult!: number;
        totalYellowResult!: number;
        totalRedResult!: number;
      }
      ```

- **Save actual hours coworker APIs:**

  - `POST /jobs/${id}/sync-data`
    - ```typescript
      class ActualHours {
        actualHours: number;
      }
      ```

- **Read job APIs:**

  - `GET /jobs/${id}/ready`
    - ```typescript
      class ReadyJobRequest {
        units: Unit[];
        actualHours: number;
        feedbacks: string;
        fuaDescriptions: string;
      }
      ```

## Infrastructure Requirements

1. **Development & Testing Environments:** Separate environments for development, staging/QA, and production.

# Development Roadmap

## MVP Requirements

The Minimum Viable Product (MVP) will focus on enabling a field employee to authenticate, view their core daily work, perform essential job tasks, manage related data comprehensively, and report completion, including advanced functionalities and special case handling from the outset.

**Login Restriction:** Only users with at least one `RoleMobile` (INSPECTOR, MECHANIC, CLEANER, ADMINISTRATOR) assigned to their profile are permitted to log in to the HomEE app.

1. **Authentication (Core & Advanced):**
   - Username & Password login.
   - Initial password reset flow for accounts that do not change password after 6 months.
   - Secure session management.
   - Multi-Tenant Authentication flow.
2. **Home Screen (Basic & Interactive):**
   - Display "Welcome" title.
   - Week selector to choose a day.
   - Display Task summary for the selected day (list of jobs, navigation to job detail).
   - Toggle to switch to Shopping List summary view for the selected day.
   - Interactive shopping list summary (expand picked-up items).
3. **Task List & Viewing (Core & Advanced):**
   - Display list of assigned tasks (default sort: newest).
   - Basic filtering by date.
   - Advanced filtering (location, type).
   - Completed jobs toggle.
   - Navigate to Job Detail screens (General Info, Location Info, Needed Articles - read-only display initially, then editable as per creation/execution features).
4. **Shopping List Management (Full):**
   - Filtering (date, warehouse, job type).
   - Detail screen for job allocation.
   - Confirmation workflow.
   - View consolidated shopping lists.
   - Input quantities of articles picked up.
   - Confirm completion of picking up articles.
   - Overview and detail screen for allocating picked-up items to specific jobs.
5. **Create New Task (Maintenance/Cleaning - Full Logic):**
   - Allow authorized users (Mechanics/Cleaners) to create new Maintenance or Cleaning tasks.
   - Step 1: General Info (title, location, unit, date, estimated hours, instruction).
   - Step 2: Template & Points, including implementation of complex rules for template application and point management.
6. **Perform Job (Core Loop & Advanced Features):**
   - Access "Perform Job" screen from "Needed Articles."
   - Display progress bar (points completed/total).
   - Select Unit/Sub-unit.
   - For each Unit/Sub-unit will have at least Inspection Point.
   - For each Inspection Point:
     - Display Title.
     - Allow selection of one Review Code (Green/Orange/Red).
     - Allow adding a textual Description/Finding.
     - Allow taking/attaching at least one Photo (maximum 8 photos).
     - "Cost to bill" functionality (optiona)l, user can add multiple "Cost to bill", each item have:
       - Allow to input Description
       - Required to input total quatity (default is 1)
       - Required to input cost for only 1 amount
       - Display total cost field (readonly), total cost = total quatity \* cost
     - "Follow up actions" functionality (optiona)l, user can only add one "Follow up actions".
       - Required to input Description
       - Optional, allow taking/attaching at least one Photo (maximum 8 photos).
   - "Save" button to save progress locally.
7. **Article Management (Full - Used, Returned, Broken, Additional):**
   - "Used Article" screen:
     - List articles allocated to the job.
     - Input "Used" quantity (validation: >=0, <=Available).
     - Display "Unused" quantity.
   - Manage Returned articles.
     - **Autofill Logic:** When save in "Used article", app will navigate to "Returned" screen, the system can autofill the "Returned" amount with the full unused quantity by default (user can edit). For broken articles, this will remove article where article is edited in "Used article" from "Broken" screen.
   - Manage Broken articles.
     - **Autofill Logic:** When save in "Returned article", app will navigate to "Broken" screen, the system can autofill the broken amount so that the sum matches the available unused quantity.
   - Manage Additional used/returned/broken articles from Van/Location.
8. **Job Summary & Submission (Core & Detailed):**
   - "Summary" screen:
     - Display basic job result summary (count of Green/Orange/Red points).
     - Display Worker, Estimated Hours.
     - Allow input of "Actual Hours" (required).
     - Display detailed article summaries (used, returned, broken).
     - Display expenditures.
     - Display follow-up actions.
     - Display detailed financial data (requires backend support/logic).
   - "Submit" button: Marks job as "ready" locally, prepares for sync. Navigates to Task List.
9. **Offline Capabilities (Robust):**
   - View cached job details (if accessed online previously).
   - Save "Perform Job" progress, all article management data (job-allocated and additional), and new task creation data locally when offline.
   - Robust data synchronization when connection is restored, including improved sync logic and attempts to support saving "additional articles" offline (if feasible through caching).
   - Visual indicator for offline status.
10. **Profile Management (Full):**
    - View basic profile information.
    - Edit profile details.
    - Change password.
    - Manage app settings (default home tab, photo storage switch).
    - "Logout" functionality.
11. Roles & Permission: MISSING
12. **Special Case Handling:**
    - Handling Rejected Jobs: Workflow for viewing and restarting rejected jobs with article editing limitations.
    - Co-worker Role: Implement specific views and restricted permissions for co-workers.
13. **UI/UX Refinements:**
    - Incorporate initial UI/UX refinements based on early feedback or best practices.

# Logical Dependency Chain

1. **Setup project & navigation:** Initialize the React Native project and install navigation dependencies (React Navigation, required peer dependencies).
2. **Foundation & Authentication (Must-Have First):**
   - **App Shell & Basic Navigation:** Establish header, bottom navigation structure.
   - **Authentication Module:** Username/Password login, session management, API integration with HomEE portal for user validation. **Login is restricted to users who have at least one `RoleMobile` (INSPECTOR, MECHANIC, CLEANER, ADMINISTRATOR) assigned.** This is the entry point.
   - **User Profile (Minimal):** Display basic user info (read-only from portal), Logout. Essential for user context.
3. **Core Data Display (Getting to Visible Front-End Quickly):**
   - **Task List Screen:** API to fetch assigned jobs. Display job list (title, identifier, location). Basic date filtering. This provides the primary list of work.
   - **Job Detail Screens (Read-Only):** General Info, Location Info, Needed Articles. Allows users to see what a job entails.
   - **Home Screen (Basic):** Display tasks for a selected day (from week selector). Simple toggle to a placeholder for shopping list. This is the main landing/overview.
4. **Core Job Interaction - Performing a Job (MVP Usability):**
   - **Perform Job Screen (MVP):**
     - Select Unit/Sub-unit.
     - Display Inspection Points for the selected unit.
     - Allow selection of Review Code (Green/Orange/Red).
     - Allow basic text Description/Finding.
     - Allow attaching one Photo per point.
     - "Save" progress locally.
   - **Used Articles Screen (MVP - Job Allocated):** Document usage of articles pre-assigned to the job.
   - **Summary Screen (MVP):** Display aggregated data (point counts), allow input of Actual Hours.
   - **Submit Job Functionality:** API call to mark job as "ready" or "completed" on backend.
5. **Shopping List (MVP - Basic Interaction):**
   - **Shopping List Overview (MVP):** Display articles for a selected date. Allow input of "Picked Up" quantity for job-allocated articles.
6. **Offline Capabilities (MVP - Foundational):**
   - **Local Data Storage:** Setup local DB.
   - **Caching:** Cache job details when viewed online.
   - **Local Save:** Save "Perform Job" progress and "Used Article" (job-allocated) data when offline.
   - **Basic Sync:** Attempt to sync pending local data to server upon reconnection.
   - **Offline Indicator:** Visual cue for network status.
7. **Expanding Core Features (Iterative Build-Upon):**
   - **Full Shopping List Management:** Implement detail screen for allocation, confirmation workflow, advanced filtering. (Depends on MVP Shopping List).
   - **Create New Task (Maintenance/Cleaning):**
     - Step 1: General Info. (Depends on Location/Unit master data).
     - Step 2: Point Management (start simple, then add complex template logic).
   - **Full Article Management:** Returned, Broken, Additional from Van/Location. (Depends on MVP Used Articles & master data for Vans/Articles). This has offline complexities that need careful consideration.
   - **Advanced Perform Job Features:** Cost to Bill, Follow-up Actions. (Depends on MVP Perform Job).
   - **Full Profile Management:** Editing details, password change, app settings. (Depends on MVP Profile & Auth).
8. **Advanced & Supporting Features:**
   - **Multi-Tenant Authentication:** (Depends on foundational Auth).
   - **Full Offline Capabilities:** Address "additional articles" offline saving, robust sync conflict resolution. (Depends on MVP Offline & Full Article Management).
   - **Special Case Handling:** Rejected Jobs, Co-worker views. (Depends on core job flow & roles).
   - **Notification System:** (Depends on user roles & backend event triggers).

This order prioritizes getting a functional, albeit basic, end-to-end flow for performing a job into the user's hands quickly, then iteratively adding depth and breadth to the features.

# Risks and Mitigations

1. **Technical Challenges:**
   - **Risk: Complex Template Logic for Task Creation:** The specified logic for applying "inspection templates" and "general templates" during task creation (Maintenance/Cleaning) is highly intricate, reactive, and potentially confusing for users if not implemented perfectly. It's prone to bugs and difficult UI.
     - **Mitigation:**
       - **MVP:** Implement a simplified version for "Create Task" Step 2, perhaps allowing manual point addition without complex template interactions initially.
       - **Phased Rollout:** Introduce advanced template logic in a later phase after core functionalities are stable.
       - **UX Prototyping & Testing:** Conduct thorough UX testing with target users for the template interaction flow before full development.
       - **Clear Documentation:** Use flowcharts/state diagrams for development and provide clear in-app guidance for users if complex logic is retained.
       - **Clarify Terminology:** Ensure template names ("inspection template" vs. "general template") are consistent and clear for Maintenance/Cleaning job creation.
   - **Risk: Offline Functionality for "Additional Articles":** The current specification states that saving "Additional Used/Returned/Broken Articles" (from Van/Location) will fail offline. This is a significant usability issue for field workers in poor connectivity areas.
     - **Mitigation:**
       - **Investigate Aggressive Caching:** Explore pre-caching necessary master data (Van lists, articles within vans, common location articles) to enable offline selection and validation.
       - **Temporary Offline Capture:** If full validation is impossible offline, allow users to capture these details temporarily (e.g., free-text for article, quantity) and flag them for review/formalization when back online.
       - **Prioritize:** This is a critical usability feature; allocate resources to find a workable offline solution.
   - **Risk: Data Synchronization Complexity & Conflict Resolution:** Ensuring data integrity with offline work, multiple potential sync points, and eventual consistency with the HomEE portal can be challenging.
     - **Mitigation:**
       - **Robust API Design:** Clearly defined, idempotent APIs for data submission.
       - **Clear Sync Rules:** Establish rules for conflict resolution (e.g., last write wins from mobile, server authoritative for certain data, user prompted for manual resolution in rare cases).
       - **Thorough Testing:** Test various offline/online transition scenarios, concurrent data changes (if portal allows admin edits while mobile is offline), and large data syncs.
       - **Incremental Sync:** Design sync to handle only changed data.
2. **Figuring out the MVP that we can build upon:**
   - **Risk: Scope Creep for MVP:** Tendency to include too many features in the initial version, delaying release and feedback.
     - **Mitigation:**
       - **Strict Adherence to MVP:** Follow the defined MVP requirements focusing on the core user journey: login -\> view task -\> perform basic job steps -\> submit.
       - **Early User Feedback:** Get the MVP to a small group of representative users as quickly as possible to validate core assumptions and gather feedback for subsequent iterations.
       - **Prioritization Framework:** Use a clear framework (e.g., MoSCoW) if new features are proposed for MVP.
3. **User Adoption & Usability:**
   - **Risk: Field Staff Resistance or Difficulty Using the App:** If the app is not intuitive, is unreliable, or doesn't clearly solve user pain points, adoption will be low.
     - **Mitigation:**
       - **User-Centered Design:** Involve target users (field employees) in the design and testing process (e.g., UAT for MVP and major releases).
       - **Thorough Training:** Provide comprehensive training materials and sessions.
       - **Iterative Improvement:** Collect user feedback continuously and incorporate it into subsequent development cycles.
       - **Focus on Value:** Ensure each feature clearly benefits the end-user and simplifies their work.
       - **Reliability:** Prioritize stability and reliability, especially for offline functionality.

# Appendix

## Supporting Tables from Original PRD

_(These tables would be reproduced here from the original detailed PRD for reference. Examples include:)_

- Table 2.1: User Roles and Key App Permissions
- Table 4.1: Password Policy Requirements
- Table 11.1: Article Flow Summary (Conceptual)
- Table 13.1: Offline Data Handling and Synchronization Rules

**Table 2.1: User Roles and Key App Permissions**

| Role                       | Key App Permissions & Characteristics                                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Employee (Main Worker)** | - Primary user of the app for field tasks.                                                                                            |
|                            | - Manages assigned Shopping Lists (view, filter, input picked-up, confirm).                                                           |
|                            | - Manages assigned Tasks/Jobs (view list, filter, access details, perform job, manage used/returned/broken articles, submit summary). |
|                            | - Can be a "Mechanic" or "Cleaner" to create new Maintenance/Cleaning tasks (username auto-filled, non-editable as creator).          |
|                            | - Can be an "Inspector," "Mechanic," or "Cleaner" who must select review codes during job performance.                                |
|                            | - Manages own profile (details, password, settings).                                                                                  |
|                            |                                                                                                                                       |
| **Co-worker**              | - Can access jobs they are assigned to as a co-worker.                                                                                |
|                            | - Can view job details, perform job page, and summary page.                                                                           |
|                            | - Cannot start the job.                                                                                                               |
|                            | - Can edit their "Actual Hours" on the summary page.                                                                                  |
|                            | - Cannot view used/returned/broken articles.                                                                                          |
|                            |                                                                                                                                       |

---

**Table 4.1: Password Policy Requirements**

| Policy Item                     | Requirement                                                     |
| ------------------------------- | --------------------------------------------------------------- |
| **New Password (Reset/Update)** | Required field.                                                 |
|                                 | Minimum 8 characters.                                           |
|                                 | Must contain at least 1 uppercase letter.                       |
|                                 | Must contain at least 1 lowercase letter.                       |
|                                 | Must contain at least 1 number.                                 |
|                                 | Must contain at least 1 special character.                      |
| **Confirm New Password**        | Required field.                                                 |
|                                 | Must be the same as the New Password.                           |
| **Update Password Specific**    | New password must be different from the current (old) password. |

---

**Table 11.1: Article Flow Summary (Conceptual)**

| Stage / Action                            | Article State / Information Tracked                                          | Key User Actions / System Logic                                                                                                                                                                                        |
| ----------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Job Assignment**                     | Articles "Reserved" for a specific job.                                      | System (via HomEE Portal) assigns articles needed for a job. Displayed in "Needed Articles" in Job Detail.                                                                                                             |
| **2. Shopping List Overview**             | "Reserved" quantity displayed.                                               | User views sum of reserved articles from warehouse(s). User inputs "Picked up" quantity.                                                                                                                               |
|                                           | "Picked up" quantity (input field).                                          | "Picked up" must not be > "Ready for pick up" (reserved).                                                                                                                                                              |
| **3. Shopping List Detail**               | Allocation of "Picked up" quantity to specific jobs.                         | User clicks an article on overview; system navigates to detail screen to show jobs needing this article.**System autofills the picked-up amount from overview into the detail screen for allocation (user can edit).** |
|                                           | Sum of allocated "Picked up" must match total "Picked up" on overview.       | Save disabled if total is incorrect.                                                                                                                                                                                   |
| **4. Performing Job - Used Articles**     |                                                                              |                                                                                                                                                                                                                        |
|                                           | "Used" quantity (input field).                                               | 0 <= "Used" <= "Available."                                                                                                                                                                                            |
|                                           | "Unused" quantity (calculated: Available - Used).                            |                                                                                                                                                                                                                        |
|                                           | "In location" (display of existing articles at location from previous jobs). |                                                                                                                                                                                                                        |
|                                           | Additional Used: From Van (select Van, Article, input Amount).               | 0 < "Amount" <= "Available"**.** Selected Van/Article should not be duplicated in multiple additional sections/same Van.                                                                                               |
| **5. Performing Job - Returned Articles** | From Job: "Available" (Unused from job).                                     | User documents unused articles returned from the job to a Warehouse or Van.**System autofills 'Returned' with full unused by default (user can edit).**                                                                |
|                                           | From Job: "Amount" returned (input).                                         | "Returned Amount" + "Broken Amount" (from job) must = "Available" (Unused from job).**System autofills 'Broken' to satisfy this rule if 'Returned' is entered.**                                                       |
|                                           | From Location: "In location" (available at site).                            | User documents articles found at location and returned to Storage.                                                                                                                                                     |
|                                           | From Location: "Amount" returned (input).                                    | 0 < "Amount" <= "Available"                                                                                                                                                                                            |
| **6. Performing Job - Broken Articles**   | From Job: "Available" (Unused from job).                                     | User documents articles broken from the job's stock.                                                                                                                                                                   |
|                                           | From Job: "Amount" broken (input).                                           | "Returned Amount" (from job) + "Broken Amount" (from job) must = "Available" (Unused from job).**System autofills 'Broken' if 'Returned' is entered and vice versa.**                                                  |
|                                           | From Job: "Reason" (optional input).                                         |                                                                                                                                                                                                                        |
|                                           | From Location: "In location" (available at site).                            | User documents articles found broken at the location.                                                                                                                                                                  |
|                                           | From Location: "Amount" broken (input).                                      | 0 < "Amount" <= "In location."                                                                                                                                                                                         |
|                                           | From Location: "Reason" (optional input).                                    | Single section for adding/removing broken articles from location.                                                                                                                                                      |
| **7. Job Completion**                     | Article states (Used, Returned, Broken) are finalized.                       | Counts contribute to job summary. System updates inventory on portal once job is completed/closed.                                                                                                                     |

---

**Table 13.1: Offline Data Handling and Synchronization Rules**

| Feature/Action                    | Offline Behavior                                                                                         | Data Storage         | Online Synchronization                                                                  |
| --------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------- | --------------------------------------------------------------------------------------- |
| **Network Status Indicator**      | Icon turns red.                                                                                          | N/A                  | Icon turns green.                                                                       |
| **Tasks Page (Job List)**         | Works for viewing cached list.                                                                           | Local Cache          | Updates list on refresh.                                                                |
| - Create New Task                 | Not possible.                                                                                            | N/A                  | N/A (action requires online)                                                            |
| - Refresh Task List               | Not possible.                                                                                            | N/A                  | N/A (action requires online)                                                            |
| **Accessing Task/Job Details**    | Can access if task/job detail page was accessed before (cached). Else, "You are offline..." message.     | Local Cache          | Fetches latest data from server.                                                        |
| **Perform Job Page**              | Can access if page was accessed before. Else, "You are offline..." message. Data entry enabled.          | Local DB             | All saved data synced to server.                                                        |
| - Save Button                     | "Save successfully" message. Data saved to local DB.                                                     | Local DB             | Data from local DB synced.                                                              |
| **Used Article Page**             | Can access if page was accessed before. Else, "You are offline..." message. Data entry for job articles. | Local DB             | All saved data synced to server.                                                        |
| - Save (No Additional Articles)   | "Save successfully" message. Data saved to local DB.                                                     | Local DB             | Data from local DB synced.                                                              |
| - Save (With Additional Articles) | "Save failed. Please turn on your internet connection" message. No save of additional articles.          | No Save (Additional) | N/A (action requires online for additional)                                             |
| **Returned Article Page**         | Can access if page was accessed before. Else, "You are offline..." message. Data entry for job articles. | Local DB             | All saved data synced to server.                                                        |
| - Save (No Additional Returns)    | "Save successfully" message. Data saved to local DB.                                                     | Local DB             | Data from local DB synced.                                                              |
| - Save (With Additional Returns)  | "Save failed. Please turn on your internet connection" message. No save of additional returns.           | No Save (Additional) | N/A (action requires online for additional)                                             |
| **Broken Article Page**           | Can access if page was accessed before. Else, "You are offline..." message. Data entry for job articles. | Local DB             | All saved data synced to server.                                                        |
| - Save (No Additional Broken)     | "Save successfully" message. Data saved to local DB.                                                     | Local DB             | Data from local DB synced.                                                              |
| - Save (With Additional Broken)   | "Save failed. Please turn on your internet connection" message. No save of additional broken.            | No Save (Additional) | N/A (action requires online for additional)                                             |
| **Summary Page**                  | Can access if page was accessed before. Else, "You are offline..." message.                              | Local DB (inputs)    | All saved data synced to server.                                                        |
| - Submit Button                   | "Ready job successfully" message. Data saved to local DB. Navigates to Task List.                        | Local DB             | Data from local DB synced; job status updated on server.                                |
| **General Sync Trigger**          | N/A                                                                                                      | Local DB             | All data in local DB will be synced to the server when internet connection is restored. |
| **Automatic Sync**                | N/A                                                                                                      | Local DB             | Sync action will be performed automatically daily (e.g., every 30 minutes) when online. |

---

## Areas Requiring Further Technical Specification

- **Notification System Details:** Specific triggers for notifications, content of notifications, and user interaction with notifications.
- **Conflict Resolution Strategy for Data Sync:** Detailed rules for handling data conflicts during synchronization, especially if data can be modified both on mobile (offline) and on the portal simultaneously.
- **Security Specifications:** Detailed security measures for data at rest (on device and server) and in transit, including encryption standards, secure key management, and vulnerability assessments.

## Technical Specifications Summary

- Platform: React Native CLI
- Target OS: Android, iOS
- Key Libraries:
  - State Management:
    - @reduxjs/toolkit
    - react-redux
    - redux-saga
    - zustand
    - redux-persist
    - reselect
  - Networking / API:
    - axios
    - @react-native-community/netinfo
  - React Native Core Enhancements:
    - react-native
    - react-native-safe-area-context
    - react-native-screens
    - react-native-vector-icons
    - react-native-gesture-handler
    - react-native-reanimated
    - react-native-svg
    - react-native-splash-screen
    - react-native-config
    - react-native-device-info
    - react-native-permissions
    - react-native-image-picker
    - react-native-linear-gradient
    - react-native-date-picker
    - react-native-background-fetch
    - @react-native-async-storage/async-storage
  - Navigation:
    - @react-navigation/native
    - @react-navigation/stack
    - @react-navigation/bottom-tabs
  - Form & Validation:
    - react-hook-form
    - @hookform/resolvers
    - yup
  - Internationalization:
    - i18next
    - react-i18next
  - Utilities:
    - lodash
    - @types/lodash
    - moment
    - patch-package
  - UI Components:
    - react-native-actions-sheet
    - react-native-element-dropdown
    - react-native-midnight
    - react-native-toast-message
    - @shopify/flash-list
  - Database / Storage:
    - realm
- Language: TypeScript
- Language App: English, Dutch
- State Management: Redux Toolkit, Redux Persist, Redux Saga
- UI Components: React Native SVG, React Native Vector Icons
- Local Storage: Realm
