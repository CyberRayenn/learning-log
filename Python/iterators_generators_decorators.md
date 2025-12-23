23/12/25 - day 80 of learning python - day one of posting my journey

today i learned iterable , iterator , generators and some decorators

#iterable vs iterator
-----------------------------
# iterable
# [1] object contains Data that can be iterated upon
# [2] Examples (string , list , set , tuple , dictionary)
# ---------------------------
# iterator
# [1] object used to iterate over iterable using next() method return 1 element at a time
# [2] you can genreate iterator from iterable when using iter() method 
# [3] For Loop already calls iter() method on the iterable behind the scene
# [4] gives "stopIteration" If Theres No Next Element
----------------------------

i understand it with this example : 

mystring = "cyber"
for i in mystring :
  print(i)
=>c
=>y
=>b
=>e
=>r


#for iterator
myIterator = iter(mystring)

print(next(myIterator))
print(next(myIterator))
print(next(myIterator))
print(next(myIterator))
print(next(myIterator))

=> c
=> y
=> b
=> e
=> r


so the thing that we don't that the loop for , it's exactly like that : 
for i in iter(mystring):
  print(i)


# -------------------------
# --Generators-------------
# -------------------------
# [1] Generator is a Function with "yield" keyword instead of "return"
# [2] it support iteration and return generator iterator by calling "yield" 
# [3] Generator Function can have one or more "yield"
# [4] by using next() it resume from where it called "yield" not from begining
# [5] when called , its not start automatically, its only give you the control
# ---------------------------

def generator():
  yield 1 
  yield 2 
  yield 3
  yield 4

mygen = generator()
print(next(mygen))
print(next(mygen))
print(next(mygen))
print(next(mygen))

=> 1
=> 2 
=> 3 
=> 4

# -------------------------
# --Decorators => Intro---
# -------------------------
# [1] Sometimes called meta programming
# [2] everything in python is object even functions 
# [3] decorator take a function and add some functionality and return it 
# [4] Decorator wrap other function and enhance their behaviour
# [5] Decorator is higher order function (function accept function as parameter)
# -------------------------

def myDecorator(func): #Decorator

    def nestedFunc() : #Any Name its just for decoration
        
        print("Before") # message from decorator
    
        func() #execute function

        print("after") # message from decorator

    return nestedFunc

@myDecorator
def sayhello():

   print( "hello from say hello function" )

@myDecorator
def sayhowareyou():

    print("hello from say how are you function")

sayhello()

print ("#" * 30)

sayhowareyou()

