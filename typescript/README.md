# Typescript

These personal annotations are coming from Stephen Grider's course. Check it out [here](https://www.udemy.com/course/typescript-the-complete-developers-guide/).

---

# Section 1 - Getting Started with Typescript

- Catch errors during development
- Type annotations
- Only active during development
- No performance optimization

---

# Section 2 - What is a Type System?

**Type**
> Easy way to refer to the different properties + functions that a value has

**Primitive Types**
  - number
  - boolean
  - void
  - undefined
  - string
  - symbol
  - null

**Object Types**
  - functions
  - arrays
  - classes
  - objects

> We can trick ts compiler into thinking object types are different types

---

# Section 3 - Type Annotations in Action

**Type Annotations + Type Inference**
  - Variables
  - Functions
  - Objects

**Type annotation**
  - Code we add to tell Typescript what  type of value a variable will refer to

**Type inference**
  - Typescript tries to figure out what type of value a variable refers to

**Variable declaration vs variable initialization**

Every time we have the any type, typescript just can't do its job, because it helps us catch errors in development only because of types

---

# Section 4 - Annotations With Functions and Objects

**Type annotation for functions**
  - Code we add to tell Typescript what type of arguments a function will receive and what type of values it will return

**Type inference for functions**
  - Typescript tries to figure out what type of value a function will return

We'll always use type annotation for parameters and return values, because although in the case of return values TS can infer what the type is, it's only related to the type itself, not to the logic. So we can return anything we'd like and it's not going to complain.

If we want to make a function that doesn't return anything, we call use "void" as a return type.
  - In fact, if we use void we can also return null or undefined.

We also can return the type "never", so it really won't return anything at all - never. 

---

# Section 5 - Mastering Typed Arrays

**Typed Arrays** - Arrays where each element is some consistent type of value

**Where to use typed arrays?** - Any time we need to represent a collection of records with some arbitrary sort order

---

# Section 6 - Tuples in Typescript

---

# Section 7 - The All-Important Interface

**Interfaces + Classes =** How we get really strong code reuse in TS

**Interfaces** - Creates a new type, describing the property names and value types of an object

- If we're using an interface, it doesn't matter if we have additional properties. It's only going to check if it has the list of properties inside of the interface.

- Use diagrams to structure the explanations on github ------ always showing the original creators***********

- General Strategy for Reusable Code in TS
  - Create functions that accept arguments that are typed with interfaces
  - Objects/Classes can decide to "implement" a given interface to work with a function 

---

# Section 8 - Building Functionality with Classes

**Classes**
> Blueprint to create an object with some fields (values) and methods (functions) to represent a 'thing'.

**Modifiers**
  - **Public** - This method can be called any where, any time
  - **Private** - This method can only be called by other methods in this class
      - We don't use it because of security concerns (it doesn't add any kind of security layer on top of it). We use it to protect a method from being called outside of a class, because of its side effects, or other developers who might actually use it without understanding it properly.
  - Protected - This method can be called by other methods in this class, or by other methods in child classes


A solution to keep us from rewriting the same properties of a value, if to use "public" in before the params of a constructor function in a class. 

Those modifiers apply as well to fields

---

> #### ***TIP:*** use private inside of a constructor parameter to initialise a prop inside of the class easily:
```typescript
interface IUsersRepository {}

// Before
export class CreateUserRepositoryBefore {
  private usersRepository: IUsersRepository;
  
  constructor (
    usersRepository: IUsersRepository 
  ) {
    this.usersRepository = usersRepository;
  };
}

// After
export class CreateUserRepository {
  constructor (
    private usersRepository: IUsersRepository 
  ) {};
}
```
