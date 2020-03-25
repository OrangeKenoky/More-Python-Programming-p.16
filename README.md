Note: this is a readme but it comes out formatted all funny. Why?  Would have expected plain text.

Here's the expected output;
===== RESTART: C:/Stuff/ProgramCode/Python 3.8/book-p16.py =====
Point constructor
{X:10, Y:20}
Point constructor
Circle constructor
{X:100, Y:100},{RADIUS=50}


# More-Python-Programming-p.16
Shows the example on page 16 with errors I made discussed in readme.
#single inheritance example from the book,  page 16.

class Point():
    #note - the next two lines appear to initialize x and y as floating point but... they aren't needed.  Or are they?
    #x=0.0
    #y=0.0
    #error 1 -
    # on the next line and similar lines below, I only used one "_".  Two are needed!  Double underline init statements! DUNDER!
    def __init__(self, x, y):
        #note - the values supplied by x and y in the above __init__ do not fall directly into the self.x and self.y output values
        #you could put the following and get the output x =333 and the y = n, which would be the value passed in.
            #def __init__(self, m, n):
            #self.x=333
            #self.y=n
        self.x=x
        self.y=y
        print("Point constructor")
    def ToString(self):
        return "{X:"+str(self.x)+", Y:"+str(self.y)+"}"

class Circle(Point):
    #Note - similar to note for x and y above... is the radius = 0.0 needed?  Does not appear to accomplish anything.
    #radius =0.0
    def __init__(self,x,y,radius):
        #"super" in the next statement means to look in the class, which was brought in the defining "class Circle(Point):" statement.
        super().__init__(x,y)
        self.radius=radius
        print("Circle constructor")

    def ToString(self):
    #note- this function 'ToString' has a same named function in the Point class, which is going to provide output that
    #is obtained first and then have the radius portion added here.
    #If there was no ToString function in Point class, 
    #there'd be an error created by using the super().ToString() in the next statement.
    #Remember: the "super" word means look in the class brought in by the statement defining this class "class Circle(Point):"
        return super().ToString()+\
               ",{RADIUS="+ str(self.radius)+"}"
p=Point(10,20)

#error two-
#I typed in "ToSTring" in the next line instead of "ToString".  Good grief.  Be careful tyPINg!
print(p.ToString())
c=Circle(100,100,50)
print(c.ToString())
