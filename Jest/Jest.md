# Jest

Install Globally

```
npm i -g jest
```

Install Locally

```
npm i jest
```

Run tests

```
jest
```

```
jest --watch
```

## Jest Globals

- Test Suite - `describe`
- Test Case - `it`

## Test Files

- `__tests__` folder
- `*.spec.js` or `*.test.js`

## Setup and Teardown

- `beforeEach` - runs before each test (e.g. setup databases, mock instances, etc.)
- `beforeAll` - runs once before the first test
- `afterEach` - runs after the last test (e.g. close connections, terminate processes, etc.)
- `afterAll` - runs once after each test

## Skipping and Isolating Tests

- `it.only()`
- `it.skip()`

## Asynchronous Test

```js
it("async", async () => {
  await asyncAction();
});
```

## Snapshot

TagList.spec.js

```jsx
import React from "react";
import TagsList from "./TagsList";
import renderer from "react-test-renderer";

describe("The Tags List", () => {
  it("renders as expected", () => {
    const tree = renderer
      .create(<TagsList tags={["css", "html", "go"]} />)
      .toJSON();

    expect(tree).toMatchSnapshot();
  });
});
```

Update the snapshot

```
jest -u
```