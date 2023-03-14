
## primitive types vs. reference types
- every variable in java must have a declared type
	- ex. `Int n = 0` 

### primitive types
- the most basic data types in java
- these are actual values
- there are 8 primitive types
	- byte
	- short
	- int
	- long
	- float
	- double
	- boolean
	- char

### reference types
- store "references" to objects
	-  ex.  an `SLList` is a reference type
- there are 4 reference types
	- class
	- interface
	- array
	- type

### how to tell what type a variable is
- ask "is it a primitive?"
- if not, it's a reference

### exercise: primitive or reference??
1. `int five = 5;`  *primitive: int*
2. `byte b = 123;`  *primitive: byte*
3. `SLList list = new SLList(5);`  *reference: class* 
4. `int[] arr = [1,6,8,2];`  *reference: array*
5. `boolean cat = false;` *primitive: boolean*
6. `boolean[] cats;` *reference: array*
7. `T iteml` *reference: type*


## static vs. instance variables

### instance variables
- declared inside class but not inside methods
- each object has its own version of an instance variable

### static variables
- declared inside class with static keyword but not inside methods
- every object of that class shares this static variable

<mark style="background-color: #fcccdc">example(from the video) :</mark>
```
class Pineapple {
	int slices = 8; // instance
	static boolean isSpiky = true; // static
}
```

<mark style="background-color: #fcccdc"> example(me, i made this.): </mark> in super mario, all the goombas have the same behavior: walking speed, animation, etc. that is their static variable. their instance variable is their death status. if you kill one goomba, only that one dies.

## static vs instance methods
- both declared within class

### instance methods
- object must be created before instance method can be called
- method is called on specific object (e.g. `this`)

### static methods
- use static keyword
- can be called without creating objects
- shared by all instances

<mark style="background-color: #fcccdc">example(from the video) :</mark>
```
class Pineapple {
	static boolean isSpiky = true; // static
	int slices = 8; // instance

	public int numSlices() {
		return this.slices;
	}

	public static boolean isSpiky() {
		return isSpiky;
	}
}
```

![[Pasted image 20230313173452.png]]

### practice problem
![[Pasted image 20230313173544.png]]

## scope
- the region of your java code where a certain variable is defined and from which it can be accessed
	- can only access a variable within its scope (the region in which it was created)
- if we wanted to do something like `pineapple += 5`
	- java has a process to figure out where `pineaple` is
		- check local scope: current method body
		- check current instance scope: attributes of the object
		- check classes this class inherits from (inheritance)


![[Pasted image 20230313175139.png]]

![[Pasted image 20230313175333.png]]

## inheritance

### classes and subclasses
subclasses (or child classes)
- extend another class
- in this example, Dog and Cat are subclasses of Animal
	- Corgi and Shiba Inu are subclasses of Dog
	![[Pasted image 20230313175634.png]]

superclasses (or parent classes) 
- classes that are extended by another class.
- Animal is a superclass of Dog and Cat

each class can only extend one other class, but can be extended by many classes
- this is different from interfaces, in which a class can implement many interfaces

### interfaces
- interfaces are implemented by classes
	- they define a specific set of methods that the implementer **must** have
- interfaces can also define default methods for the implementer
- a class can implement multiple interfaces
	- in this case, the cat class implements the nine lives and female interfaces
	 ![[Pasted image 20230313184522.png]]

### overloading vs. overriding
- overloading is when two methods in the same class have the same name but different input parameters. this is decided at compile time
- overriding is when a class and subclass share the same **exact** method signature
	- we determine if we are going to use an overridden method via dynamic method selection
	![[Pasted image 20230313185036.png]]
	![[Pasted image 20230313185157.png]]

do this exercise
![[Pasted image 20230313185249.png]]

`Jake.bark();`
`Jake.eat();`
`Jake.loudBark();`
`Jake.angryBark();`
`Milton.bark();`
`Milton.loudBark();`

## dynamic method selection
### dynamic vs. static typing
- static type is the variable type to the left of the variable name during declaration
	- they are typically the variable java acknowledges during compilation
- dynamic type is the variable type to the right of the variable name
	- they are typically the variable that java acknowledges during compilation
	- dynamic type can be a subclass of the static type but never the opposite
	![[Pasted image 20230313190910.png]]

do this exercise
![[Pasted image 20230313191041.png]]

### dynamic method selection procedure
1. determine the static classes of the calling object and any parameters
	1. if the static class or any class it extends does not have the method signature, we throw a compiler error
2. we **lock onto** the method we choose
3. in runtime, we look at the dynamic class of the calling object
	1. if we see that the method we locked onto was overridden in the dynamic class, we lock into the overridden method
4. run whatever we locked onto

![[Pasted image 20230313192033.png]]

![[Pasted image 20230313192417.png]]

![[Pasted image 20230313193450.png]]

![[Pasted image 20230313194519.png]]
