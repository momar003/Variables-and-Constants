# Variables and Constants

## Objective

The objective of this activity is to learn how to declare and use initialized and uninitialized variables in Assembly language. The program assigns the value **10** to `var1`, assigns the value **15** to `var2`, adds the two values together, and stores the result in the variable `result`.

---

## Flowchart

```text
+-------+
| Start |
+-------+
     |
     v
+----------------+
| Assign 10 to   |
| var1           |
+----------------+
     |
     v
+----------------+
| Assign 15 to   |
| var2           |
+----------------+
     |
     v
+----------------+
| Add var1       |
| and var2       |
+----------------+
     |
     v
+----------------+
| Store the sum  |
| in result      |
+----------------+
     |
     v
+-------+
|  End  |
+-------+
```

---

## Challenges

One challenge I encountered was understanding the difference between initialized and uninitialized variables in Assembly language. I also learned how to use CPU registers to perform arithmetic operations and store the result in memory. After reviewing the course materials, I was able to complete the program successfully.

---

## Assembly Source Code

```asm
section .text
    global _start

_start:
    ; Load var1 into eax
    mov eax, [var1]

    ; Add var2
    add eax, [var2]

    ; Store result
    mov [result], eax

    ; Exit program
    mov eax, 1
    int 0x80

segment .bss
    result resd 1

segment .data
    var1 dd 10
    var2 dd 15
```

---

## Explanation

* `var1` is an initialized variable with the value **10**.
* `var2` is an initialized variable with the value **15**.
* `result` is an uninitialized variable created in the `.bss` section.
* The program loads `var1` into the `EAX` register.
* It adds the value of `var2` to `EAX`.
* The final value (**25**) is stored in `result`.
* The program exits without displaying any output. The value of `result` can be verified using **gdb**.

---

## Expected Result

```
var1 = 10
var2 = 15
result = 25
```

When the program runs successfully, nothing is printed to the screen. Using **gdb**, the `result` variable should contain the value **25**.
