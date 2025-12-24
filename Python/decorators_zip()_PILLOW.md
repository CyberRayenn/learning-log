23/12/25 - day 81 of learning python - day one of posting my journey

today i wanted to practise decorators so i did a practical speed test and i used time library

# ------------------------------------------
# --Decorators => practical speed test -----
# ------------------------------------------

def myDecorator(func): #Decorator

    def nestedFunc(*numbers) : #Any Name its just for decoration
        
        for number in numbers :

            if number < 0:

                print(f"beware the number {number} is less than zero")
    
        func(*numbers) #execute function

        print("after") # message from decorator

    return nestedFunc



@myDecorator
def calculate(n1,n2):

    print( n1 + n2 )

calculate(-10,-20)


from time import time

def speedtest(func) :

    def wrapper() :

        start = time()

        func()

        end = time()

        print(f"function running time {end - start}")
    
    return wrapper()

@speedtest
def bigloop():

    for number in range(1,20000):

        print(number)
--------------------------------------------------------------------------------------------------------------------------------------------------------------

THEN I LEARNED ZIP() built in function and i did this examples :

# -----------------------------------------------------
# --practical => loop on many iterators with zip() ----
# -----------------------------------------------------
# zip() Return A Zip object Contains All Objects
# zip() length Is The Length Of Lowest Object
# ----------------------------------------------------

list1 = [1,2,3,4,5]
list2 = ["A" , "B", "C" ]
tuple1  = ("Man" , "Women" , "Girl" , "Boy")
dict1 = {"name" : "cyber" , "age" : 19 , "Country" : "USA"}


for item1 , item2 , item3 , item4  in zip(list1,list2,tuple1,dict1):

    print("List 1 Item =>" , item1)
    print("List 2 Item =>" , item2)
    print("tuple 1 Item =>" , item3)
    print("dict 1 key  =>" , item4 , ", value =>" , dict1[item4])



ultimatelist = zip(list1,list2)

for item in ultimatelist:

    print(item)

---------------------------------------------------------------------------------------------------------------------------------------------------

I PRACTISED SOME OF FUNCTIONS INSIDE THE LIBRARY "PILOW" OF MODIFING PHOTOS

# -----------------------------------------------------
# --practical => Image Manipulation with pillow--------
# -----------------------------------------------------

from PIL import Image 

# Open The Image
myImage = Image.open("me.jpg")

# show The Image
myImage.show()

# Crop The Image (MY BOX)
mybox = (300,300,800,800) #(Left , Upper , right , Lower)
myNewImage = myImage.crop(mybox)

# show the new image
myNewImage.show()

# My Converted Mode Image
myConverted = myImage.convert("L")
myConverted.show()
