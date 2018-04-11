# Monstronauts' Unity Project Guidelines #

Follow these guidelines and preferred practices when working on Unity projects with the Monstronauts team.

## Table of Contents
- [Naming Guidelines](NAMING.md)
 + [General Rules](NAMING.md#general-rules)
 + [Namespaces](NAMING.md#namespaces)
 + [Classes & Structs](NAMING.md#classes--structs)
 + [Interfaces](NAMING.md#interfaces)
 + [Methods](NAMING.md#methods)
 + [Properties](NAMING.md#properties)
 + [Events](NAMING.md#events)
 + [Delegates](NAMING.md#delegates)
 + [Fields](NAMING.md#fields)
 + [Parameters](NAMING.md#parameters)
 + [Enums](NAMING.md#enums)
 + [Attributes](NAMING.md#attributes)
 + [Exceptions](NAMING.md#exceptions)
 + [String Keys](NAMING.md#string-keys)
 + [Prefabs](NAMING.md#prefabs)
 + [Scenes](NAMING.md#scenes)
 + [Scriptable Objects](NAMING.md#scriptable-objects)
 + [Assets & Resources](NAMING.md#assets--resources)
- [Formatting Guidelines](FORMATTING.md)
  + [Access Level Modifier](#access-level-modifier)
  + [Folder Structure](#folder-structure)
  + [Code Comments](#comments)
  <!--
  implicit type vars doFactory
  var stream = File.Create(path);
var customers = new Dictionary();
 
// Exceptions
int index = 100;
string timeSheet;
bool isCompleted;


static members at the top of a class doFactory

block comments for methods
use /// XML formatted comments (at minimum must have summary)
do not use block comments
do not use inline comments at the end of the line
comment should take up their own line
-->

<!--

- [Declaration Guidelines](#declarations)
  + [Access Level Modifiers](#access-level-modifiers)
  + [Fields & Variables](#fields--variables)
  + [Classes](#classes)
  + [Interfaces](#interfaces)
- [Spacing](#spacing)
  + [Indentation](#indentation)
  + [Line Length](#line-length)
  + [Vertical Spacing](#vertical-spacing)
- [Brace Style](#brace-style)
- [Switch Statements](#switch-statements)
-->

<!--
- [Design Guidelines]
  + [Class or Struct]
  + [Abstract Classes]
  + [Static Classes]
  + [Interfaces]
  + [Structs]
  + [Enums]
  + [Nested Types]
  + [Libraries] // must be modular

  
  Prioritize over your own solution
de-couple
reusable
-->
- [Learning Resources](RESOURCES.md)
  + [Basic Pipeline Topics](RESOURCES.md#basic-pipeline-topics)
  + [Advanced Programming Topics](RESOURCES.md#advanced-programming-topics)
  + [Useful Topics](RESOURCES.md#useful-topics)
    * [Camera](RESOURCES.md#camera)
    * [Animation](RESOURCES.md#animation)
    * [Effects](RESOURCES.md#effects)
    * [Audio](RESOURCES.md#audio)
  + [Networking Topics](RESOURCES.md#networking-topics)
  + [Art Topics](RESOURCES.md#art-topics)
    * [Concept Art](RESOURCES.md#concept-art)
    * [Maya](RESOURCES.md#maya)

## Contributors

This guide is maintained by [Monstronauts](https://monstronauts.com)

- [Allen Tan](https://github.com/abgtan)
- [Bear Sarile](https://github.com/bearsarile)

## Games

Please check out our games!

- [Potion Punch](http://potionpunch.com/)