| Index  | Topics |
| ------ | ------ |
| Python | Basics |



=====================================================
1. Basics
=====================================================

Datatypes : 
	Primitive: int, float, bool, str
	Nonprimitive: list, tuple, dict, set


Operators : 
	Arithmetic (+ - * / % ** //)
	Assignment (= += -= *= /= %= **= //=)
	Comparison (== != > < >= <=)
	Logical (and, or, not)
	Identity (is, is not)
	Membership (in, not in)	
	Bitwise (& | ^ ~ << >>)	

Input/Output:
	print("Hello World")
	n = input("Enter data : ")

Tricks: 
	Comments (#)
	Type Hinting(name: str = "Bob")
	Return type(func add(a:int, b:int)->int:)
	Define later(def add(a,b): pass)OR(def add(a,b):...)
	Import Libs (import math as m)
	Swap values (a,b = b,a)
	Get type (type(val))
	Global variable (global varName)
	Check if current scipt run as main program (if __name__ = "__main__" : main())
	

=====================================================
2. Control Flow
=====================================================

Conditionals : 
	If-Else (if: elif: else:)
	Switch (match val: case val: case_:)

Loops :
	For :	
		for animal in ["dog", "cat"]:
		for i in range(lower,upper,step):
		for i, value in enumerate(animals):
	While : 
		while val < 5:
	
	
=====================================================
3. Collections
=====================================================

List : 
(Hetro, Ordered, Mutable, AllowsDuplicates)
	lst = [True, 15, "Hello"]
	lst.append(val)
	lst.pop()
	lst[0]
	lst[-1]
	lst[1:3]
	lst[2:]
	lst[::2]
	lst[::-1]
	# lst[start:end:step]
	del lst[indx]
	lst.remove(val)
	lst.index(val)
	lst + otherLst	
	lst.extend(otherLst)
	val in lst
	len(lst)
	a,b,c = lst

Tuple : 
(List but immutable)
	tup = (True, 15, "Hello")
	tup[0]
	tup + otherTup
	tup[:2]
	val in tup
	a,b,c = tup
	
Dict : 
(Unique immutable keys, mutable)
	dct = {"Name":"Ojas", "Roll":15988}
	dct["Name"]
	dct.get("Name")
	list(dct.keys())
	list(dct.values())
	del dct["Name"]

Set : 
(Mutable, unordered, Hetro)
	st = {1,True,"Hello"}
	st.add(val)
	st & otherSet
	st | otherSet
	st - otherSet
	st ^ otherSet
	st >= otherSet
	st <= otherSet
 	val in st


> The curly brackets{} by default belongs to dict when empty initializing, not to set
Note : LEARN ABOUT 'LIST COMPREHENSION' (new_list = [item for item in iterable if condition])

=====================================================
4. Exception Handling
=====================================================

try : 
     raise Error
except Error as e : 
      pass
else:
finally: 

=====================================================
5. Functions
=====================================================

def add(x,y): 
 	return x + y
def varArgs(*args):
	return args
def keywordArgs(**kwargs):
	return kwargs
def swap(x,y):
	return y,x
def create_adder(x):
	def adder(y):
		return x+y
	return adder
def create_avg():
    	total = 0
    	count = 0
   	def avg(n):
        	nonlocal total, count
	        total += n
        	count += 1
	        return total/count
	return avg

mulAns = (lambda x,y: x*y)(3,4)
numbers = [1,2,3,4]
squaredNums = list(map(lambda x : x**2, numbers))
evenNums = list(filer(lambda x : x%2==0, numbers))
product = reduce(lambda x,y : x*y, numbers)
 
add(2,5)
add(y=5,x=2)
varArgs(1,2,3)
keywordArgs(big="foot", happy="ness")
x, y = swap(10,20)
add_10 = create_adder(10)
add_10(3)
avg = create_avg()
avg(3)
avg(5)
avg(2)



> When printing note that *args prints as list, **kwargs prints as dict. 



=====================================================
6. Classes
=====================================================

class Person:
	_totalPersons = 0
	def __init__(self, name, age):
		self.name = name
		self.age = age
		Person._totalPersons += 1
	@staticmethod
	getTotalPersons():
		return Person._totalPersons;
	def introduce(self):
		print(f"Yo guys mi name {self.name} and me {self.age} yrs ol)

class Superhero(Person):
	# code here 

P1 = Person("Ojas", 22)
P2 = Person("Riya", 20)
P1.introduce()
print(P2.name)
print(f"Total : {Person.getTotalPersons}")



// OOPS : 
	- Abstraction : hiding complex implementation details and showing only essential features to the user
	- Polymorphism : Ability of an object to take on multiple forms
	- Inheritance : one class acquires properties of other class
	- Encapsulation : Data and methods bundling 

// INHERITANCE:
	- Types : Single, multiple, multilevel, hierarchical, hybrid
	- Interface contracts : Has only @abstractmethod. Thus forcing a compulsory implementation to child class
	- Abstract classes : Can Have @abstractmethod, concrete methods, variables. 
	Note : 'from abc import ABC, abstractmethod' is used for interface, abstract classes
	Note : Both interface contracts and abstract classes cannot have their own objects.

	// Basic : 
		class Animal: 
    			def __init__(self, name):
        			self.name = name
    			def speak(self):
        			print(f"{self.name} makes a Sound")

		class Dog(Animal):
    			def speak(self):
        			print(f"{self.name} Barks")

		class Cat(Animal):
		    	def speak(self):
        			print(f"{self.name} Meows")
        
		dog = Dog("Dollar")
		cat = Cat("Whiskers")


	// INTERFACE CONTRACTS : No functionality, only forced signature with @abstractmethod and 'pass'
	// ABSTRACT CLASS : Has common functionallity for all childeren to inherit



=====================================================
7. Advance Topics
=====================================================

Generator Function: 
(Memory efficient when dealing with large datasets)
	def count_up_to_max(maxNum):
    		count = 1
    		while count <= maxNum:
        		yield count
		        count += 1
        
	myGenerator = count_up_to_max(5);

	print(next(myGenerator));
	print(next(myGenerator));
	for num in myGenerator:
	    print(num)

 
env	
numpy, scipy, pandas, seaborn