## C++ Style Guide

Follow the c++ style guide when writing software but also when reviewing. 

# Files and folder structure

```
project-root/
├── CMakeLists.txt
├── include/
│   └── class_name/
│       └── class_name.h
├── src/
│   └── main.cpp
│   └── class_name
│       └── class_name.cpp
│       └── class_name_functionality.cpp
├── tests/
│   └── test_main.cpp
└── build/
```

 * Try to divide your source files into separate files, separate by functionality. e.g.

```
class_name.cpp // contains constructor and deconstructor 
class_name_threads.cpp // contains all the thread functions 
class_name_init.cpp // contains functions for initialization
```

# Naming conventions
* File names, folder names should all be snake_case
* Class/structs names should be PascalCase
* Variables should be snake_case , Class variables should end with _ , snake_case_
* Function names should be camelCase
* Private variables should be declared first without the privatetag, then public functions, protected functions (if there are any), then private functions.

```c++
class MyClass{
  int private_value_;

  public:
    MyClass(int value);

  private:
    void privateFunction();
};
```

* Struct variables should not end with an underscore because its values are public.

```c++
struct MyStruct {
  int value;
}
```

* Use descriptive names, it should be clear from the variable or function name what the variable represents and the function will do. 

```c++
// Unclear what will be calculated, naming of a and b unclear
double calculate(Point a, Point b); 

// Clear that the distance between point_a and point_b will be calculated
double calculateDistance(Point point_a, Point point_b);
```

* Avoid abbreviations, they are not always clear to the reader, or they might be very domain specific.
* Avoid single letter variable names, unless they make sense what they mean.

```c++
point.x; 
point.y; 
point.z; // In this case x, y, z are mathmatical variables that are very commonly used 

int i; // Does not clearly indicate what it represents
int index; // Makes it clear that the variable indicates an index
```

# Const 
* Use ```const``` explicitly to indicate a variable is not going to be changed, including in function parameters.

```c++
// The caller may assume value will not be changed by the function even 
// though in this case the int will be copied
void fun(const int value) { 
}
```

* Use ```const``` when returning containers by reference to prevent caller from manipulating the data.

```c++
// Returning vector by reference, using const prevents caller from doing 
// class_name.getVector().push_back(value);
const std::vector<int> ClassName::getVector&() { 
  return vector_data_;
}
```

* Make ```variables``` ```const``` when they are not meant to be changed, preventing accidentally reassigning the value.

```c++
const float offset = 0.1f; // Make sure offset value cannot change
offset = 0.2f; // This will result in compile error
```

# Enums
* Enums should be PascalCase
* Enum values should be CAPITAL_SNAKE_CASE

```c++
enum class State {
  INIT,
  RUN,
  STOP
};
```

# Switch statements

* Avoid using the ```default``` case when using a ```enum``` in a switch, the compiler will not warn if a case is not implemented, adding new enum values might result in not handling those cases since they would be handled as default.

```c++
enum class State {INIT, RUN, STOP};
State state_{State::INIT};

// This will compile, but State RUN and STOP are not handled, they will always go to the default case
  switch (state_) {
  case State::INIT: {
      break;
  } 
  default: {
    break;
  }
}
```

# Nested statement

* Try to prevent nested statements as much as possible to increase readability.

```c++
// Do not use
 if (value1) {

   if (value2) {
       
        if (value3) {
          // do something here
        }
   }
 }

 // Do try to break up your if statements to prevent deep nested code
 if (not value1) {
   return;
 }

 if (not value2) {
   return;
 }

 if (value3) {
   // do something here
 }
```

# Header files 

* Use include guards

```c++
#ifndef H_HEADER_FILENAME__
#define H_HEADER_FILENAME__

#endif
```

* Use < > for header files outside your project.
* Use " " for header files that are located in your project. 

```c++
#include <iostream> // Outside project header file
#include "class_name/class_name.h" // Inside project header file
```

* Define header files where needed, if header file only needed in specific source file include it in the source not the header file.

# Modern c++ practices 

* Prefer ```nullptr``` over ```NULL``` or ```0```.
* Use ```override``` for virtual function overrides. 
* Prefer ```unique_ptr``` and ```shared_ptr``` over raw pointers.
* Do not use ```using namespace```

# White lines 

* Before statements if while for etc, add a white line above it and after the closing brackets.

```c++
int value = 1;
// empty white line
if (value == 1) {
}
// empty white line
return;
```

* Use white lines to separate blocks of code for readability.

# Brackets 

* Use brackets also on single line statements for clearer readability. 

```c++
// Don't do this 
if (value == true)  
  std::cout << "value was true\n";

// Do 
if (value == true) {
  std::cout << "value was true\n";
}
```

* Adding brackets also allows for less error prone adding of new code into the statemens.

```c++
if (value == true) 
  std::cout << "value was true\n";
  std::cout << "extra print statement\n"; // this is now not part of the if statement
```
