Boost Python

Links
https://www.boost.org/doc/libs/1_67_0/libs/python/doc/html/tutorial/tutorial/exposing.html
https://www.boost.org/doc/libs/1_42_0/libs/python/doc/v2/reference_existing_object.html
Example #1
Save code with name hello.cpp
   #include <boost/python/module.hpp>  
   #include <boost/python/def.hpp>  
   using namespace std;  
   using namespace boost::python;  
   int helloWorld() {          
         cout << "Hello world!" << endl;
         return 0;  
   }
   BOOST_PYTHON_MODULE(hello) {
         def("hello_world", helloWorld);  
   }
Run the Program
Code save with name hello.cpp
Run the program
g++ -fpic -shared -o hello.so -Wl,-soname,"hello.so" hello.cpp -I/usr/include/python2.7 -L/usr/local/lib  -lboost_python
  python
  >>> import hello
  >>> print libhello.hello_world()
  Hello world!
  0
Example #2
Save code with name hello.cpp
 #include <boost/python/module.hpp>
 #include <boost/python/def.hpp>
 using namespace std;
 using namespace boost::python;
 #include <iostream>
 struct World
 {
     void set(std::string msg) { this->msg = msg; }
     std::string greet() { return msg; }
     std::string msg;
 };
 #include <boost/python.hpp>
 using namespace boost::python;
 BOOST_PYTHON_MODULE(hello)
 {
     class_<World>("World")
         .def("greet", &World::greet)
         .def("set", &World::set)
         ;
 }
Run the Program
Code save with name hello.cpp
Run the program
g++ -fpic -shared -o hello.so -Wl,-soname,"hello.so" hello.cpp -I/usr/include/python2.7 -L/usr/local/lib -lboost_python
 python
 >>> import hello
 >>> planet = hello.World()
 >>> planet.set('howdy')
 >>> planet.greet()

Example #3
Save code with name hello.h
 #include <iostream>
 struct World
 {
     void set(std::string msg);
     std::string greet();
     std::string msg;
 };
Save code with name hello.cpp
 #include <iostream>
 #include "hello.h"
 void World::set(std::string msg) {
     this->msg = msg;
 }
 std::string World::greet() {
     return msg;
 }
Save code with name hello_ext.cpp
 #include <boost/python/module.hpp>
 #include <boost/python/def.hpp>
 #include <boost/python.hpp>
 #include "hello.h"
 using namespace std;
 using namespace boost::python;
 BOOST_PYTHON_MODULE(hello)
 {
     class_<World>("World")
         .def("greet", &World::greet)
         .def("set", &World::set)
         ;
 }
Compile the code
g++ -fpic -shared -o hello.so -Wl,-soname,"hello.so" hello.cpp hello_ext.cpp -I/usr/include/python2.7 -L/usr/local/lib -lboost_python
   python
   >>> import hello 
   >>> planet = hello.World() 
   >>> planet.set('howdy')
   >>> planet.greet()
   'howdy'
   
Pybind11
Link
https://pybind11.readthedocs.io/en/master/basics.html#compiling-the-test-cases
