# Integration Testing Note Repository

## What is Integration Testing?
- Integration Testing focuses on checking data communication amongst modules in a system.
    - This is opposed to Unit Testing which focuses on the functionality of a specific module.
- Other names:
    - I&T (Integration and Testing)
    - String Testing
    - Thread Testing
- Focuses mainly on the interfaces & flow of data/information between the modules.

- Even if all unit tests pass a system can still produce errors when the different modules 'talk' to each other.

### Integration defects can arise for various reasons
- A module is designed by an dev whose programming logic differs from other programmers. 
    - Integration Testing verifies that the different modules are able to work with each other.
- When a module gets integrated into a system the client requirements may have changed. 
    - The new requirements may not be unit tested and therefore integration testing will become necessary.
- The module itself might work the but its interface may have errors.
- External hardware interfaces may be erroneous
- Inadequate exception handling could cause issues.

## Integration Testing Strategies
- Big Bang
- Incremental:
    - Top Down
    - Bottom up 
    - Sandwich

### Big Bang Testing
- All modules are completed then integration testing begins.
    - Advantages
        - Works well with smaller systems.
    - Disadvantages
        - Difficult to locate faults
        - Prone to missing key interfaces
        - Can cause backups in the development cycle.  
            - If 1 module is completed before another the dev who built module 1 has nothing to do till all other modules are built
        - Reduces the ability to prioritize high-risk modules over others.

### Incremental Testing
- As modules that are related to each other are completed they get tested with each other.
    - As more modules get built the more you add to the testing
- There are 2 main types of Incremental testing
    - Bottom Up
    - Top Down

### Stub vs Driver
- These are dummy programs that act as substitutes for the missing models needed for the module to work.
    - They don't implement the entire programming logic of the module but simulates the data.
- Stub - Is called by the Module Under Test
- Driver - Calls the Module to be tested.
- Top to down - needs stubs
- Bottom up - needs drivers

### Bottom-up Testing
- A strategy where the lower level modules are tested first. 
    - Once tested these modules are used to facilitate the testing of higher level modules.
- Advantages:
    - Locating faults becomes easier
    - No wasted time waiting for models to be built
- Disadvantages: 
    - Critical modules at the top which control the system flow are tested last and may develop defects
    - Early prototyping not possible

### Top-Down Testing
- A strategy that follows the flow of the system.  
- Higher level modules are built and tested first before developing the next layer down.
- Stubs are used for testing if some modules are not ready.
- Advantages:
    - Locating faults becomes easier
    - Can create prototypes at various levels of development
    - Critical modules are tested first
- Disadvantages: 
    - Many Stubs needs to be created (more coding time)
    - Lower level modules have less time to be tested.

### Sandwich Testing
- A combination of Top-down and Bottom-up approaches

## How To I&T:
1. Prepare the Integration Tests Plan
1. Design the Test Scenarios, Cases, and Scripts
1. Executing the test Cases followed by the reporting the defects
1. Tracking & re-testing defects
1. Steps 3-4 till Integration is complete.

## I&T Test Plans:
- Methods/Approaches to testing
- Scope and Out of Scope items of the test
- Roles and Responsibilities
- Pre-requisite for I&T
- Testing Environment
- Risk and Mitigation Plans

## Entry and Exit Criteria
- Entry:
    - Unit Tested Components/Modules
    - All High Prioritized bugs fixed and closed
    - All Modules to be completed and integrated successfully
    - Integration tests Plans, test cases ans scenarios documented.
    - Required Test Environment setup
- Exit:
    - Successful Testing of integrated SUT
    - Executed Test Cases are documented
    - All High priority bugs are fixed and closed
    - Technical documents completed and submitted.

## Best Practices/Guidlines for I&T
1. Determine and define the Integration Test Strategy to be used.
1. Study the architectural design of the system and identify the Critical Modules. (These are your priority)
1. Obtain the interface designs from the Architectural team and create test cases to verify all the interfaces. 
1. After the test cases, it's the test data which plays the critical role.
1. Have mock data prepared prior to execution. Don't create data while executing the test cases.

## Tips and Tricks
- Since Integration Tests take more time to setup it is good to use Equivalence partitioning
    - Equivalence Partitioning:
        - Grouping cases together in to equivalent partitions.
        - If 1 item in the partition passes then all items in the partition will pass
        - If 1 item in the partition fails then all items in the partition wil fail.