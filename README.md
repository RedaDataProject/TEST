**a) The GitHub project you selected**

Project Selected:
- Name: Swag Labs
- GitHub URL: https://github.com/saucelabs/sample-app-web
- Description: Swag Labs is a simple e-commerce web application designed for functional testing purposes. It includes both frontend and backend components, supports user authentication, product browsing, adding items to cart, and checkout flows. This project was selected because it offers enough complexity to demonstrate automated testing of critical user flows while remaining easy to set up locally.

---

**b) How to set up and run your tests**

Setup and Running Tests:

Prerequisites:
- Node.js (version 14+)
- npm (Node package manager)

Steps:
1. Clone this repository:
   git clone <your_repository_url>
2. Navigate into the project folder:
   cd <your_repository_folder>
3. Install dependencies:
   npm install
4. Run the tests in headless mode:
   npx cypress run
5. Alternatively, open the interactive test runner:
   npx cypress open

No changes to the original Swag Labs app source code were necessary. Tests assume the application is running locally at http://localhost:3000.

---

**c) Any assumptions or modifications you made**

Assumptions and Modifications:

- Automated tests were developed using Cypress with TypeScript.
- A custom Cypress command `cy.login()` was created to handle user authentication steps across tests.
- Tests cover three critical user flows: login/logout, adding/removing products from cart, and completing checkout.
- Both positive and negative test cases were included to validate expected behaviors and error handling.
- The Swag Labs app was run locally without any modifications to its source code.
- Tests assume a stable local environment with the app running on port 3000.
- No additional mocks or stubs were introduced.
