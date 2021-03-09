# Cypress

## Directory Structure

Created automatically after installation

- `fixtures` | JSON data for mocking e.g. stub network request
- `integration` | Test Files
- `plugins` | Cypress Plugin
- `support` | Reusable code - e.g. utils functions, custom commands

## Interacting with Elements

- **Parent**
  - Start a chain
  - e.g. `cy.visit()`, `cy.get()`, `cy.request()`, `cy.exec()`, `cy.route()`
- **Child**
  - Chained off parent/another child
  - e.g. `cy.get('[data-cy=username').click()`
- **Dual**
  - Start a chain or be chained off
  - Depends on the test
  - e.g. `cy.container()`, `cy.screenshot()`, `cy.scrollTo()`, `cy.wait()`

### Selecting Elements

```jsx
return (
  <input
    classNames="form-control"
    name="username"
    type="email"
    data-cy="username"
    placeholder="Email"
    value={email}
    onChange={this.changeEmail}
  />
);
```

```js
cy.get("form-control form-control-lg").click(); // Style class can change
cy.get("input").click(); // A lot of input tag in page
cy.get("[name=username]").click(); // Good but still couple to HTML attribute
cy.contains("Username").click(); // Couple to text
cy.get("[data-cy=username]").click(); // Best - Provide Unique ID
```

## Test File

### Assertions

```js
/// <reference types="Cypress" />

describe("Register", () => {
  it("register a new user", () => {
    const username = "visitor";
    const email = "visitor@example.com";
    const password = "password";

    cy.visit("http://localhost:4100");
    cy.contains("a.nav-link", "Sign up").click();

    // Correctly redirect to register page
    cy.location("pathname").should("equal", "/register");

    cy.get("[data-cy=username").type(username);
    cy.get("[data-cy=email").type(email);
    cy.get("[data-cy=password").type(password);

    cy.get("form").submit();

    // Redirected back to home page and profile section is shown
    cy.location("pathname").should("equal", "/");
    cy.get("[data-cy-profile]").should("be.visible");

    cy.contains("a.nav-link", "Your Feed").should(
      "have.class",
      "nav-link active"
    );
    cy.contains("a.nav-link", "Global Feed").should(
      "not.have.class",
      "nav-link active"
    );
  });
});
```

### Hooks, Plugins, Support

```js
/// <reference types="Cypress" />

describe("Create New Post", () => {
  beforeEach(() => {
    // Custom commands defined in plugins and support
    cy.task("cleanDatabase");
    cy.registerUserIfNeeded();
    cy.login();
  });

  it("write a new post", () => {
    // Do some assertions
  });
});
```

### Aliases

Don't create state changing aliases that are deep in chain of command

```js
/// <reference types="Cypress" />

describe("Create New Post", () => {
  beforeEach(() => {
    cy.get("[data-cy=new-post]").click().as("ClickOnNewPost");
  });

  it("write a new post", () => {
    cy.get("@ClickOnNewPost");
  });

  it("write another post", () => {
    cy.get("@ClickOnNewPost"); // Reuse across tests
  });
});
```
