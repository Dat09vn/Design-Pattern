The Singleton method or Singleton Design pattern is one of the simplest design patterns. It ensures a class only has one instance, and provides a global point of access to it.

--------------------------------------------------------------------------------------------------------------------

1./Static Member:

The Singleton pattern or pattern Singleton employs a static member within the class. This static member ensures that memory is allocated only once, preserving the single instance of the Singleton class.

2./Private Constructor:

The Singleton pattern or pattern singleton incorporates a private constructor, which serves as a barricade against external attempts to create instances of the Singleton class. This ensures that the class has control over its instantiation process.

3./Static Factory Method:

A crucial aspect of the Singleton pattern is the presence of a static factory method. This method acts as a gateway, providing a global point of access to the Singleton object.
When someone requests an instance, this method either creates a new instance (if none exists) or returns the existing instance to the caller.

--------------------------------------------------------------------------------------------------------------------
Steps to Implement Singleton Class in C++:

1./Make all the constructors of the class private.

2./Delete the copy constructor of the class.

3./Make a private static pointer that can point to the same class object (singleton class).

4./Make a public static method that returns the pointer to the same class object (singleton class).

--------------------------------------------------------------------------------------------------------------------

Singleton class can be instantiated by two methods:

1./Early initialization : In this method, class is initialized whether it is to be used or not. The main advantage of this method is its simplicity. You initiate the class at the time of class loading. 
Its drawback is that class is always initialized whether it is being used or not.

2./Lazy initialization : In this method, class in initialized only when it is required. It can save you from instantiating the class when you don’t need it. Generally, lazy initialization is used when we create a singleton class.

--------------------------------------------------------------------------------------------------------------------

Disavantage:

1./Hard to Subclass: Subclassing a Singleton can be challenging. Because the constructor is typically private, extending a Singleton requires additional care and may not follow standard inheritance patterns.

Code example C++:
#include <iostream>
using namespace std;

class Singleton {
private:
    // Singleton() = default;
    Singleton() {
        cout << "This is Singleton" << endl;
    }
    ~Singleton() {
        cout << "This is destructor of Singleton" << endl;
    }
    static Singleton *instance;
public:
    static Singleton *getInstance() {
        if(instance == nullptr) {
            instance = new Singleton();
        }
        return instance;
    }
    static void releaseSingleton() {
        if(instance != nullptr) {
            delete instance;
            instance = nullptr;
        }
    }
    void do_something() {
        cout << "Doing something" << endl;
    }

};
Singleton *Singleton::instance = nullptr;


int main()
{
    Singleton *obj1 = Singleton::getInstance();
    obj1->do_something();
    obj1->releaseSingleton();
    return 0;
}
