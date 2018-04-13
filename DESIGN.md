# Design Guidelines #

## Table of Contents
- [Class or Struct](#class-or-struct)
- [Preprocessor Directives](#preprocessor-directives)
- [Extensibility](#extensibility)
- [Delegation](#delegation)
- [Deprecation](#deprecation)
- [Logging](#logging)
- [Error Handling](#error-handling)
- [Library Usage](#library-usage)
- [Code Review](#code-review)

## Class or Struct

As of writing, both Classes and Structs can be serialized using the `Serializable` attribute.

**✓ DO** use a struct if instances of the type are:
* immutable value types.
* small, lightweight, and commonly short-lived.
* mostly embedded in other objects.
* generally just used to hold and group information.

**✓ DO** use a class if instances of the type are:
* read by reference.
* encapsulated objects with identity and functionality beyond basic operators.

## Preprocessor Directives

**✓ DO** favor conditional directives `#if`, `#elif`, and `#else` over runtime conditionals.

**✓ DO** group code together by functionality into blocks using the `#region` and `#endregion` directives.

**✓ DO** use the `#warning` directive for unfinished code.

**X AVOID** leaving warnings unattended for a long time.

**X DO NOT** use the `#error` directive to raise errors.

**X DO NOT** use `#define` directives to create toggle symbols that enable or disable functionality. Use the Scripting Define Symbols in the Unity Player Settings instead. 

## Extensibility

**✓ DO** favor building decoupled, extensible, and reusable libraries, utilities, and tools over code tied to application-specific logic if the functionality is commonly used by applications.

**✓ DO** create code that can be imported to any project as-is, without modifications.

**✓ DO** use callbacks, events, delegate methods, and delegate objects to allow application-specific code to interact with reusable code.

**✓ DO** use `Action<...>`, `Func<...>`, or `Expression<...>` types instead of custom delegates.

**✓ DO** favor using `System` events over `UnityEvent` events. This way, you restrict adding and removing of listeners to scripts, making it easier to track for other developers.

## Delegation

As an alternative to C# events and delegates, you may use the delegation mechanism using Interfaces.

**✓ DO** use the delegation mechanism to enforce a relationship between a delegate class and a delegating class.

**✓ DO** favor the delegation mechanism over events or delegate methods when:
* there must be only one delegate for one or more delegated methods, or
* you require the delegate to implement more than one delegated method, and not just a subset of delegated methods.

Example:
```csharp
// Option A: Using Delegation
// Restricted to exactly one handler
// Same instance must handle both events

public interface IConflictHandler
{
  void ResolveConflict(string message);
  void ResolveTransfer(string message)'
}

public class DataSyncer
{
  public IConflictHandler conflictHandler;

  public void ResolveConflict(string message)
  {
    if (conflictHandler != null)
    {
      conflictHandler.ResolveConflict(message);
    }
    else
    {
      ResolveItByYourself();
    }
  }

  public void ResolveTransfer(string message)
  {
    if (conflictHandler != null)
    {
      conflictHandler.ResolveTransfer(message);
    }
    else
    {
      ResolveItByYourself();
    }
  }
}

// Option B: Using Events
// Allows more than one handler using the + and - operators
// Allows a different handler for each event

public class DataSyncer
{
  Action<string> _resolveConflictEventHandler;

  public event Action<string> ResolveConflictEventHandler
  {
    add
    {
      _resolveConflictEventHandler -= value;
      _resolveConflictEventHandler += value;
    }
    remove
    {
      _resolveConflictEventHandler -= value;
    }
  }

  Action<string> _resolveConflictEventHandler;
  public event Action<string> ResolveTransferEventHandler
  {
    add
    {
      _resolveConflictEventHandler -= value;
      _resolveConflictEventHandler += value;
    }
    remove
    {
      _resolveConflictEventHandler -= value;
    }
  }

  public void ResolveConflict(string message)
  {
    if (_resolveConflictEventHandler != null)
    {
      _resolveConflictEventHandler(message);
    }
    else
    {
      ResolveItByYourself();
    }
  }

  public void ResolveTransfer(string message)
  {
    if (_resolveTransferEventHandler != null)
    {
      _resolveTransferEventHandler(message);
    }
    else
    {
      ResolveItByYourself();
    }
  }
}
```
## Deprecation

**✓ DO** deprecate unused code with dependencies using `Obsolete` attribute when refactoring code.

**✓ DO** remove unused code when there are no more dependencies.

## Logging

**✓ DO** avoid nonsensical logging.

**✓ DO** add the ability to disable logging messages.

**✓ DO** keep logging messages if they serve an important purpose in tracking the application's execution.

## Error Handling

**✓ DO** ensure that errors are handled, and exceptions are caught in areas that could cause the application to freeze or crash.

## Library Usage

**✓ DO** favor using the Monstronauts libraries over rolling your own solution.

**✓ DO** add to the Monstronauts libraries if your needs are not met.

**✓ DO** use plugins sparingly, and only when necessary. Replace plugins with your own solutions over time.

## Code Review

**✓ DO** conduct code reviews to eliminate inefficient and ineffective code.

**✓ DO** implement simple hacks only when the situation calls for a quick and dirty temporary solution, such as during the prototyping phase.

**✓ DO** make sure to refactor prototype quality code into production level code.

## Where To Next?
- [Show All Topics](README.md)
- [Naming Guidelines](NAMING.md) 
- [Formatting Guidelines](FORMATTING.md)
- [Design Guidelines](#design-guidelines) (You Are Here)
- [Learning Resources](RESOURCES.md)

<!-- Singletons Or Static Classes -->
