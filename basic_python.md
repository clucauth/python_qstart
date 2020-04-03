# Basic Python


## Usage

Python version: python -V

Print to console: print("Hello world")

Comment: #

Numbers: 2, 3.23, 52.3E-4 (E indicates powers of 10)

Strings: '', "", triple quotes for multi-lines

Format: 

    print('Why is {0} playing with that python?'.format(name))

Format (Python 3.6+): 

    print(f'Why is {name} playing with that python?')

More formats:

    print('{0:.3f}'.format(1.0/3))

    print('{0:_^11}'.format('hello'))

    print('{name} wrote {book}'.format(name='Swaroop', book='A Byte of Python'))

    print('a', end='')

    print('a', end=' ')

Whitespace is important in Python!

If statement:

    if guess = 1:
        print('1')
    elif guess < 1:
        print('<1')
    else:
        print('else')

While statement:

    while running:
        print('running')
    else:
        print('else')

For loop:

    for i in range(1, 5):
        print(i)
    else:
        print('else')

Function:

    def say_hello():
        print('hello world')
        
Dir function:

    import sys
    dir(sys)
    
    
## Data structures

List:

    shoplist = ['apple', 'mango', 'carrot', 'banana']
    # len(shoplist)
    # for item in shoplist:
    # shoplist.append('rice')
    # shoplist.sort()
    # del shoplist[0]
    
Tuple:

    zoo = ('python', 'elephant', 'penguin')
    # parentheses are optional, but recommended
    # len(zoo)
    # zoo[2]
    
Dictionary:

    d = {key1 : value1, key2 : value2 }
    
Sequence:

    shoplist = ['apple', 'mango', 'carrot', 'banana']
    # shoplist[-1]
    # shoplist[1:3]
    # shoplist[2:]
    # shoplist[1:-1]
    # shoplist[:]
    
    # shoplist[::2]  increment 2 per step
    
Set:

    bri = set(['brazil', 'russia', 'india'])
    # 'india' in bri
    # bric = bri.copy()
    # bric.add('china')
    # bric.issuperset(bri)
    # bri.remove('russia')
    # bri & bric # OR bri.intersection(bric)
    
    delimiter = '_*_'
    mylist = ['Brazil', 'Russia', 'India', 'China']
    print(delimiter.join(mylist))
    

## OOP

Method:

    class Person:
        def say_hi(self):
            print('Hello, how are you?')

Init:

    class Person:
      def __init__(self, name):
        self.name = name

      def say_hi(self):
        print('Hello, my name is', self.name)
        
Inheritance:

    class SchoolMember:
      '''Represents any school member.'''
      def __init__(self, name, age):
        self.name = name
        self.age = age
        print('(Initialized SchoolMember: {})'.format(self.name))

      def tell(self):
        '''Tell my details.'''
        print('Name:"{}" Age:"{}"'.format(self.name, self.age), end=" ")


    class Teacher(SchoolMember):
      '''Represents a teacher.'''
      def __init__(self, name, age, salary):
        SchoolMember.__init__(self, name, age)
        self.salary = salary
        print('(Initialized Teacher: {})'.format(self.name))

      def tell(self):
        SchoolMember.tell(self)
        print('Salary: "{:d}"'.format(self.salary))
        

## Exception

Error >< Exception

Handle exception:

    try:
      text = input('Enter something --> ')
    except EOFError:
      print('Why did you do an EOF on me?')
    except KeyboardInterrupt:
      print('You cancelled the operation.')
    else:
      print('You entered {}'.format(text))
      
Custom and raise exception:

    class ShortInputException(Exception):
      '''A user-defined exception class.'''
      def __init__(self, length, atleast):
        Exception.__init__(self)
        self.length = length
        self.atleast = atleast
        
    try:
      text = input('Enter something --> ')
      if len(text) < 3:
        raise ShortInputException(len(text), 3)
      # Other work can continue as usual here
    except EOFError:
      print('Why did you do an EOF on me?')
    except ShortInputException as ex:
      print(('ShortInputException: The input was ' +
           '{0} long, expected at least {1}')
          .format(ex.length, ex.atleast))
    else:
      print('No exception was raised.')
    finally:
      // do something
