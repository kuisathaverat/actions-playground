# GitHub Copilot Instructions

This file contains coding guidelines and principles that GitHub Copilot should follow when suggesting code for this repository.

## Core Principles

### KISS (Keep It Simple, Stupid)
- Prefer simple, straightforward solutions over complex ones
- Avoid over-engineering and unnecessary abstractions
- Write code that is easy to understand and maintain
- Use clear and descriptive names for variables, functions, and classes
- Break down complex problems into smaller, manageable pieces
- Avoid clever tricks that sacrifice readability

### DRY (Don't Repeat Yourself)
- Eliminate code duplication by extracting reusable functions, methods, or modules
- Create shared utilities for common operations
- Use inheritance, composition, or mixins to share behavior
- Avoid copy-pasting code; refactor instead
- Centralize configuration and constants
- Extract repeated patterns into well-named abstractions

### SOLID Principles

#### Single Responsibility Principle (SRP)
- Each class or module should have one, and only one, reason to change
- Functions should do one thing and do it well
- Separate concerns into different classes or modules

#### Open/Closed Principle (OCP)
- Classes should be open for extension but closed for modification
- Use interfaces, abstract classes, and dependency injection
- Design for extensibility without changing existing code

#### Liskov Substitution Principle (LSP)
- Subtypes must be substitutable for their base types
- Derived classes should extend, not replace, base class behavior
- Maintain behavioral contracts in inheritance hierarchies

#### Interface Segregation Principle (ISP)
- Clients should not depend on interfaces they don't use
- Create focused, specific interfaces rather than large, general ones
- Split large interfaces into smaller, more cohesive ones

#### Dependency Inversion Principle (DIP)
- Depend on abstractions, not concretions
- High-level modules should not depend on low-level modules
- Use dependency injection and inversion of control

### YAGNI (You Aren't Gonna Need It)
- Don't implement functionality until it's actually needed
- Avoid speculative generality and premature optimization
- Focus on current requirements, not hypothetical future needs
- Remove unused code, features, and dependencies
- Start simple and add complexity only when necessary

### DDD (Domain-Driven Design)

#### Ubiquitous Language
- Use domain terminology consistently in code
- Align class, method, and variable names with business concepts
- Collaborate with domain experts to understand the business domain

#### Bounded Contexts
- Clearly define boundaries between different parts of the system
- Keep domain models focused and cohesive within their context
- Avoid leaking domain concepts across boundaries

#### Entities and Value Objects
- Use entities for objects with unique identity that changes over time
- Use value objects for immutable objects defined by their attributes
- Ensure value objects are immutable and comparable by value

#### Aggregates
- Group related entities and value objects into aggregates
- Define clear aggregate roots that control access to the aggregate
- Enforce consistency rules within aggregate boundaries

#### Repositories
- Use repositories to abstract data access logic
- Provide collection-like interfaces for retrieving and storing aggregates
- Keep repositories focused on persistence concerns

#### Domain Services
- Create domain services for operations that don't naturally belong to entities or value objects
- Keep services stateless and focused on domain logic
- Avoid putting business logic in application services or controllers

#### Domain Events
- Use domain events to represent significant business occurrences
- Decouple different parts of the system using events
- Maintain a clear audit trail of domain changes

## Implementation Guidelines

1. **Testing**: Write tests that reflect domain concepts and business rules
2. **Documentation**: Document complex domain logic and business rules clearly
3. **Refactoring**: Continuously refactor to maintain these principles
4. **Code Reviews**: Evaluate code changes against these principles
5. **Consistency**: Apply these principles consistently across the codebase

## When Suggesting Code

- Prioritize clarity and maintainability over cleverness
- Question complexity and look for simpler alternatives
- Identify and eliminate duplication
- Ensure each component has a clear, single purpose
- Use domain language that reflects the business context
- Avoid adding features or abstractions that aren't currently needed
- Design for testability and extensibility
