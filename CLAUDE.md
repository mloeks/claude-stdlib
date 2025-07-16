# My individual preferences for Claude

## Code Comments
- Put a minimal amount of code comments
- Any comment which redundantly expresses what the code is already telling
  should not be put
- Especially don't put any structural comments
- Only put comments if they are adding any expressiveness to the code, i.e.
  explain some code which is otherwise not easy to understand just by reading
  it
- Exceptions are Javadoc comments, which can be redundant at times, but OK to
  put for a complete Javadoc

## Clean Code
- Put a high emphasis on expressive and human-readable code
- Keep methods small, they should just do one thing
- Write self-explanatory code, and use self-explanatory variable and function
  names
- Try to adhere to SOLID principles wherever possible, while keeping some
  pragmatism where meaningful

## Testing
- Follow TDD and write a failing test first which documents the behaviour to be
  implemented
- Then write the code to make that test pass
- Then consider refactoring the code to make it more readable, robust,
  performant etc. (applying the red-green-refactor pattern)
- Prefer integration / service tests expressing behaviour over narrow unit
  tests which are tightly coupled to the implementation.
- Only use unit tests to test edge cases or different input/output using 
  data driven testing methods
- Make sure the tests are readable and repetitive test setups / assertions are properly extracted away into helper methods
  - I prefer to use the terms "given..." in methods for test data / mock setup
  - I prefer to use the terms "verify..." in methods for assertion / mock
    verification
- Make use of data-driven / parameterized tests for testing similar scenarios
  or covering test boundaries whenever possible
- Follow the GIVEN-WHEN-THEN test structure and separate those blocks with
  comments if the language used for the tests does not support it out of the
  box.
- If working with mocks, always make sure to verify all interactions and avoid
  leaking unverified interactions into subsequent tests, this can usually be
  done well in the @AfterEach method

### AssertJ
- Please chain assertions where possible
- Please make use of singleElement()
- Please make use of extracting(...) or similar methods where meaningful

### Mockito
- Please verify mock interactions and make sure no unverified interactions leak
  into subsequent tests
- Exception: don't verify if doing black box testing and/or using fake
  implementations instead of mocks
- Avoid using spy unless absolutely neeed. If you think it's needed, question
  the design under test first

## Code Style
- If no specific coding style has been specified in the context of your
  project, explicitly ask me about it
- Always put a new line at the end of a file

## Working with git
- Write concise commit messages using the recommendations from https://cbea.ms/git-commit/
- Always put a commit message body, explainaing the WHAT and WHY of the changes
  (not the HOW)
- Prefer to commit small and often on feature branches
- If logically meaningful, squash together multiple commits containing the same
  logic into one

