# Factorial Recursion in JS
How factorial recursion actually works, with n = 3 as an example


## STACK 1
```js
 function factorial(3) {
   if (3 < 2) {
     return n
   }
 //this has to run factorial with (2) before it gives us the return
   return 3 * factorial(3 - 1)
 }
```

```
  ===========================================
  |         return 3 * factorial(2)         |
  ===========================================
```
**************************************************************************************
## STACK 2

```js
 function factorial(2) {
   if (2 < 2) {
     return n
   }
 //this has to run factorial with (1) before it gives us the return again
   return 2 * factorial(2 - 1)
 }
```

```
    ======================================
    |     return 2 * factorial(1)        |
    ======================================
  ===========================================
  |         return 3 * factorial(2)         |
  ===========================================
```
**************************************************************************************
## STACK 3

```js
 function factorial(1) {
   if (1 < 2) {
     return n
   }
```

```
 function stops here. Now, if we step backwards to our last stack...

        =============================
        |         return 1          |
        =============================
    ======================================
    |     return 2 * factorial(1)        |
    ======================================
  ===========================================
  |         return 3 * factorial(2)         |
  ===========================================
```
**************************************************************************************
## STACK 2


```js
 function factorial(2) {
   if (2 < 2) {
     return n
   }
   return 2 * 1
 //so the 1 is finally multiplied with the two, and returned, we are in stack 2, let's go back to stack 1
 }
```

```
    ======================================
    |            return 2 * 1            |
    ======================================
  ===========================================
  |         return 3 * factorial(2)         |
  ===========================================
```

**************************************************************************************
## STACK 1

```js
 function factorial(3) {
   if (3 < 2) {
     return n
   }
 //this finally allows us to return the two that was taken from the stack above, with the result being 6
   return 3 * 2
 }
```

```
  ===========================================
  |          return 3 * 2                   |
  ===========================================
```