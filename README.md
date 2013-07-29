Library
=======
#create book class
class Book(object):
    def __init__(self, title):
        self.title = title

#define how book is displayed as string      
    def __str__(self):
        return str(self.title)

#define how book is displayed as object          
    def __repr__(self):
        return self.title

#doesn't make sense to me why this would be in the book class and not shelf 
    def enshelf(self, shelf):
        pass
#disclaimer condition to be inherited to all classes
    Disclaimer = "This is the property if King County Library System and should be treated with respect." 

#create Shelf Class
class Shelf(Book):
    def __init__(self, name):
        self.shelf = []
        self.name = name

#create method to add books to shelf        
    def addbk(self, book):
        self.shelf.append(book)

#create method to remove books from shelf
    def removebk(self, book):
        self.shelf.remove(book)

#display the books that are on the shelf
    def displaybks(self):
        return self.shelf        

#define how shelf will be named      
    def __str__(self):
        return str(self.name)

#create a Library Class
class Library(Shelf):
    def __init__(self):
        self.numshelf = []

#create method to add shelves to library        
    def addshlf(self, shelf):
        self.numshelf.append(shelf)

#create method to remove shelves from library    
    def removeshlf(self, shelf):
        self.numshelf.remove(shelf)

#total number of shelves in Library        
    def shelftot(self):
        shelftot = len(self.numshelf)
        return shelftot

#display libraries content
    def bookReport(self):
        return "This Library has %s shelves. They contain the books %s %s %s %s" % (self.shelftot(), self.numshelf[0].displaybks(), self.numshelf[1].displaybks(), self.numshelf[2].displaybks(), self.Disclaimer)
        
#create some books    
Outlier = Book("Outlier")
Bible = Book("Bible")
Moby_Dick = Book("Moby Dick")
Gone_W_Wind = Book("Gone W/ Wind")
Blink = Book("Blink")
Twlight = Book("Twlight")
WarNPeace = Book("War and Peace")
Salt = Book("Salt")
Zelda = Book("Zelda")

#create some shelves
shelf1 = Shelf("shelf1")
shelf2 = Shelf("shelf2")
shelf3 = Shelf("shelf3")

#create a Library
SeattleC = Library()

#add books to shelves and shelves to Library
shelf1.addbk(Twlight)
shelf1.addbk(Blink)
SeattleC.addshlf(shelf1)
SeattleC.addshlf(shelf2)
shelf2.addbk(Outlier)
shelf2.addbk(Bible)
shelf2.addbk(Gone_W_Wind)
shelf3.addbk(WarNPeace)
shelf3.addbk(Salt)
shelf3.addbk(Zelda)
SeattleC.addshlf(shelf3)

#display libraries content
print SeattleC.bookReport()
#remove bible
shelf2.removebk(Bible)
#display updated library
print SeattleC.bookReport()
