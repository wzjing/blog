## Type-Qualifier

- const
```C
const int = 0; // 常量

const char *var = "Value"; // 常量指针：值不可变，但是地址可变
var = "New Value"; // Incorrect
*var = "New Value" // Correct

char * const var = "Value"; // 指针常量：指向的地址不可变， 但是值可变
var = "New Value" // Correct
*var = "New Value" // Incrrect
```
- volatile<br/>
```C
volatile int running; // 禁止编译器优化此变量
... // some code
running = 1; // Operation 1
...// some code
running = 0; // Operation 2
```
编译器可能会将此段代码优化，从而省略Operation 1，而将running直接赋值为0；添加volatile修饰符就是告诉编译器，不要优化此变量。

- restrict
```C
void foo(int *a, int *b, int *c) {
    *a = *c; // 加载右值 *c 到寄存器中
    *b = *c; // 无法判断 *c 是否可以从寄存器中直接读取，因此再次加载 *c 到寄存器中
}

void foo_restrict(int *__restrict__ a, int *__restrict__ b, int *__restrict c) {
    *a = *c; // 加载 *c 到寄存器中
    *b = *c; // 由于 __restrict__ 修饰符，*c 可以直接从已加载的寄存器中读取
}
```
有时候编译器无法判断某个变量是否可以优化，__restrict_修饰符可以告诉编译器这些变量是可以直接去优化的

- _Atomic
```C
#include <stdatmoic.h>
_Atomic int = 1;
_Atomic(int) = 1;
atomic_int = 1;
```