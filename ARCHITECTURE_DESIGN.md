# Android Interview Questions
![Android Interview Questions](images/icon.png)

## Architecture Design

1. #### Why we should use MVP / MVVM architectures?

   * to avoid too much logic code in the UI layer and god activities
   * reusable code that's easier to test
   * avoid duplicated code between common views
   * Easier to maintain
   * we can test logic without using instrumentation tests

2. #### Why the View should be implemented with an interface in MVP?

   * Because we want to decouple the code from the implementation view.
   * We want to abstract the framework used to write our presentation layer, regardless of any external dependency.
   * We want to be able to easily change the implementation of view if needed.
   * We want to follow the SOLID dependency rule to improve unit testability and in order to follow the dependency rule, high-level concepts (such as the presenter implementation) can't depend on low-level details (like the implementation view).

3. #### What’s the use of interfaces in a presenter?

   * following SOLID Dependency inversion principle

4. #### Why do you use dependency injection (DI / Dagger)?

   According to this concept a class should not configure its dependencies statically but should be configured from the outside = Inversion of Control

   * useful for decoupling the whole system
   * allow easier unit testing
   * much easier moving things around and keeping classes small and simple
   * help wiring different elements 

5. #### Explain dependency rule in Clean Architecture.

   In Clean Architecture by Robert C. Martin the dependency rule points strictly from the outermost layer/ring to the innermost.