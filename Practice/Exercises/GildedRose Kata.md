## 1. Pinning Tests

#### What is a pinning test (a.k.a. characterization test)?

Tests used to lock down existing behaviors. Typically used for making it safer to refactor legacy code.
#### What is safe to refactor without tests?

Generally, it is safe to use your IDEs refactoring tools (e.g. extract method, convert for-loop to foreach, etc.) 

## How do I know my pinning tests are good?

Spend time commenting out pieces of the code under test or changing values. If you do this and run your tests, you should get a test failure for any changes that result in the code's behavior changing.
#### Goals
- Use IDE refactoring tools to 
	- Convert for-loop to foreach
	- Extract processing of individual items into its own method
- Create pinning tests
	- Create XUnit project
	- Write pinning tests to lock down all the known requirements 
- Verify that there are no gaps in your pinning tests by making temporary changes to the code under test and verifying those changes result in failed tests
## 2. Refactoring to Established Patterns

#### What is refactoring?

The art of changing/re-arranging code such that it retains its original behavior. This may be necessary to make the code easier to understand, improve performance, etc.
#### What are design patterns?

Design patterns are known solutions to common problems. They are often used in combination with other patterns to solve problems in a recognizable way to other developers that are familiar with design patterns.
#### Goals
- Add Factory Method and extract item updating functionality into a Command class
- Break out item updating into Strategies using the same interface as the Command for each item type and update the Factory Method to return the appropriate Strategy based on the item name
- Split the updating of the Quality and the SellIn date into separate protected methods
- Push down UpdateQuality and UpdateSellin method into an abstract base class to be implemented by all Item Updaters (i.e. apply the Template Method pattern)
## 3. Refactor Tests

#### When should I refactor tests?

After all major structural changes are complete to the code under test, you should then refactor tests to better accommodate the new architecture.
#### Why should I refactor tests?

Unit tests should generally be 1:1 with the classes they are testing. Pinning tests are typically testing from a higher level of abstraction.
#### Should I delete my pinning tests?

Yes! After the new, refactored tests are complete, you should remove the pinning tests as they are not duplicates and only serve as additional maintenance cost.
#### Goals
- Create unit tests for all of the new classes that were extracted from the original implementation
- Delete old pinning tests

## 4. Use TDD to Add Conjured Item Strategy

#### Why should I write tests first?

Writing tests first helps ensure:
- you are not getting false positives on your new tests
- you only write code that you need (YAGNI)
- your code remains decoupled and cohesive
#### Goals
- Using green-red-refactor, add code to satisfy the requirements for "conjured" items

---


![[GildedRose Requirements]]

---

![[Item Class]]

![[GildedRose Class]]

