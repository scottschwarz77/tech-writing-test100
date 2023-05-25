In C, when passing variables to a function, we can either use call by value or call by reference. These approaches determine how the function interacts with the variables passed as inputs.

1. Call by Value:
When using call by value, the function receives a copy of the variable's value as its input. Any changes made to the variable within the function do not affect the original variable outside the function. Here's how it works:

- The function receives the value of the input variable.
- It operates on the local copy of the value.
- Any modifications made to the local copy are not reflected in the original variable.

Here's an example:

```c
void modifyValue(int x) {
    x = x + 10;
    printf("Inside function: %d\n", x);
}

int main() {
    int num = 5;
    printf("Before function call: %d\n", num);
    modifyValue(num);
    printf("After function call: %d\n", num);
    return 0;
}
```

Output:
```
Before function call: 5
Inside function: 15
After function call: 5
```

In the example above, the `modifyValue` function receives a copy of `num` as `x`. Even though `x` is modified within the function, the change does not affect the original `num` variable.

2. Call by Reference:
When using call by reference, the function receives the memory address (pointer) of the variable as its input. This allows the function to directly access and modify the original variable using the pointer. Here's how it works:

- The function receives the memory address (pointer) of the input variable.
- It uses the pointer to access and modify the original variable directly.
- Any modifications made to the variable are reflected in the original variable.

Here's an example:

```c
void modifyReference(int* ptr) {
    *ptr = *ptr + 10;
    printf("Inside function: %d\n", *ptr);
}

int main() {
    int num = 5;
    printf("Before function call: %d\n", num);
    modifyReference(&num);
    printf("After function call: %d\n", num);
    return 0;
}
```

Output:
```
Before function call: 5
Inside function: 15
After function call: 15
```

In the example above, the `modifyReference` function receives the memory address of `num` as `ptr`. By using the pointer `ptr` and dereferencing it with `*ptr`, the function can directly modify the original `num` variable.

In summary, call by value passes a copy of the variable's value to the function, while call by reference passes the memory address (pointer) of the variable, allowing the function to directly modify the original variable.
