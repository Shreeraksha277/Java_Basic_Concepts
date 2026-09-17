# ☕ Java OOP Concepts — Placement Revision

A simple Java program covering the important **OOP concepts** needed for placement preparation.

## 📌 Concepts Covered

* Class
* Object
* Instance Variable
* Static / Class Variable
* Non-Static Variable
* Constructor
* No-Argument Constructor
* Parameterized Constructor
* Constructor Overloading
* `this` Keyword
* Method
* Method Call
* Local Variable
* Static Method
* Method Overloading
* Inheritance
* Method Overriding

---

# 1️⃣ Complete Example

class Bottle {

    // ================= CLASS =================
    // A class is a blueprint/template used to create objects.


    // ================= INSTANCE VARIABLE / NON-STATIC VARIABLE =================
    // Every Bottle object gets its own separate copy of plastic.
    int plastic = 90;


    // ================= STATIC / CLASS VARIABLE =================
    // Only ONE copy of this variable is created for the entire Bottle class.
    // All Bottle objects share the same bottleCount.
    static int bottleCount = 0;


    // ================= NO-ARGUMENT CONSTRUCTOR =================
    // Constructor with no parameters.
    Bottle()
    {
        System.out.println("size is not passed, default value assigned");

        // Static variable is shared by all objects.
        bottleCount++;
    }


    // ================= PARAMETERIZED CONSTRUCTOR =================
    // Constructor with one parameter.
    Bottle(int plastic)
    {
        this.plastic = plastic;

        // STATIC VARIABLE:
        // Increases the common count whenever an object is created.
        bottleCount++;
    }


    // ================= CONSTRUCTOR OVERLOADING =================
    // Same constructor name but different parameters.
    Bottle(int plastic, String brand)
    {
        this.plastic = plastic;

        System.out.println("Obj has created for " + brand);

        // STATIC VARIABLE:
        // Shared by all Bottle objects.
        bottleCount++;
    }


    // ================= INSTANCE VARIABLE =================
    // Every Bottle object has its own separate count.
    int count = 0;


    // ================= METHOD =================
    // A method is a block of code that performs a particular task.
    void mould()
    {
        if (plastic < 1)
        {
            System.out.println("It is not possible");

            // RETURN:
            // Stops the execution of the method.
            return;
        }

        System.out.println("A bottle is created");

        plastic--;

        count++;
    }


    // ================= METHOD OVERLOADING =================
    // Same method name but DIFFERENT PARAMETERS.
    // This is called method overloading.

    void display()
    {
        System.out.println("Bottle display");
    }


    void display(String brand)
    {
        System.out.println("Brand: " + brand);
    }


    void display(String brand, int plastic)
    {
        System.out.println("Brand: " + brand + ", Plastic: " + plastic);
    }


    // ================= STATIC METHOD =================
    // A static method belongs to the CLASS, not to individual objects.
    // It can be called using the class name.
    static void showBottleCount()
    {
        System.out.println("Total Bottle objects created: " + bottleCount);
    }
}


// ======================================================
// INHERITANCE
// ======================================================
// PremiumBottle extends Bottle.
// Therefore PremiumBottle inherits properties and methods of Bottle.

class PremiumBottle extends Bottle
{

    // ================= METHOD OVERRIDING =================
    // Parent class has mould().
    // Child class creates its own version of mould().
    // Same method name + same parameters = overriding.

    @Override
    void mould()
    {
        System.out.println("Premium bottle is created");
    }
}


// ================= MAIN CLASS =================
public class Main
{

    // ================= MAIN METHOD =================
    // Program execution starts from main().
    public static void main(String[] args)
    {

        // ================= OBJECT CREATION =================
        // Creates Bottle object.
        // Calls Bottle(int, String) constructor.
        Bottle bislery = new Bottle(20, "bislery");


        // ================= OBJECT CREATION =================
        Bottle aqua = new Bottle(30, "aqua");


        // ================= OBJECT CREATION =================
        // Calls Bottle(int) constructor.
        Bottle nayasa = new Bottle(100);


        // ================= OBJECT CREATION =================
        // Calls Bottle() constructor.
        Bottle x = new Bottle();


        // ================= ACCESSING INSTANCE VARIABLE =================
        // bislery has its own plastic value.
        System.out.println(bislery.plastic);


        // ================= METHOD CALL =================
        bislery.mould();


        // ================= METHOD CALL =================
        bislery.mould();


        // ================= ACCESSING INSTANCE VARIABLE =================
        // bislery has its own count.
        System.out.println(bislery.count);


        // ================= OBJECT CREATION =================
        Bottle kinley = new Bottle(50, "kinley");


        // ================= ACCESSING INSTANCE VARIABLES =================
        // Each object has its own plastic value.
        System.out.println(bislery.plastic);
        System.out.println(aqua.plastic);
        System.out.println(nayasa.plastic);
        System.out.println(x.plastic);
        System.out.println(kinley.plastic);


        // ==================================================
        // STATIC VARIABLE
        // ==================================================
        // bottleCount is shared by ALL Bottle objects.
        // We access a static variable using the CLASS NAME.

        System.out.println(Bottle.bottleCount);


        // ==================================================
        // STATIC METHOD
        // ==================================================
        // Static method can be called using CLASS NAME.
        // No object is required.

        Bottle.showBottleCount();


        // ==================================================
        // METHOD OVERLOADING
        // ==================================================
        // Same display() method name but different parameters.

        bislery.display();

        bislery.display("Bisleri");

        bislery.display("Bisleri", 20);


        // ==================================================
        // METHOD OVERRIDING
        // ==================================================
        // Creating PremiumBottle object.
        PremiumBottle premium = new PremiumBottle();


        // Parent class has mould().
        // But PremiumBottle has overridden mould().
        // Therefore PremiumBottle's mould() executes.

        premium.mould();
    }
}
```

---

# 2️⃣ Quick Revision

## 🔹 Class

```java
class Bottle {
}
```

**Class = Blueprint / Template**

It defines the properties and behavior of objects.

---

## 🔹 Object

```java
Bottle bislery = new Bottle();
```

**Object = Actual instance of a class**

* `Bottle` → class
* `bislery` → reference variable
* `new Bottle()` → creates object

---

## 🔹 Instance Variable

```java
int plastic = 90;
```

A non-static variable belonging to an object.

Each object gets its **own copy**.

```text
bislery → plastic = 20
aqua    → plastic = 30
nayasa  → plastic = 100
```

---

## 🔹 Static / Class Variable

```java
static int bottleCount = 0;
```

Only **one copy** exists for the entire class.

All objects share it.

Access using:

```java
Bottle.bottleCount;
```

### Remember

```text
Non-static → Separate copy for each object

Static → One shared copy for the class
```

---

# 3️⃣ Constructor

A constructor is automatically called when an object is created.

```java
Bottle()
{
}
```

### Rules

* Same name as class
* No return type
* Called automatically
* Used to initialize objects

---

# 4️⃣ No-Argument Constructor

```java
Bottle()
{
}
```

Constructor with **zero parameters**.

Called by:

```java
Bottle x = new Bottle();
```

> Note: A compiler-provided default constructor is supplied only when you don't write any constructor yourself. The `Bottle()` above is a user-defined no-argument constructor.

---

# 5️⃣ Parameterized Constructor

```java
Bottle(int plastic)
{
    this.plastic = plastic;
}
```

Constructor that accepts parameters.

Example:

```java
Bottle b = new Bottle(100);
```

---

# 6️⃣ Constructor Overloading

Multiple constructors with the same class name but different parameters.

```java
Bottle()
Bottle(int plastic)
Bottle(int plastic, String brand)
```

### Formula

```text
Same constructor name
+
Different parameters
=
Constructor Overloading
```

---

# 7️⃣ `this` Keyword

```java
this.plastic = plastic;
```

Used to refer to the **current object**.

```text
this.plastic → instance variable
plastic      → constructor parameter
```

Think:

```text
current object's plastic = parameter plastic
```

---

# 8️⃣ Method

```java
void mould()
{
    ...
}
```

A method is a block of code that performs a particular task.

Calling it:

```java
bislery.mould();
```

---

# 9️⃣ Local Variable

A variable declared inside a method/block is a **local variable**.

Example:

```java
void mould()
{
    int x = 10;
}
```

Here:

```text
x → Local Variable
```

It is available only inside that method/block.

---

# 🔟 Static Method

```java
static void showBottleCount()
{
}
```

A static method belongs to the **class**.

Call it using:

```java
Bottle.showBottleCount();
```

No object is required.

---

# 1️⃣1️⃣ Method Overloading

```java
void display()
void display(String brand)
void display(String brand, int plastic)
```

Same method name but different parameters.

### Formula

```text
Same method name
+
Different parameters
=
Method Overloading
```

Example:

```java
bislery.display();
bislery.display("Bisleri");
bislery.display("Bisleri", 20);
```

---

# 1️⃣2️⃣ Inheritance

```java
class PremiumBottle extends Bottle
```

`PremiumBottle` inherits properties and methods from `Bottle`.

### Keyword

```java
extends
```

### Formula

```text
Parent Class
     ↓
   extends
     ↓
Child Class
```

---

# 1️⃣3️⃣ Method Overriding

Parent:

```java
class Bottle
{
    void mould()
    {
        System.out.println("A bottle is created");
    }
}
```

Child:

```java
class PremiumBottle extends Bottle
{
    @Override
    void mould()
    {
        System.out.println("Premium bottle is created");
    }
}
```

The child provides its own implementation of the parent's method.

### Formula

```text
Parent + Child
+
Same method name
+
Same parameters
+
Child provides new implementation
=
Method Overriding
```

---

# ⚡ Overloading vs Overriding

| Feature               | Overloading                    | Overriding                                 |
| --------------------- | ------------------------------ | ------------------------------------------ |
| Method name           | Same                           | Same                                       |
| Parameters            | **Different**                  | **Same**                                   |
| Classes               | Usually same class             | Parent + Child                             |
| Inheritance required? | No                             | Yes                                        |
| Purpose               | Multiple ways to call method   | Change parent behavior                     |
| Example               | `display()`, `display(String)` | `Bottle.mould()` → `PremiumBottle.mould()` |

### 🧠 Easy Trick

```text
OVERLOADING
↓
Different parameters


OVERRIDING
↓
Child changes parent's method
```

---

# ⚡ Static vs Non-Static

| Static                                | Non-Static                    |
| ------------------------------------- | ----------------------------- |
| Belongs to class                      | Belongs to object             |
| One shared copy                       | Separate copy for each object |
| `static int count`                    | `int plastic`                 |
| Access using class name               | Usually access using object   |
| Object not required for static method | Object generally required     |

### Remember

```text
STATIC
→ Class
→ One copy
→ Shared

NON-STATIC
→ Object
→ Separate copy
→ Individual
```

---

# 🎯 Placement Interview Questions

### Q1. What is a class?

A class is a blueprint or template used to create objects.

### Q2. What is an object?

An object is an instance of a class.

### Q3. What is a constructor?

A constructor is a special member of a class that is automatically called when an object is created.

### Q4. What is constructor overloading?

Having multiple constructors with different parameter lists.

### Q5. What is `this`?

`this` refers to the current object.

### Q6. What is a static variable?

A static variable belongs to the class and has one shared copy for all objects.

### Q7. What is method overloading?

Having methods with the same name but different parameter lists.

### Q8. What is method overriding?

When a child class provides its own implementation of a method inherited from the parent class.

### Q9. Is inheritance required for overloading?

**No.**

### Q10. Is inheritance required for overriding?

**Yes.**

### Q11. Difference between static and non-static?

Static belongs to the class and is shared; non-static belongs separately to each object.

---

# 🧠 One-Minute Revision

```text
CLASS
→ Blueprint

OBJECT
→ Instance of class

CONSTRUCTOR
→ Runs when object is created

NO-ARGUMENT CONSTRUCTOR
→ Constructor with 0 parameters

PARAMETERIZED CONSTRUCTOR
→ Constructor with parameters

CONSTRUCTOR OVERLOADING
→ Same constructor + different parameters

INSTANCE VARIABLE
→ Separate copy for every object

STATIC VARIABLE
→ One shared copy for the class

LOCAL VARIABLE
→ Variable inside method/block

THIS
→ Current object

METHOD
→ Performs a task

STATIC METHOD
→ Belongs to class

METHOD OVERLOADING
→ Same method + different parameters

INHERITANCE
→ Child gets properties/methods from parent

METHOD OVERRIDING
→ Child provides its own version of parent's method
```

# ⭐ Most Important Formulas

```text
Class → Blueprint

Object → Instance

new → Creates object

Constructor → Initializes object

this → Current object

static → Class + One shared copy

non-static → Object + Separate copy

Overloading → Same name + Different parameters

Overriding → Parent + Child + Same method + New implementation

extends → Inheritance
```
