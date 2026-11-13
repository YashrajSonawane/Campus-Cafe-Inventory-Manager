# Campus Cafe Inventory

This is a simple Java console program for a campus cafe. Staff can add products, see all products, check the total stock value and average price, restock a product, and make a copy of a product.

## How to run

```
javac *.java
java Main
```

To run the warm-up file:

```
java Warmup
```

## Questions

### 1. What did you predict for Warmup.java, and what did it actually print?

**My prediction:**
```
8 5 130
Two
```

**Actual output:**
```
7 5.0 -126
Two
Three
```

Some lines surprised me. `(int) 7.9` gave 7, not 8, because casting to int just cuts off the decimal part. It does not round. `d` printed 5.0 because it is a double, so Java shows the decimal point.

`(byte) 130` gave -126 because a byte can only store numbers from -128 to 127. When 130 does not fit, it "wraps around" to the negative side. The switch printed both "Two" and "Three" because there is no `break`, so Java keeps running the next cases after it finds a match.

### 2. What is the difference between the static variable totalProducts and the instance variable name?

`totalProducts` is static, so there is only one copy of it for the whole class. All products share it, and it counts how many products were created. `name` is an instance variable, so every product has its own name. For example, one product can be "Tea" and another can be "Samosa".

### 3. What does the copy constructor do, and why does changing p2.name not change p1.name?

The copy constructor makes a new product with the same name, price and quantity as another product. `p2` is a completely new object, separate from `p1`. So when we change `p2.name` to "Coffee", only `p2` changes, and `p1` is still "Tea".

### 4. Why does Java force you to write (int) average, and what happens to the decimal part?

A double can have a decimal part, but an int cannot. So changing a double to an int can lose some data. Java does not do this automatically, and we must write `(int)` to show we agree to lose the decimal. The decimal part is simply removed, so 12.75 becomes 12.
