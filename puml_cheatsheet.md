# PUML CHEATSHEET

# Access Modifiers (and similar?)
- Private --> '-'
- Public --> '+'
- Package Private --> '~'
- Static --> '{static}'
- Final --> '{final}'


# Field / Var type:
{access_mod}"FieldName" : <Type>

So for a public variable called xController, that is a Controller, we have:

```
+xController: Controller
```

# Functions
Similar to variables, but they're functions:
{access_mod}"FuncName"("param1Name":<param1Type>, "param2Name":<param2Type>) : <returnType>

so for a private function called printStringXTimes, that takes a string and an int, and returns nothing, we have:
```
-printStringXTimes(s:String, num:int): void
```


# Defining a package and a class within that package
```
@startuml
    package PackageName {

        {access_mod}class ClassName {
            // class vars
        }

    }
@enduml
```

We can make classes abstract or otherwise, e.g.:

```
+abstract class AbstrClassName {
    // xxx
}
```

Likewise, we can have enumerators and interfaces with nearly identical syntax:

```
+enum {
    ENUM_VAL_1
    ENUM_VAL_2

    +someEnumFunc() : void
}

~interface InterfaceName {
    +interfaceVar : int

    -someInterfaceMethod() : void
}
```

# Inheritance, Implementation, Dependency, Etc.

- Extension	        <|--	Specialization of a class in a hierarchy
- Implementation	<|..	Realization of an interface by a class
- Composition	    *-- 	The part cannot exist without the whole
- Aggregation	    o-- 	The part can exist independently of the whole
- Dependency	    --> 	The object uses another object
- Dependency	    ..> 	A weaker form of dependency
- Strong Ownership? --+     Idk I only saw this once.


Inter-package dependency involves prefacing the class1 depending on class2 with their differing packages:

```
presentation.MainViewer --> domain.ContentCalculator
```