## 类型声明

### 自定义类型
相同的类型可以多次声明，但是在**同一作用域内**，不能重复定义。:warning:

```c
typedef int INT;
typedef unsigned INT;
```
> // error: typedef redefinition with different types

```c
typedef int INT
int main() 
{
    typedef unsigned INT;
}
```
### 函数声明
```c
void  foo();
void  foo(int);
```
```c
void  foo(void);
void  foo(int);
```
> error: conflicting types for 'foo'
```c
foo();
void  foo(int);
```
> error: conflicting types for 'foo'

```c
foo();
int  foo(int);
```
> warning: type specifier missing, defaults to 'int'
