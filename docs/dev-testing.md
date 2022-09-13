---
sidebar_position: 6
---

# Developer Testing

## Quality
- Internal Quality: Code that is loosely coupled, highly cohesive, and is adaptable to change.
- External Quality: Code that does what it is supposed to do.

## Feedback Loops
- Feedback loops allow use to see what is going on with our code asap.
- Developers should intentionally create feedback loops in our code to ensure that our code is doing the right thing.
- Inner Loop: Near instananeous checks that happen in our dev environments.
- Outer Loops: Checks that happen slower on the repo level such as in the build pipeline

## The Levels of Testing
- Static
    - This is an inner loop test.
    - Includes code level protections such as strict types, using an editor config, using a linter, etc.
- Unit
    - Testing functionality of code in isolation from other code.
    - This is an inn loop test.
- Integration
    - This is when we are testing two or more functional units together
    - We want to see how our code integrates with the rest of the code base
    - Usually includes testing against other systems such as a database or network
- E2E
    - Often in the form of a smoke test
    - Before we deploy to prod, we wanto to have some automated or manual test to make sure everything is perfect
    - This is an expensive test, so we want to depend on the other 3 tests as much as possible