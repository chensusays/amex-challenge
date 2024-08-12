## Production Ready Suggestions
1. Add tests for 
    - React components (storybook, jest)
    - Caching fetch library (mock api calls)
        - I would suggest we choose a vetted technology like Next.js instead of reinventing the wheel here

2. Logging and Error Handling
    - Ensure our codebase gracefully handles errors and doesn't leave users in a unsuable state
    - Detailed logging to help developers pinpoint bugs and other useful information

3. Validating inputs where necessary
    - prevent malicious activity

4. Documentation
    - complex features and models should be accompanied with additional resources such as diagrams and explanations where code comments and self-documenting code do not suffice

5. Maintainability
    - writing code with modularization in minde
    - adhere to team coding standards (naming conventions, simple = better)
    - git commit conventions

6. Optimize TTI (Time To Interactive)
    - page load times
    - heavy css animations
    - long processes (such as api calls)
    - other performance considerations for bundle size

7. Setup CI/CD pipeline for dev, staging, prod builds w/e2e test runners
    - allows for faster and more frequently deployments
    - ensures code quality with automated testing


## Implementation Notes
I decided to proceed with a simple key value store. The key is the url and the value is data that is fetched from the API. I levegered React's hooks to allow for the page to refresh when data updates. And using a simple try catch for fetching data and determine state. All API calls are done asynchronously to remain nonblocking

Possible concerns with this implementation is handling of TTL. If a user visits many urls that request data then we might run out of memory or into performance issues.

