### Clean C++_ Sustainable Software Development Patterns and Best Practices with C++ 17
    + Everything should be made as simple as possible, but not simpler. 
    + Always implement things when you actually need them, never when you just foresee that
you need them.
    + Copy and paste is a design error.
    + Premature optimization is the root of all evil (or at least most of it) in programming.
    + Programs must be written for people to read, and only incidentally for machines to execute.
    + Use simple but descriptive and self-explaining names.
    + Truth can only be found in one place: the code.
    + Code should tell a story and be self-explanatory. Comments must be avoided whenever possible.
    + Any fool can write code that a computer can understand. Good programmers write code that humans can understand.
    + Except for the purpose to try out something quickly, donâ€™t use comments to disable code. there is a version control system!
    + Functions should do one thing. They should do it well. They should do it only.
    + Functions should be pretty small. Ideally 4–5 lines, maximum 12–15 lines, but not more.
    + The name of a function should start with a verb. predicates, that is, statements about an object that can be true or false, should start with “is” or “has.”
    + The name of a function should express its intention/purpose, and not explain how it works.
    + The ideal number of arguments for a function is zero (niladic). Next comes one (monadic),
    followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification — and then shouldn’t be used anyway.
    + Real functions should have as few arguments as possible. one argument is the ideal number. Member functions (methods) of a class often have no arguments. Usually those functions are manipulating the internal state of the object, or they are used to query something from the object.
    + Avoid output arguments at all costs.
    + Pay attention to const correctness. Use const as much as possible, and choose always a proper declaration of
      variables or objects as mutable or immutable.
    + Apart from a few exceptions, strings in a modern C++ program should be represented by C++ strings taken
      from the standard library.
    + Avoid using printf(), and also other unsafe C-functions, such as sprintf(), puts(), etc.
    + Explicit calls of new and/or delete can be avoided through the following measures:
        •	 Use allocations on the stack wherever possible. Allocations on the stack are simple
        (remember KISS principle discussed in Chapter 3) and safe. It’s impossible to leak
        any of that memory that was allocated on the stack. The resource will be destroyed
        once it goes out of scope. You can even return the object from a function by value,
        thus transferring its contents to the calling function.
        •	 To allocate a resource on the heap, use “make functions.” Use std::make_
        unique<T> or std::make_shared<T> to instantiate the resource and wrap it
        immediately into a manager object that takes care of the resource, a smart pointer.
        •	 Use containers (Standard Library, Boost, or others) wherever appropriate.
        Container manages the storage space for its elements. Instead, in the case of selfdeveloped data structures and sequences, you are forced to implement the entire
        storage management on your own, which can be a complex and error-prone task.
        •	 Provide wrappers for resources from proprietary third-party libraries that
        require a specific memory management (see next section).
    +  Write your classes in a way that you do not need to declare/define neither a destructor, nor a copy/move
       constructor or copy/move assignment operator. Use C++ smart pointers and standard library classes and
       containers for managing resources.
    + The three guiding principles for working with a C++ compiler nowadays are the following:
        •	 Everything that can be done at compile time should also be done at compile time.
        •	 Everything that can be checked at compile time should also be checked at compile time.
        •	 Everything the compiler can know about a program should also be determined by
        the compiler.
    + If it doesn’t obscure the intent of your code, use auto wherever possible!
    + Avoid undefined behavior! It is a bad mistake and ends up with programs that silently misbehave.
    + Create interfaces (apIs) that are strongly typed.
    + If you want to improve the code quality in your organization, replace all your coding guidelines with one     goal: No raw loops!
    + The basic exception-safety guarantee is the guarantee that any piece of code should offer at least. It is also the
      exception-safety level that can be achieved with relatively little implementation effort. This level guarantees
      the following:
      •	 If an exception is thrown during a function or method call, it is ensured that no resources
      are leaked! This guarantee includes memory resources as well as other resources. This
      can be achieved by applying RAII Pattern (see section about RAII and Smart Pointers).
      •	 If an exception is thrown during a function or method call, all invariants are
      preserved.
      •	 If an exception is thrown during a function or method call, there will be no
      corruption of data or memory afterwards, and all objects are in a healthy and
      consistent state. However, it is not guaranteed that the data content is the same as
      before the function or method has been called.
    + Design your code, especially your classes, such that they guarantee at least the basic exception-safety. this
      should always be the default exception-safety level!
    + Throw exceptions only in very exceptional cases. do not misuse exceptions to control the normal program flow.
    + Functions that use pointers or references to base classes must be able to use objects of
      derived classes without knowing it.
    + The Dependency Inversion Principle (DIP) is an object-oriented design principle to decouple software
      modules. The principle states that the basis of an object-oriented design is not the special properties of concrete software modules. Instead, their common features should be consolidated in a shared used abstraction (e.g., an interface). Robert C. Martin a.k.a. “Uncle Bob” formulated the principle as follows:
        A. High-level modules should not depend on low-level modules. Both should depend on abstractions.
        B. Abstractions should not depend on details. Details should depend on abstractions.
    + The principles of good software design still apply, regardless of the programming style you will use!
    + Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live.
    +  If all requirements on our piece of code have been successfully implemented, and we do not find a new unit test that would lead to new production code, we are done!
    + Decisions and patterns give people solutions; principles help them design their own.
    + Decouple components from their required services in such a way that the components do not have to know the names of these services, nor how they have to be procured.
    + Convert the interface of a class into another interface clients expect. Adapter lets classes work together that couldn’t otherwise because of incompatible interfaces.
    + Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it.
    + Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations.
    + Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
    + Provide a unified interface to a set of interfaces in a subsystem. Facade defines a higherlevel interface that makes the subsystem easier to use.
    + If a substitution results in an invalid type or expression, type deduction fails. An invalid type
      or expression is one that would be ill-formed if written using the substituted arguments.
      Only invalid types and expressions in the immediate context of the function type and its
      template parameter types can result in a deduction failure.
    + Implement the copy assignment operator with strong exception safety.