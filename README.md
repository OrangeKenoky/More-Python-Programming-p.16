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
    x=0.0
    y=0.0
    #error 1 -
    # on the next line and similar lines below, I only used one "_".  Two are needed!  Double underline init statements! DUNDER!
    def __init__(self, x, y):
        self.x=x
        self.y=y
        print("Point constructor")
    def ToString(self):
        return "{X:"+str(self.x)+", Y:"+str(self.y)+"}"

class Circle(Point):
    radius =0.0
    def __init__(self,x,y,radius):
        super().__init__(x,y)
        self.radius=radius
        print("Circle constructor")

    def ToString(self):
        return super().ToString()+\
               ",{RADIUS="+ str(self.radius)+"}"
p=Point(10,20)

#error two-
#I typed in "ToSTring" in the next line instead of "ToString".  Good grief.  Be careful tyPINg!
print(p.ToString())
c=Circle(100,100,50)
print(c.ToString())
