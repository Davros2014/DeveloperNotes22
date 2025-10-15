
## **Front End (Nuxt 3, Vue, Tailwind, etc.)**

- **UI Components:**  
    The front end is built with Vue (Nuxt 3), using components like [AdminCompanyBranchTextForm.vue](vscode-file://vscode-app/c:/Users/ArajarDW/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) to render forms, tables, modals, etc.
- **State & Form Handling:**  
    Components use local state (`ref`, `reactive`, `computed`) and form libraries (`vee-validate`, `zod`) for validation and user input.
- **API Calls:**  
    Data is fetched from the back end using composables like `useApiQuery`. For example:


	`const { data: branchTextData } = useApiQuery(["branchTextData"], (client) =>`
  `client.getBranchTexts());`
    
    This calls an API endpoint (e.g., `/api/branch-texts`) to get data.
- **User Actions:**  
    When a user submits a form, the component emits an event with the form data:
    
    `emit("submit", formValues);`
    
    The parent component or a composable then sends this data to the back end via an API call (e.g., `client.updateBranchTexts(formValues)`).

## **Back End (API, Database, Business Logic)**

- **API Endpoints:**  
    The back end exposes REST or GraphQL endpoints (e.g., `/api/branch-texts`, `/api/company/:id/branch-texts`) for CRUD operations.
- **Data Handling:**  
    When the front end requests data (GET), the back end queries the database and returns JSON. When the front end submits data (POST/PUT), the back end validates, processes, and updates the database.
- **Business Logic:**  
    The back end enforces rules (e.g., only valid branch texts can be assigned, permissions, etc.).
- **Response:**  
    The back end sends success/error responses, which the front end uses to update the UI (show notifications, update state, etc.).

---

## **How They Work Together (Example Flow)**

1. **User opens the form:**  
    Front end fetches branch texts from the back end and displays them.
2. **User selects branch texts and submits:**  
    Front end validates input, emits a submit event, and sends data to the back end via an API call.
3. **Back end receives data:**  
    Validates and updates the database, then responds with success or error.
4. **Front end updates UI:**  
    Shows confirmation, updates local state, or displays errors based on the response.

---

**Summary:**

- **Front end**: Handles UI, user input, validation, and API calls.
- **Back end**: Handles data storage, business logic, and exposes API endpoints.
- They communicate via HTTP requests (fetch, axios, composables) using JSON data.