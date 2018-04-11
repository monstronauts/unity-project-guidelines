# Naming Guidelines #

The overarching goals of these guidelines are to balance the source code's **consistency**, **readability/clarity**, and **simplicity/brevity**. The reader must understand the purpose and type of each identifier in the source code without having to refer to, or rely on its complete declaration.

There are minor differences between Microsoft's standards, and Monstronauts' standards, so unless otherwise noted below, naming should follow the [Microsoft .NET Naming Standards for C#](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines).

## Table of Contents
- [General Rules](#general-rules)
- [Namespaces](#namespaces)
- [Classes & Structs](#classes--structs)
- [Interfaces](#interfaces)
- [Methods](#methods)
- [Properties](#properties)
- [Events](#events)
- [Delegates](#delegates)
- [Fields](#fields)
- [Parameters](#parameters)
- [Enums](#enums)
- [Attributes](#attributes)
- [Exceptions](#exceptions)
- [String Keys](#string-keys)
- [Prefabs](#prefabs)
- [Scenes](#scenes)
- [Scriptable Objects](#scriptable-objects)
- [Assets & Resources](#assets--resources)

## General Rules

**✓ DO** name source files according to their main classes. In general, avoid having more than one class in one file.

**✓ DO** use PascalCasing for all public member, type, class, method, and namespace names.

**✓ DO** use camelCasing for parameter names and local variables.

**✓ DO** follow the first character's capitalization for acronyms or abbreviations consisting of only 2 characters. Otherwise, use lowercase for the rest of the characters after the first character.

Example:
```csharp
HtmlHelper htmlHelper;
FtpTransfer ftpTransfer;
UIControl uiControl;
```

**✓ DO** choose easily readable identifier names.

**✓ DO** favor consistency over readability, and readability over brevity.

**✓ DO** use common names, such as **value** or **item**, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the paramater is not important.

**✓ DO** use US English spelling except for `MonoBehaviour` and its subclasses.

**X DO NOT** capitalize each word in closed-form compound words (two or more words that are connected and written as one word such as Endpoint).

**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters (exceptions apply).

**X DO NOT** use **Hungarian** notation in identifiers.

Example:
```csharp
// Good
int counter;
string name;

// Bad
int iCounter;
string strName;
```

**X DO NOT** use abbreviations, contractions, or acryonyms **that aren't widely accepted or commonly used** as part of identifier names.

Example:
```csharp
// Good
public void ShowWindow();

// Bad
public void ShowWin();
```

***X AVOID*** using identifiers that conflict with keywords of widely used programming languages.

## Namespaces

**✓ DO** use PascalCasing, and concatenate multiple words together without hyphens ( - ) or underscores ( \_ ), and separate namespace components with periods.

**✓ CONSIDER** using plural namespace names where appropriate.

**✓ DO** organize namespaces with a clearly defined structure.

The following template specifies the general rule for naming namespaces:
```
<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]
```

Example:
```csharp
using Monstronauts.PotionPunch
using Monstronauts.Modulark.Analytics
using Monstronauts.Modulark.Utils
using Monstronauts.Twiddle.Core.BaseClasses
```

**X DO NOT** use the same name for a namespace and a type in that namespace.

## Classes & Structs

**✓ DO** use PascalCasing.

**✓ DO** name classes and structs with nouns or noun phrases.

**✓ CONSIDER** ending the name of derived classes with the name of the base class.

Example:
```csharp
public class RoundSquare : Square
```

**X DO NOT** give class or struct names a prefix. Use namespaces to classify and group them instead.

## Interfaces

**✓ DO** name interfaces with adjective phrases, or ocassionally with nouns or noun phrases, prefixed with the letter "I".

Example:
```csharp
interface IComponent {} // Descriptive noun
interface ICustomAttributeProvider {} // Noun phrase
interface IPersistable {} // Adjective
```

**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class-interface pair where the class is a standard implementation of the interface.

Example:
```csharp
public class CellHandler : ICellDelegate
```

## Methods

**✓ DO** use PascalCasing.

**✓ DO** name methods using verbs or verb phrases.

## Properties

**✓ DO** use PascalCasing.

**✓ DO** name collection properties with a plural phrase instead of using a singular phrase followed by "List", "Set", "Dictionary", or "Collection"

**✓ DO** name Boolean properties with an affirmative phrase and prefix them with "Is", "Can", or "Has" when it makes sense and adds value.

**✓ DO** name a property the same as its type when the type is not a primitive.

## Events

**✓ DO** use PascalCasing.

**✓ DO** name events with a verb or a verb phrase, using the Past Tense.

**X DO NOT** use "Before" or "After" prefixes or postfixes such as "Will", "On", "Is", "Did" to indicate pre- and post-events. Use present and past tenses as described.

Example:
```csharp
// Good
public event Action Closing;
public event Action Closed;

// Bad
public event Action IsClosing;
public event Action DidClose;
```

**✓ DO** name the event parameter "sender" of type "object" if it represents the object that raised the event.

**✓ DO** name event argument classes with the EventArgs suffix.

**✓ DO** name the event parameter "e" if it represents that event argument class.

## Delegates

**✓ DO** use PascalCasing.

**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.

Example:
```csharp
// Good
public delegate void ClickEventHandler(){}

// Bad
public delegate void Click(){}
```

**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.

```csharp
// Good
public delegate void RenderCallback(){}

// Bad
public delegate void Render(){}
```  

**X DO NOT** add the suffix "Delegate" to a delegate.

## Fields

**✓ DO** use camelCasing for all non-static field names.

**✓ DO** prefix private fields with "_" to easily identify them in constructors, methods, and properties.

Example:
```csharp
public class Hero
{
  public string alias;
  protected string realName;
  string _secretIdentity;
}
```

**✓ DO** use PascalCasing for static field names.

**✓ DO** name fields using a noun, noun phrase, or adjective.

**✓ DO** use SCREAMING_CAPS for constants or readonly variables.

Example:
```csharp
public static float DefaultTurnRate = 20.0f;
public static const float DEFAULT_TURN_RATE = 20.0f;
```

## Parameters

**✓ DO** use camelCasing.

**✓ DO** favor descriptive parameter names over abbreviated or single character names except when (A) it is widely accepted, (B) it is scoped inside a loop, and (C) it is explicitly written in this guide.

**✓ DO** use "left" and "right" for binary operator overload parameter names if there is no meaning to the parameters.

**✓ DO** use "value" for unary operator overload parameter names if there is no meaning to the parameters.

## Enums

**✓ DO** use PascalCasing.

**✓ DO** use singular names for regular enums, and plural names for bit field enums (flags enums).

Example:
```csharp
public enum Color
{
  Red,
  Green,
  Blue,
  Yellow,
  White,
  Black
}

[Flags]
public enum Sides
{
  None = 0,
  Top = 1,
  Left = 2,
  Right = 4,
  Bottom = 8
}
```

**X DO NOT** add the suffix "Enum", "Flag" or "Flags".

## Attributes

**✓ DO** use PascalCasing.

**✓ DO** add the suffix "Attribute".

## Exceptions

**✓ DO** use PascalCasing.

**✓ DO** add the suffix "Exception".

## String Keys

**✓ DO** use PascalCasing.

## Prefabs

**✓ DO** use PascalCasing.

## Scenes

**✓ DO** use PascalCasing.

## Scriptable Objects

**✓ DO** use PascalCasing.

## Assets & Resources

**✓ DO** use PascalCasing.

## Where To Next?
- [Show All Topics](../README.md)
- [Naming Guidelines (You Are Here)](#naming-guidelines)
- [Formatting Guidelines](FORMATTING.md)
- [Design Guidelines](DESIGN.md)
- [Learning Resources](RESOURCES.md)