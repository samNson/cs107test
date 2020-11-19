# cs107test


## CMake
[CMake] (https://cliutils.gitlab.io/modern-cmake/chapters/intro/installing.html) is a cross-platform free and open-source software tool for managing the build process of software using a compiler-independent method. It supports directory hierarchies and applications that depend on multiple libraries.

Depenedencies:


#### How do you envision that a user will interact with your package? What should they import? How can they instantiate AD objects?

A user can include a single API header file to `NoetherAutoDiff.h` while linking to either the raw source files or linking to a compiled binary for the library.

Here is an example of the usage.
```
    const char* input = "sin(x)^cos(x-5/3+4^x*y/z)/tan(3*x)+exp(3*x-1)";
    map<char, double> inits = {{'x', 1.4}, {'y', 2.4}, {'z', 3.4}  };
    map<char, double> seeds = {{'x', 1}, {'y', 1}, {'z', 1} };
    int mode = 0;   // use mode = 0 for forward mode autodiff 
                    //     mode = 1 for reverse mode autodiff

    NoetherAutoDiff n = NoetherAutoDiff(input, 0, inits, seeds);
    n.print();
```

The *print* will output the follow:
```
    Evaluated at: 
    x=1.4  y=2.4  z=3.4  
    Numeric Value:
    f = 28.2899
    Derivatives: 
    df/dx = 78.4032
    df/dy = 0.154979
    df/dz = -0.109397
```

## Dependencies

## Download and Buile Instructions  
The *NoetherAutoDiff* library can be downloaded from the group github repo as follows:  
```git clone https://github.com/cs107-noether/cs107-FinalProject.git```

Once downloaded, follow these steps to configure and be able to use the library:
- From the command line, navigate into the NoetherAutoDiff library directory as follows  
    ```cd cs107-FinalProject``` 
- Build the libray source code using the provided build script as follows:  
     ```./build.sh```
- This will install the following dependencies onto your machine and also build the NoeitherAutoDiff
source code. 






A user will specify an input function as a string and pass that into the library along with the values at which to calculate the derivative, an seed vector will be optional. 



[![Build Status](https://travis-ci.com/samNson/cs107test.svg?branch=main)](https://travis-ci.com/samNson/cs107test)

[![Coverage Status](https://codecov.io/gh/samNson/cs107test/branch/main/graph/badge.svg?token=6da39f8f-bc16-4c10-b12d-ae1472059d90)](https://codecov.io/gh/samNson/cs107test)

Testing CI
