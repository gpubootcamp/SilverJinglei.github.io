# C lang Design Pattern

## Overview

c lang only have [struct] => simulate [class] in c++

c lang don’t has:

1. inheritance
2. template <T>
3. member function

## GOF

> GOF use class (type) and object (instance) => play Pattern
>
> Therefore, c-lang only use [instance] way is enough.(class is no way)

### Assembly Instance => Gen Instance

>  Strategy Use Instance to create instance
>
>  Use instance gen strategy (Build, Factory Method, Prototype) => simulate inheritance

#### Build

#### Factory Method

#### Prototype (Clone)

## Inheritance

Has a => (replace) is a

```c
typedef struct parent
{
    
}parent;

typedef struct child
{
    parent* base;
    child* this;
}child;


```

# Terminate Switch
Marcro dispatch switch case

```c
switch(enum)
{
    case e1:
    case e2:
    default:
}

=>

#define HandleEnum(x) x##_Func(x)

HandleEnum(enum);

```
