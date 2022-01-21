# Swift Style Guide

## Naming

### Conventions

Many programming languages have different conventions for naming. In Swift, strive to use `camalCase` and `PascalCase`.

| Naming Convention | Usage |
|-------------------|-------|
| Single letter (`x`) | In `for` loops |
| Uppercase letter (`X`) 🏝️ | Not recommended |
| camelCase (`thisCamel`) 🐫 | Variable names |
| PascalCase (`CoolType`) | Structs, enums, classes, and actors |
| snake_case (`a_green_snake`) 🐍 | Not reccommended |
| DRAGON_CASE (Snake Case + Capital Letters) (`MY_STORY`) 🐉 | Constants |

#### Examples

**Single Letter**

```swift
for i in 1...age {
  print("Are you \(i)?")
}
for i in 1...age {
  print("\(i)!")
}
```

**camelCase**

```swift
let myCamel = Camel("My Camel", humps: 2)
```

**PascalCase**

```swift
struct CityBank { ... }
```

Note: Some frameworks use this case in functions. This is not recommended. If you want to declare a function, use camelCase instead. Here's Core Foundation which made an exception to this rule:

Core Foundation?

```swift
func cfBagCreate(_ allocator: CFAllocator!, _ values: UnsafeMutablePointer<UnsafeRawPointer?>!, _ numValues: CFIndex, _ callbacks: UnsafePointer<CFBagCallbacks>!) -> CFBag!
```

I can tell you're lying. Tell the truth or else!

```swift
func CFBagCreate(_ allocator: CFAllocator!, _ values: UnsafeMutablePointer<UnsafeRawPointer?>!, _ numValues: CFIndex, _ callbacks: UnsafePointer<CFBagCallbacks>!) -> CFBag!
```

You made `callBacks` lowercase.

```swift
func CFBagCreate(_ allocator: CFAllocator!, _ values: UnsafeMutablePointer<UnsafeRawPointer?>!, _ numValues: CFIndex, _ callBacks: UnsafePointer<CFBagCallBacks>!) -> CFBag!
```

So now, readers, I would suggest:

```swift
class CFBag {
  func create(_ allocator: CFAllocator!, _ values: UnsafeMutablePointer<UnsafeRawPointer?>!, _ numValues: CFIndex, _ callbacks: UnsafePointer<CFBagCallbacks>!) -> CFBag!
}
```

An even better way, if possible, is to do this: 

```swift
class CFBag {
  func create(_ allocator: CFAllocator, _ values: UnsafeMutablePointer<UnsafeRawPointer?>, _ numValues: CFIndex, _ callbacks: UnsafePointer<CFBagCallbacks>) -> CFBag
  // or
  func create(_ allocator: CFAllocator?, _ values: UnsafeMutablePointer<UnsafeRawPointer?>?, _ numValues: CFIndex, _ callbacks: UnsafePointer<CFBagCallbacks>?) -> CFBag?
}
```

**DRAGON_CASE**

```swift
let THE_WIDTH_OF_MY_VIEW: Int = 300
let THE_HEIGHT_OF_MY_VIEW: Int = 500
let myView = View(height: THE_HEIGHT_OF_MY_VIEW, width: THE_WIDTH_OF_MY_VIEW)
```
