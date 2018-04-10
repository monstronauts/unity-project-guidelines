# Monstronauts' Unity Project Guidelines #

Follow these guidelines and preferred practices when working on Unity projects with the Monstronauts team.

## Table of Contents
- [Naming Guidelines](#naming-guidelines)
  + [General Rules](#general-rules)
  + [Namespaces](#namespaces)

## Naming Guidelines

The overarching goals of these guidelines are to balance the source code's **consistency**, **readability/clarity**, and **simplicity/brevity**. The reader must understand the purpose and type of each identifier in the source code without having to refer to, or rely on its complete declaration.

There are minor differences between Microsoft's standards, and Monstronauts' standards, so unless otherwise noted below, naming should follow the [Microsoft .NET Naming Standards for C#](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines).

### General Rules

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

### Namespaces

**✓ DO** organize namespaces with a clearly defined structure.

**✓ DO** use PascalCasing, and concatenate multiple words together without hyphens ( - ) or underscores ( \_ ), and separate namespace components with periods.

**✓ CONSIDER** using plural namespace names where appropriate.

The following template specifies the general rule for naming namespaces:
```
<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]
```

Example:
```csharp
Monstronauts.PotionPunch
Monstronauts.Modulark.Analytics
Monstronauts.Modulark.Utils
Monstronauts.Twiddle.Core.BaseClasses
```

**X DO NOT** use the same name for a namespace and a type in that namespace.

### Enums

