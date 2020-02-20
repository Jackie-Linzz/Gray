#Thoughts and Design

As for now, My favorite language is C++, but it is too complex. Scheme is the most elegant language I have ever seen, but it is not industrial. Python is like glue and it is easy to use, but it is too slow. CLOS is a powerful object system, but its syntax is not that natural. I haven't used go and julia. Maybe I would have a try sometime. So basically, none of the existing programming language can make me satisfied.
  

Features:

1. Gray supports multiple programming paradiam. It supports procedure-oriented programming, object-oriented programming, generic programming.

2. code is the same as data. It can also be manipulated, just like macro in lisp.

3. It support garbage collection. It is an option. User can enable it or disable it.

4. User can program on two layers. The upper layer focuses on elegance. The lower layer focuses on performance.

5. The template syntax in C++ looks kind of ugly. Better find an elegant way.

6. Its core stays at a minimum. It can be extended easily. (optional)

7. It could be both static and dynamic. (optional)


##Grammr
Grammar of Gray is mostly inspired by C++ and lisp. The upper layer grammar should be elegant.

###Grammar about macro
Code is also first class, like function and data class. Maybe its form is like
    
`quote(...code is in here...)`, or  `code(...code is here...)`
    
or like
    
    quote { code is here }, or code { code is here }

"Evaluation of the macro call begins like evaluation of a function call except for one crucial difference: the macro arguments are the actual expressions appearing in the macro call. They are not evaluated before they are given to the macro definition. By contrast, the arguments of a function are results of evaluating the elements of the function call list." (from emacs lisp)

Symbol is needed because of above reason.

"Having obtained the arguments, Lisp invokes the macro definition just as a function is invoked. The argument variables of the macro are bound to the argument values from the macro call, or to a list of them in the case of a &rest argument. And the macro body executes and returns its value just as a function body does.

The second crucial difference between macros and functions is that the value returned by the macro body is an alternate Lisp expression, also known as the expansion of the macro. The Lisp interpreter proceeds to evaluate the expansion as soon as it comes back from the macro.

Since the expansion is evaluated in the normal manner, it may contain calls to other macros. It may even be a call to the same macro, though this is unusual" from emacs lisp.

well, the macro call will first expand, generate code, and then the expansion is evaluated or executed.

    

  
