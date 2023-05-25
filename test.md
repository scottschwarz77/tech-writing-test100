# Understanding Call-By-Value and Call-By-Reference in C

In C, when calling a function, you can pass input variables using call-by-value or call-by-reference. These approaches determine how the function will affect the variables passed as inputs.

## Call-by-value

When using call by value, the function receives a copy each input variable. Any changes made to these variable copies within the function do not affect the original variables that were passed to the function when it was called.

Following is an example of call-by-value. The `modifyValue` function receives a copy of `num` as `x`. Even though `x` is modified within the function, the change does not affect the `num` variable that is passed as input to the function.

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

2. Call by Reference:

A function that is called using call by reference can indirectly modify input variables that were passed to the function.

Following is an example of call-by-reference. The call to the `modifyReference` function sends the memory address of `num` (using `&num`). This address is copied into the `ptr` variable, which is defined in the `modifyReference` function definition. By dereferencing `ptr` (using `*ptr`), the function modifies the value at the address where `ptr` points. Because the address of `num` and `ptr` are the same, the function indirectly modifies the value of `num`.

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
