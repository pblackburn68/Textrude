# Textrude Sample Projects and Helpers

Project files for the excellent **TextrudeInteractive** which is part of the Textrude suite by Neil MacMullen  [here](https://github.com/NeilMacMullen/Textrude)

Yaml model 

```mermaid
classDiagram
  model --* interface 
  model --* entity
  entity --* property  
  interface --* property  
  class model{ 
    +String name
    List~interface~ interfaces
    List~entity~ entites
  }
  
  class interface{
    +String name
    +int type
    +bool isIdentity
  }
  class property{
    +string: name
    +int: type
    +int: sizeS
    +bool: isIdentity
    +bool: isKey
    +bool: isObject
  }
  class entity{
    +string: name
    List~interface~ interfaces
    List~property~ properties
  }
```
<br>
When specifying an entity interface name, additional information can be supplied as follows
interface name:beforeafter:usekey<br>
Eg.
<pre>
entities
- name: User   
- interfaces: IUser:0:true
</pre>
beforeafter:
Indicate if the interface properties are to be rendered before or after the entities main properties
where 0 for before and a 1 would render them after
useKey:
Set a value indicating if sql generation will use the interfaces key (if defined)