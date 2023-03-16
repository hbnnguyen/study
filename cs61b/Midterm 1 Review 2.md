### array basics
- arrays are the simplest way to keep a sequence of values in an ordered manner
	- array size is fixed once the array is created
	- arrays use square bracket `[]` notation to declare and access values
- there are 3 main ways to initialize an array
	- `string[] arr1 = new String[5];` *specified array length, initialized with no values*
	- `int[] arr2 = new int[] {3,10,7};` *initialized with values directly inputted*
	- `char[] arr3 = {'a','e','b','u'};` *"new" can be omitted when initializing directly*

	![[Pasted image 20230313223421.png]]

## lists
### what is a list?
```
public interface List<T> {
	void add(T item);
	T get(int idx);
	void remove(int idx);
	boolean contains(Object o);
	int size();
}
```
- collection of items in an ordered manner
- different implementations of lists have different pros and cons
- unlike arrays, lists are true Objects, not primitive types
- dynamic size
- must be imported from `java.utils` or some other library
- set of given methods that may be used to access and modify elements
- implementation is much more complicated, but lots of useful functionality given to users

## linked lists
IntLists
- recursive structure where each IntList item points to the next item
- messy, lacking in encompassing structure
![[Pasted image 20230315215021.png]]











