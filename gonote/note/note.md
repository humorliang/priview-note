- 1、简单介绍一下Golang。
谷歌开发的一种系统编程语言。它具有内置的垃圾收集机制并支持并发。代码可以编译成单个可执行二进制文件，不需要添加库或运行时环境即可在服务器上执行

- 2、Golang是否可以声明一个类？
    是的，Golang用一种独特的类型接口方式实现类。
    详情请移步：如何声明一个Golang类

- 3、Go是否支持泛型？（陷阱问题）
    否，泛型是方便的，但是它们在类型系统和运行时的复杂性方面付出了代价。

- 4、从GitHub或者bitbucket导入代码的命令是什么？
```go
    go get 和 go install 命令
```
- 5、一个通过make()命令创建的缓冲区被分配了一块内存后。如何销毁缓冲区并收回内存？
```go
buffer = nil
在运行时，buffer = nil将启动垃圾回收。
```
- 6、以下内容表示什么？（陷阱问题）
```go
var num int  //（整型变量）
var prt * int  //int类型（指针）
num＝10   //（赋值10到变量num）
ptr = &num //（指针 指向 变量num的内存地址）
```
- 7、切片和数组的显著差异是什么？
数组大小是固定的，切片大小不是。切片在运行时可以动态地增加或减少切片的大小，但数组不可以。切片类似于链表，可以向切片push，pop数据，实现FIFO，LIFO。使用了内置的添加、复制功能对切片操作。

- 8、cap()和len()函数的区别是什么？
```go
len()返回切片中的元素个数。
cap()返回切片的容量即切片可以容纳的元素数量。
```

- 9、哈希表或哈希映射允许快速查找。GO如何实现哈希映射？（陷阱问题）
```go
哈希表在Golang中相当于map，也就是哈希映射。
hash-table := make(map[string]string)
```
- 10、以下哪些函数，变量，标识符可以被导出，或者可以被外部函数调用？（陷阱问题）
```go
var aName // private, 私有，只在函数或声明范围内可访问
var BigBro // public 公有，可导出
var 123abc // 非法
var 爱 = "love" // public 公有，可导出
func (p *Person) SetEmail(email string) { 
    // public 因为SetEmail()函数以大写字母开头
    p.email = email
}
func (p Person) email() string { 
    // private 私有，因为email()函数以小写字母开头
    return p.email
}
```
- 11. 我们来简要说一下go的值类型和引用类型， 这很重要。
```go
    值类型有：    int float bool string array
    引用类型有：  slice map channel   (对内存中的数据块引用)
```