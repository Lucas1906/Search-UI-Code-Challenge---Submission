# Search UI Code Challenge

Welcome to the Search UI coding challenge. You will be asked to build a small
application demonstrating your abilities in React and TypeScript. This challenge
is targeted towards mid to senior level engineers.

## Instructions

1. Clone this repository to your local machine
2. Create a new private repository on GitHub so others can't copy your work
3. Push your local clone up to your private repository while preserving history
4. Create a simple UI that meets the requirements below
5. Add `jeromedane` as a viewer

### Additional Notes

- Use any libraries you like, keeping performance and bundle size in mind
- Use any UI framework you like, but don't spend too much time here
- This challenge should only take an hour or two

## Development

Install dependencies using `npm install`.

Run `npm start` to concurrently start the server and UI in development mode.

Open [http://localhost:3000](http://localhost:3000) to view the UI in the
browser. The page will reload if you make edits.

### API

- The API server is run on port `3001` while the React UI is run on port `3000`
- Your UI can call `/api/data?search=[some-query]` directly since
  the request will be proxied to `http://localhost/api/data?...`
- You will to need access the API on port `3001` if you're testing it directly
  from outside your application (e.g. http://localhost:3001/api/data?search=credit)

## The Problem

> As a consumer I want to research financial topics so I can make informed
> decisions.

## Requirements

```
Scenario: The application shall provide a search form
  Given the user visits the application
  Then a search field is displayed
  And a button is displayed with the text "Search"
```

```
Scenario: The search shall be triggerable by clicking the "Search" button
  Given the user has entered a search query
  When the user clicks the "Search" button
  Then matching search results are displayed
```

```
Scenario: The search shall be triggerable by pressing the Enter key
  Given the user has entered a search query
  And the input field is currently focused
  When the user clicks presses the Enter key on their keyboard
  Then matching search results are displayed
```

```
Scenario: A loading state shall be shown while search results are loading
  Given the user has entered a search query
  When the user submits their search
  Then a loading state is shown until the search results are available
```

```
Scenario: Search results shall show result title and description
  Given a user has performed a search
  When search results are displayed
  Then the title and description of each search result are displayed
```

```
Scenario: Clicking a search result title shall open its URLs in a new tab
  Given search results are displayed
  When a user clicks the title of a search result item
  Then the URL of the search result is opened in a new tab
```

```
Scenario: Search results shall be marked as their content type
  Given search results are displayed
  Then each result is clearly marked as a video, playlist, or blog post
```

```
Scenario: The user shall be informed if no search results match their query
  Given the user has performed a search
  When there are no results matching their search query
  Then the message "There are no results matching your query." is displayed
```

This candidate passed:

Demonstrated good separation of concerns (e.g., search state).
Avoided unnecessary re-rendering.
Utilized a solid understanding of layout using a third-party UI library (e.g., MUI).
Maintained low complexity in most files.
Implemented typescript.
Implemented all requirements.
Separated the search form and search results.
Utilized Tailwind for styling.
Incorporated accessibility properties.
Added e2e test
React query
Added ErrorBoundary
Used React query utility
Suspense Hook
Good separation
These are negatives from candidates that failed:

Not all requirements were implemented, including:
The title should be a link that opens in a new tab.
Not using everything inside a <header> tag.
The component name is overly descriptive and contains unnecessary responsibilities.
Incorrect usage of useEffect for stopping loading.
Using a controlled input instead of a ref, leading to unnecessary re-renders.
The initial state of the result should start as undefined.
Displaying a message for no results when the user hasn't entered any value.
Console warnings present.
UI components have excessive responsibilities.
Fetch requests made inside UI components.
Declared but unused variables.
Unused interfaces and variables.
Table components could be separated into smaller chunks in other files.
Didn’t use an object literal to handle categories.
Failed to manage the loading state at the request level.
Each component has a typo.
Exporting types and interfaces unnecessarily.
Some functions are using (e: any) instead of implementing type safety in event handlers.
Only a single commit.
Used Tailwind but still applied classes in a global CSS file for typography.
Design is not aesthetically pleasing.
Used a single state for the input and loading, which could lead to unnecessary rerenders.
Not all requirements were implemented:
The title should be a link that opens in a new tab.
Using everything inside a <header> tag.
The component name is not very descriptive and contains more responsibilities than necessary.
Incorrect usage of useEffect for stopping loading.
Not using a ref for the input; using a controlled input will cause unnecessary re-renders with every new character inserted.
The initial state of the result should start as undefined.
When the user hasn't entered any value, we see a message saying there are no results for this query, but the user didn't query for anything.
A warning is appearing in the console.
UI components have more responsibilities than necessary.
Adding a fetch request inside a UI component.
Declaring a variable and not using that variable.
Forgetting to delete interfaces and variables that are not used.
Could have separated the Table components into smaller chunks in other files.
Added unnecessary complexity with recoil state management
Increase of bundle size with unnecessary package to resolve the test
Used split function to handle categories
Used spread props in forms
Created a component inside another component
