## helloword

```go
package main
//第一行包名
import "fmt"
//第二行用fmt包
func main() {
  //程序执行函数
    /* 这是我的第一个简单的程序 */
    fmt.Println("Hello, World!")
}
```



## Go语言基础语法

标识符

```
mahesh   kumar   abc   move_name   a_123
myname50   _temp   j   a23b9   retVal
```

以下是无效的标识符：

- 1ab（以数字开头）
- case（Go 语言的关键字）
- a+b（运算符是不允许的）

字符串的链接

```go
package main
import "fmt"
func main() {
    fmt.Println("Google" + "Runoob")
}
```

关键字

| break    | default     | func   | interface | select |
| -------- | ----------- | ------ | --------- | ------ |
| case     | defer       | go     | map       | struct |
| chan     | else        | goto   | package   | switch |
| const    | fallthrough | if     | range     | type   |
| continue | for         | import | return    | var    |

| append | bool    | byte    | cap     | close  | complex | complex64 | complex128 | uint16  |
| ------ | ------- | ------- | ------- | ------ | ------- | --------- | ---------- | ------- |
| copy   | false   | float32 | float64 | imag   | int     | int8      | int16      | uint32  |
| int32  | int64   | iota    | len     | make   | new     | nil       | panic      | uint64  |
| print  | println | real    | recover | string | true    | uint      | uint8      | uintptr |

声明要空格

```
fruit = apples + oranges; 
```

格式化字符串

```go
package main

import (
    "fmt"
)

func main() {
   // %d 表示整型数字，%s 表示字符串
    var stockcode=123
    var enddate="2020-12-31"
    var url="Code=%d&endDate=%s"
    var target_url=fmt.Sprintf(url,stockcode,enddate)
    fmt.Println(target_url)
}
```

## go语言数据类型

布尔

数字

例如：int、uint 和 uintptr。

float32  complex64

byte、rune、uint、int、uintptr

字符串

派生类型

- (a) 指针类型（Pointer）
- (b) 数组类型
- (c) 结构化类型(struct)
- (d) Channel 类型
- (e) 函数类型
- (f) 切片类型
- (g) 接口类型（interface）
- (h) Map 类型



## go语言变量

```go
var identifier type
//一个与多个
var identifier1, identifier2 type

package main
import "fmt"
func main() {
    var a string = "Runoob"
    fmt.Println(a)

    var b, c int = 1, 2
    fmt.Println(b, c)
}

package main
import "fmt"
func main() {

    // 声明一个变量并初始化=赋值
    var a = "RUNOOB"
    fmt.Println(a)

    // 没有初始化就为零值
    var b int
    fmt.Println(b)

    // bool 零值为 false
    var c bool
    fmt.Println(c)
}

package main

import "fmt"

func main() {
    var i int
    var f float64
    var b bool
    var s string
    fmt.Printf("%v %v %v %q\n", i, f, b, s)
}
0 0 false ""


ackage main
import "fmt"

var x, y int
var (  // 这种因式分解关键字的写法一般用于声明全局变量
    a int
    b bool
)

var c, d int = 1, 2
var e, f = 123, "hello"

//这种不带声明格式的只能在函数体中出现
//g, h := 123, "hello"

func main(){
    g, h := 123, "hello"
    fmt.Println(x, y, a, b, c, d, e, f, g, h)
}
0 0 0 false 1 2 123 hello 123 hello
```

​	

## go语言常量

```go
const ast[int] = value
package main

import "fmt"

func main() {
   const LENGTH int = 10
   const WIDTH int = 5  
   var area int
   const a, b, c = 1, false, "str" //多重赋值

   area = LENGTH * WIDTH
   fmt.Printf("面积为 : %d", area)
   println()
   println(a, b, c)  
}
//常量可以用len(), cap(), unsafe.Sizeof()函数计算表达式的值


iota
package main

import "fmt"

func main() {
    const (
            a = iota   //0
            b          //1
            c          //2
            d = "ha"   //独立值，iota += 1
            e          //"ha"   iota += 1
            f = 100    //iota +=1
            g          //100  iota +=1
            h = iota   //7,恢复计数
            i          //8
    )
    fmt.Println(a,b,c,d,e,f,g,h,i)
}
//0 1 2 ha ha 100 100 7 8

package main

import "fmt"
const (
    i=1<<iota
    j=3<<iota
    k
    l
)

func main() {
    fmt.Println("i=",i)
    fmt.Println("j=",j)
    fmt.Println("k=",k)
    fmt.Println("l=",l)
}
//简单表述:

i=1：左移 0 位，不变仍为 1。
j=3：左移 1 位，变为二进制 110，即 6。
k=3：左移 2 位，变为二进制 1100，即 12。
l=3：左移 3 位，变为二进制 11000，即 24。

```



## 运算

位运算符

```go
package main

import "fmt"

func main() {

   var a uint = 60      /* 60 = 0011 1100 */  
   var b uint = 13      /* 13 = 0000 1101 */
   var c uint = 0          

   c = a & b       /* 12 = 0000 1100 */
   fmt.Printf("第一行 - c 的值为 %d\n", c )

   c = a | b       /* 61 = 0011 1101 */
   fmt.Printf("第二行 - c 的值为 %d\n", c )

   c = a ^ b       /* 49 = 0011 0001 */
   fmt.Printf("第三行 - c 的值为 %d\n", c )

   c = a << 2     /* 240 = 1111 0000 */
   fmt.Printf("第四行 - c 的值为 %d\n", c )

   c = a >> 2     /* 15 = 0000 1111 */
   fmt.Printf("第五行 - c 的值为 %d\n", c )
}
```

## 语言条件语句

```go
//if
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 10
 
   /* 使用 if 语句判断布尔表达式 */
   if a < 20 {
       /* 如果条件为 true 则执行以下语句 */
       fmt.Printf("a 小于 20\n" )
   }
   fmt.Printf("a 的值为 : %d\n", a)
}

//if-else
package main

import "fmt"

func main() {
   /* 局部变量定义 */
   var a int = 100;
 
   /* 判断布尔表达式 */
   if a < 20 {
       /* 如果条件为 true 则执行以下语句 */
       fmt.Printf("a 小于 20\n" );
   } else {
       /* 如果条件为 false 则执行以下语句 */
       fmt.Printf("a 不小于 20\n" );
   }
   fmt.Printf("a 的值为 : %d\n", a);

}

//if嵌套
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 100
   var b int = 200
 
   /* 判断条件 */
   if a == 100 {
       /* if 条件语句为 true 执行 */
       if b == 200 {
          /* if 条件语句为 true 执行 */
          fmt.Printf("a 的值为 100 ， b 的值为 200\n" );
       }
   }
   fmt.Printf("a 值为 : %d\n", a );
   fmt.Printf("b 值为 : %d\n", b );
}

//switch
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var grade string = "B"
   var marks int = 90

   switch marks {
      case 90: grade = "A"
      case 80: grade = "B"
      case 50,60,70 : grade = "C"
      default: grade = "D"  
   }

   switch {
      case grade == "A" :
         fmt.Printf("优秀!\n" )    
      case grade == "B", grade == "C" :
         fmt.Printf("良好\n" )      
      case grade == "D" :
         fmt.Printf("及格\n" )      
      case grade == "F":
         fmt.Printf("不及格\n" )
      default:
         fmt.Printf("差\n" );
   }
   fmt.Printf("你的等级是 %s\n", grade );      
}

//switch 判断type
package main

import "fmt"

func main() {
   var x interface{}
     
   switch i := x.(type) {
      case nil:  
         fmt.Printf(" x 的类型 :%T",i)                
      case int:  
         fmt.Printf("x 是 int 型")                      
      case float64:
         fmt.Printf("x 是 float64 型")          
      case func(int) float64:
         fmt.Printf("x 是 func(int) 型")                      
      case bool, string:
         fmt.Printf("x 是 bool 或 string 型" )      
      default:
         fmt.Printf("未知型")    
   }  
}

// fallthrough强制执行下一句
package main

import "fmt"

func main() {

    switch {
    case false:
            fmt.Println("1、case 条件语句为 false")
            fallthrough
    case true:
            fmt.Println("2、case 条件语句为 true")
            fallthrough
    case false:
            fmt.Println("3、case 条件语句为 false")
            fallthrough
    case true:
            fmt.Println("4、case 条件语句为 true")
    case false:
            fmt.Println("5、case 条件语句为 false")
            fallthrough
    default:
            fmt.Println("6、默认 case")
    }
}

//elect
select {
  case <- channel1:
    // 执行的代码
  case value := <- channel2:
    // 执行的代码
  case channel3 <- value:
    // 执行的代码

    // 你可以定义任意数量的 case

  default:
    // 所有通道都没有准备好，执行的代码
}
每个 case 都必须是一个通道
所有 channel 表达式都会被求值
所有被发送的表达式都会被求值
如果任意某个通道可以进行，它就执行，其他被忽略。
如果有多个 case 都可以运行，select 会随机公平地选出一个执行，其他不会执行。
否则：
如果有 default 子句，则执行该语句。
如果没有 default 子句，select 将阻塞，直到某个通道可以运行；Go 不会重新对 channel 或值进行求值。

package main

import (
    "fmt"
    "time"
)

func main() {

    c1 := make(chan string)
    c2 := make(chan string)

    go func() {
        time.Sleep(1 * time.Second)
        c1 <- "one"
    }()
    go func() {
        time.Sleep(2 * time.Second)
        c2 <- "two"
    }()

    for i := 0; i < 2; i++ {
        select {
        case msg1 := <-c1:
            fmt.Println("received", msg1)
        case msg2 := <-c2:
            fmt.Println("received", msg2)
        }
    }
}
//select 是随机执行的不是循环检测，是为了避免饥饿问题，我给你改了改

```

## 循环

![image-20230823100417331](/Users/kad/Library/Application Support/typora-user-images/image-20230823100417331.png)

![image-20230823103654002](/Users/kad/Library/Application Support/typora-user-images/image-20230823103654002.png)



## 函数



![image-20230823104046921](/Users/kad/Library/Application Support/typora-user-images/image-20230823104046921.png)

![image-20230823104604022](/Users/kad/Library/Application Support/typora-user-images/image-20230823104604022.png)

![image-20230823104726516](/Users/kad/Library/Application Support/typora-user-images/image-20230823104726516.png)

![image-20230823104849613](/Users/kad/Library/Application Support/typora-user-images/image-20230823104849613.png)

-匿名变量

比大小

![image-20230823105002325](/Users/kad/Library/Application Support/typora-user-images/image-20230823105002325.png)

![image-20230823105426202](/Users/kad/Library/Application Support/typora-user-images/image-20230823105426202.png)

## 值传递、地址传递

![image-20230823105737355](/Users/kad/Library/Application Support/typora-user-images/image-20230823105737355.png)

![image-20230823105858393](/Users/kad/Library/Application Support/typora-user-images/image-20230823105858393.png)

![image-20230823110047042](/Users/kad/Library/Application Support/typora-user-images/image-20230823110047042.png)

![image-20230823110525864](/Users/kad/Library/Application Support/typora-user-images/image-20230823110525864.png)



## 递归函数

递归相加

![image-20230823111932609](/Users/kad/Library/Application Support/typora-user-images/image-20230823111932609.png)



## defer

![image-20230823112103196](/Users/kad/Library/Application Support/typora-user-images/image-20230823112103196.png)

defer多条逆序



## 函数本质探讨

![image-20230823112914256](/Users/kad/Library/Application Support/typora-user-images/image-20230823112914256.png)



## 匿名函数

![image-20230823121110220](/Users/kad/Library/Application Support/typora-user-images/image-20230823121110220.png)

不给他名字复制给变量





## 回调函数



![image-20230823121605131](/Users/kad/Library/Application Support/typora-user-images/image-20230823121605131.png)

![image-20230823121937231](/Users/kad/Library/Application Support/typora-user-images/image-20230823121937231.png)



## 闭包

![image-20230823122350850](/Users/kad/Library/Application Support/typora-user-images/image-20230823122350850.png)



## gin

起步

```go
package main

import "github.com/gin-gonic/gin"

func main() {
    r := gin.Default()
    r.GET("/ping", func(c *gin.Context) {
       c.JSON(200, gin.H{
          "gin": "66666",
       })
    })
    r.GET("/keaiduo", func(c *gin.Context) {
       c.JSON(200, gin.H{
          "gin": "66666",
       })
    })
    r.Run(":8080") // 监听并在 0.0.0.0:8080 上启动服务
}
```

![image-20230824134141618](/Users/kad/Library/Application Support/typora-user-images/image-20230824134141618.png)

![image-20230824172146051](/Users/kad/Library/Application Support/typora-user-images/image-20230824172146051.png)

![image-20230824172838769](/Users/kad/Library/Application Support/typora-user-images/image-20230824172838769.png)

![image-20230824172922727](/Users/kad/Library/Application Support/typora-user-images/image-20230824172922727.png)

![image-20230824173657669](/Users/kad/Library/Application Support/typora-user-images/image-20230824173657669.png)

![image-20230824173911686](/Users/kad/Library/Application Support/typora-user-images/image-20230824173911686.png)



## get post delete put



![image-20230824175223676](/Users/kad/Library/Application Support/typora-user-images/image-20230824175223676.png)

传参

![image-20230824175919517](/Users/kad/Library/Application Support/typora-user-images/image-20230824175919517.png)

defaultquary，没有参数默认传一个值

post请求，用from接受处理数据

![image-20230824180818191](/Users/kad/Library/Application Support/typora-user-images/image-20230824180818191.png)

bind模式获取参数和表单认证

![image-20230824211732319](/Users/kad/Library/Application Support/typora-user-images/image-20230824211732319.png)

![image-20230824212127108](/Users/kad/Library/Application Support/typora-user-images/image-20230824212127108.png)



## gin七米

### RESTful API

![img](https://apifox.com/blog/content/images/2023/02/6784ff0e-25ac-45d3-bdaa-13448b274ec2.png)

##### Uniform Interface（统一接口）

 

- 就像我们上面两幅图看到的 API，这是最直观的特征，是 REST 架构的核心，统一的接口对于 RESTful 服务非常重要。客户端**只需要关注实现接口**就可以，接口的**可读性加强**，使用人员**方便调用**。
- RESTful API 通过 URL 定位资源，并通过 HTTP 方法操作该资源，对资源的操作包括获取、创建、修改和删除，这些操作正好对应 HTTP 协议提供的 GET、POST、PUT 和 DELETE 方法。  

​    GET：获取资源信息。  

​    POST：创建一个新资源。  

​    PUT：更新已有的资源。  

​    DELETE：删除已有的资源。

- 在一个完全遵循 RESTful 的团队里，后端只需要告诉前端 /users 这个 API，前端就应该知道:

​    获取所有用户：GET /users  

​    获取特定用户：GET /users/{id}  

​    创建用户：POST /users  

​    更新用户：PUT /users/{id}  

​    删除用户：DELETE /users/{id}

- 当 API 数量非常多，系统非常复杂时，RESTful 的好处会越来越明显。理解系统时，可以直接围绕一系列资源来理解和记忆。

##### Client-Server（客户端和服务端分离）

- 它意味着客户端和服务器是**独立的**、可以**分离的**。
- 客户端是负责请求和处理数据的组件，服务器是负责**存储数据**和**处理请求**的组件。
- 这两个组件之间**通过一组约定来协作**，以便客户端能够获取所需的数据。

##### Statelessness（无状态）

- 它指的是每个请求都是**独立的**，**没有前后关系**。服务器不保存客户端的状态信息，并且每个请求都必须包含所有所需的信息。
- 这样做的好处是可以使每个请求变得**简单**，**容易理解**和**处理**，并且可以**更容易地扩展和维护**。
- 例如，假设你在登录一个网站，你需要在登录界面输入用户名和密码通过接口获取到了 token 。接下来的所有请求都需要携带上这个 token 而不是系统在第一次登录成功之后记录了你的状态。

##### Cacheability（可缓存）

- 客户端和服务端可以协商缓存内容，通过设置 HTTP 状态码，服务器可以告诉客户端这个数据是否可以被缓存。
- 例如，一个 HTTP 响应头中包含一个 Cache-Control 字段，用于告诉客户端该数据可以缓存多长时间。这样可以提高数据传输的效率，从而降低网络带宽的开销，加速数据的访问速度。

##### Layered System（分层）

- 客户端不应该关心请求经过了多少中间层，只需要关心请求的结果。
- 架构的系统可以分为多个层次，每一层独立完成自己的任务。这样的架构结构使得系统更容易维护，并且允许独立替换不同层次。
- 例如，数据库存储层可以独立于其他层，在不影响其他层的情况下进行替换或扩展。

##### Code on Demand（可选的代码请求）

- 它提倡服务器可以将客户端代码下载到客户端并执行。这样，客户端可以根据服务器发送的代码来扩展它的功能。
- 这个限制可以使客户端代码变得更加灵活，并且可以通过服务器提供的代码来解决问题，而不必再等待下一个版本。
- Code on Demand 是可选的，但它可以使 RESTful API 变得更加灵活和可扩展。

#### RESTful API 设计规范

- 说了这么多的理论，那我们该如何去设计一个最简单 RESTful 风格的 API 呢？

##### HTTP 方法

- HTTP 设计了很多动词，来标识不同的操作，不同的 HTTP 请求方法有各自的含义，就像上面所展示的，RESTful API 应该使用 HTTP 方法（如 GET、POST、PUT 和 DELETE）来描述操作。

##### 版本控制

- 版本控制是指在不影响现有的客户端应用的情况下，更新 RESTful API 的方法，据我了解常见的版本控制方式包括：

**URL 方法**：通过改变 URL 来表示不同的版本，例如 `https://api.example.com/api/v1/resources` 和 `https://api.example.com/api/v2/resources`。  

**Accept 标头**：通过请求标头中的 `Accept` 字段来表示版本。  

**请求参数**：通过请求中的参数来表示版本，例如 `https://api.example.com/resources?version=1` 和 `https://api.example.com/resources?version=2`。

- 不同公司，不同的团队所设计的 API 都各有不同，但我觉得 RESTful API 版本控制的方法要尽可能的简单，易于理解和使用直接将版本放到 URL 中，直截了当，简单明了。

##### URL 明确标识资源

- API 应该使用简洁明了的 URL 来标识资源，并且在同一个资源上使用不同的 HTTP 方法来执行不同的操作。
- 这样的设计使得客户端在无需任何额外信息的情况下就可以找到所需的资源。
- 不规范的的 URL，形式千奇百怪，不同的开发者还需要了解文档才能调用。
- 规范后的 RESTful 风格的 URL，形式固定，可读性强，根据名词和 HTTP 动词就可以操作这些资源。

![img](https://apifox.com/blog/content/images/2023/02/163a9502-e26f-4883-bbd0-5625db3393be.png)

- 给大家一个小 tips，如果你遇到了实在想不到的 URL ，你可以参考 [github 开放平台](https://docs.github.com/zh/rest/actions/artifacts) ，这里面有很多很规范的 URL 设计。

##### HTTP 状态码

- HTTP 状态码是 RESTful API 设计的重要一环，是表示 API 请求的状态，用于告知客户端是否成功请求并处理数据。常用的 HTTP 状态码有：  

200 OK：请求成功，表示获得了请求的数据  

201 Created：请求成功，表示创建了一个新的资源  

204 No Content：请求成功，表示操作成功，但没有返回数据  

400 Bad Request：请求失败，表示请求格式不正确或缺少必要参数  

401 Unauthorized：请求失败，表示认证失败或缺少授权  

403 Forbidden：请求失败，表示没有访问权限  

404 Not Found：请求失败，表示请求的资源不存在  

500 Internal Server Error：请求失败，表示服务器内部错误

##### 统一返回数据格式

- 常用的返回数据格式有 JSON 和 XML。
- JSON 是现在比较流行的数据格式，它是简单、轻量、易于解析，并且它有很好的可读性。
- XML 也是一种常用的数据格式，它的优点是比较灵活，并且支持各种数据类型。

##### 合格美观的 API 文档

- 项目开发离不开前后端分离，离不开 API，当然也就离不开 API 文档，但是文档的编写又成为程序员觉得麻烦事之一，甚至我还看到有公司的的 API 文档是用 Word 文档手敲的。
- 市面上有很多可以管理 API 的软件，每个人都有自己的选择，我给大家推荐一款 API 管理神器 [Apifox](https://www.apifox.cn/)，可以一键生成 API 文档。
- 不需要你过多的操作，只需要你在可视化的页面添加你的 API 即可生成，现在也支持了**多种导航模式**、**亮暗色模式**、**顶部自定义 Icon 、文案可跳转到你的官网等地址**。

![img](https://apifox.com/blog/content/images/2023/02/c5860e0c-5d49-408e-8385-04d3df98445d.png)

- 对于独立开发者和团队来说都是一大利好福音，本文就不做过多介绍，感兴趣的可以去试试～

## 写在最后

- 总的来说 RESTful 风格的 API 固然很好很规范，但大多数互联网公司并没有按照或者完全按照其规则来设计，因为 REST 是一种风格，而不是一种约束或规则，过于理想的 RESTful API 会付出太多的成本。
- 如果您正在考虑使用 RESTful API，请确保它符合您的业务需求。例如，如果您的项目需要实现复杂的数据交互，您可能需要考虑使用其他 API 设计方法。
- 因此，请确保在选择 API 设计方法时充分考虑您的业务需求。此外，您还需要确保 RESTful API 与您的系统架构和技术栈相兼容。通过这些考虑，您可以确保 RESTful API 的正确使用，并且可以实现更高效和可靠的 API。
- 长期来看，API 设计也不只是后端的工作，而是一个产品团队在产品设计上的协调工作，应该整个团队参与。
- 这次简单分享了 API 与 RESTful API，在实际运用中，并不是一定要使用这种规范，但是有 RESTful 标准可以参考，是十分有必要的，希望对大家有帮助。

## **一、URL 设计**

### **1.1 动词 + 宾语**

RESTful 的核心思想就是，客户端发出的数据操作指令都是"动词 + 宾语"的结构。比如，GET /articles这个命令，GET是动词，/articles是宾语。

动词通常就是五种 HTTP 方法，对应 CRUD 操作。

> 

- GET：读取（Read）
- POST：新建（Create）
- PUT：更新（Update）
- PATCH：更新（Update），通常是部分更新
- DELETE：删除（Delete）

根据 HTTP 规范，动词一律大写。

### 

### **1.2 动词的覆盖**

有些客户端只能使用GET和POST这两种方法。[服务器](https://cloud.tencent.com/product/cvm?from_column=20065&from=20065)必须接受POST模拟其他三个方法（PUT、PATCH、DELETE）。

这时，客户端发出的 HTTP 请求，要加上X-HTTP-Method-Override属性，告诉服务器应该使用哪一个动词，覆盖POST方法。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/n0mlscsqai.png)

上面代码中，X-HTTP-Method-Override指定本次请求的方法是PUT，而不是POST。

### 

### **1.3 宾语必须是名词**

宾语就是 API 的 URL，是 HTTP 动词作用的对象。它应该是名词，不能是动词。比如，/articles这个 URL 就是正确的，而下面的 URL 不是名词，所以都是错误的。

> 

- /getAllCars
- /createNewCar
- /deleteAllRedCars

### 

### **1.4 复数 URL**

既然 URL 是名词，那么应该使用复数，还是单数？

这没有统一的规定，但是常见的操作是读取一个集合，比如GET /articles（读取所有文章），这里明显应该是复数。

为了统一起见，建议都使用复数 URL，比如GET /articles/2要好于GET /article/2。

### **1.5 避免多级 URL**

常见的情况是，资源需要多级分类，因此很容易写出多级的 URL，比如获取某个作者的某一类文章。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/uwz9u854pb.png)

这种 URL 不利于扩展，语义也不明确，往往要想一会，才能明白含义。

更好的做法是，除了第一级，其他级别都用查询字符串表达。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/rmfmg5bl9s.png)

下面是另一个例子，查询已发布的文章。你可能会设计成下面的 URL。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/s9hgbx0erb.png)

查询字符串的写法明显更好。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/del8hfuomu.png)

## **二、状态码**

### **2.1 状态码必须精确**

客户端的每一次请求，服务器都必须给出回应。回应包括 HTTP 状态码和数据两部分。

HTTP 状态码就是一个三位数，分成五个类别。

> 

- 1xx：相关信息
- 2xx：操作成功
- 3xx：重定向
- 4xx：客户端错误
- 5xx：服务器错误

这五大类总共包含100多种状态码，覆盖了绝大部分可能遇到的情况。每一种状态码都有标准的（或者约定的）解释，客户端只需查看状态码，就可以判断出发生了什么情况，所以服务器应该返回尽可能精确的状态码。

API 不需要1xx状态码，下面介绍其他四类状态码的精确含义。

### **2.2 2xx 状态码**

200状态码表示操作成功，但是不同的方法可以返回更精确的状态码。

> 

- GET: 200 OK
- POST: 201 Created
- PUT: 200 OK
- PATCH: 200 OK
- DELETE: 204 No Content

上面代码中，POST返回201状态码，表示生成了新的资源；DELETE返回204状态码，表示资源已经不存在。

此外，202 Accepted状态码表示服务器已经收到请求，但还未进行处理，会在未来再处理，通常用于异步操作。下面是一个例子。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/ky30dpxh4f.png)

### 

### **2.3 3xx 状态码**

API 用不到301状态码（永久重定向）和302状态码（暂时重定向，307也是这个含义），因为它们可以由应用级别返回，浏览器会直接跳转，API 级别可以不考虑这两种情况。

API 用到的3xx状态码，主要是303 See Other，表示参考另一个 URL。它与302和307的含义一样，也是"暂时重定向"，区别在于302和307用于GET请求，而303用于POST、PUT和DELETE请求。收到303以后，浏览器不会自动跳转，而会让用户自己决定下一步怎么办。下面是一个例子。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/eceyhmacru.png)

### **2.4 4xx 状态码**

4xx状态码表示客户端错误，主要有下面几种。

400 Bad Request：服务器不理解客户端的请求，未做任何处理。

401 Unauthorized：用户未提供[身份验证](https://cloud.tencent.com/product/mfas?from_column=20065&from=20065)凭据，或者没有通过身份验证。

403 Forbidden：用户通过了身份验证，但是不具有访问资源所需的权限。

404 Not Found：所请求的资源不存在，或不可用。

405 Method Not Allowed：用户已经通过身份验证，但是所用的 HTTP 方法不在他的权限之内。

410 Gone：所请求的资源已从这个地址转移，不再可用。

415 Unsupported Media Type：客户端要求的返回格式不支持。比如，API 只能返回 JSON 格式，但是客户端要求返回 XML 格式。

422 Unprocessable Entity ：客户端上传的附件无法处理，导致请求失败。

429 Too Many Requests：客户端的请求次数超过限额。

### **2.5 5xx 状态码**

5xx状态码表示服务端错误。一般来说，API 不会向用户透露服务器的详细信息，所以只要两个状态码就够了。

500 Internal Server Error：客户端请求有效，服务器处理时发生了意外。

503 Service Unavailable：服务器无法处理请求，一般用于网站维护状态。

## **三、服务器回应**

### **3.1 不要返回纯本文**

API 返回的数据格式，不应该是纯文本，而应该是一个 JSON 对象，因为这样才能返回标准的结构化数据。所以，服务器回应的 HTTP 头的Content-Type属性要设为application/json。

客户端请求时，也要明确告诉服务器，可以接受 JSON 格式，即请求的 HTTP 头的ACCEPT属性也要设成application/json。下面是一个例子。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/k0eafokiew.png)

### **3.2 发生错误时，不要返回 200 状态码**

有一种不恰当的做法是，即使发生错误，也返回200状态码，把错误信息放在数据体里面，就像下面这样。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/fre6hzpgz7.png)

上面代码中，解析数据体以后，才能得知操作失败。

这张做法实际上取消了状态码，这是完全不可取的。正确的做法是，状态码反映发生的错误，具体的错误信息放在数据体里面返回。下面是一个例子。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/vj6za45n13.png)

### **3.3 提供链接**

API 的使用者未必知道，URL 是怎么设计的。一个解决方法就是，在回应中，给出相关链接，便于下一步操作。这样的话，用户只要记住一个 URL，就可以发现其他的 URL。这种方法叫做 HATEOAS。

举例来说，GitHub 的 API 都在 api.github.com 这个[域名](https://cloud.tencent.com/act/pro/domain-sales?from_column=20065&from=20065)。访问它，就可以得到其他 URL。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/a2cbj119fs.png)

上面的回应中，挑一个 URL 访问，又可以得到别的 URL。对于用户来说，不需要记住 URL 设计，只要从 api.github.com 一步步查找就可以了。

HATEOAS 的格式没有统一规定，上面例子中，GitHub 将它们与其他属性放在一起。更好的做法应该是，将相关链接与其他属性分开。

![img](https://ask.qcloudimg.com/http-save/yehe-1203634/ba2qepz1to.png)



```go
package main

import (
    "github.com/gin-gonic/gin"
    "net/http"
)

func main() {
    r := gin.Default()

    r.GET("/book", func(c *gin.Context) {
       c.JSON(200, gin.H{
          "method": "GET",
       })
    })
    r.POST("/book", func(c *gin.Context) {
       c.JSON(http.StatusOK, gin.H{
          "method": "POST",
       })
    })
    r.PUT("/book", func(c *gin.Context) {
       c.JSON(http.StatusOK, gin.H{
          "method": "PUT",
       })
    })
    r.DELETE("/book", func(c *gin.Context) {
       c.JSON(http.StatusOK, gin.H{
          "method": "DELETE",
       })
    })

    r.Run(":8080") // 监听并在 0.0.0.0:8080 上启动服务
}
```

模版语法

```go
r.GET("/book", func(c *gin.Context) {
    data := gin.H{"name": "keaiduo", "age": 18, "sex": 1}
    c.JSON(200, data)
})
```

模版语法2

```go
//记住要大写首字母
r.POST("/book", func(c *gin.Context) {
    type msg struct {
       Name string
       Age  int
       Sex  int
    }
    data2 := msg{Name: "keai", Age: 11, Sex: 0}
    c.JSON(http.StatusOK, data2)
})
```

标记tag

```go
type msg struct {
    //标记tag键，返回小些name，进行定制化操作
    Name string `json:"name"`
    Age  int    
    Sex  int
}
```

go mod tidy自动找包



通过query进行url查找，三种方法

```go
r.GET("/book4", func(c *gin.Context) {
    ke := c.Query("query")
    c.JSON(http.StatusOK, gin.H{
       "method": ke,
    })
})
```

```go
r.GET("/book4", func(c *gin.Context) {
    //ke := c.Query("query")
    //取不到默认值
    ke := c.DefaultQuery("query","keaiduo")
    c.JSON(http.StatusOK, gin.H{
       "method": ke,
    })
})
```

```go
r.GET("/book4", func(c *gin.Context) {
    //ke := c.Query("query")
    //取不到默认值
    //ke := c.DefaultQuery("query", "keaiduo")
    ke, ok := c.GetQuery("query")
    //取不到第二个把ke改成hello
    if !ok {
       ke = "hello"
    }
    c.JSON(http.StatusOK, gin.H{
       "method": ke,
    })
})
```

url?后面一般是get请求，多个参数用&链接

from传递

```go
r.POST("/login", func(c *gin.Context) {
    name := c.PostForm("name")
    passwd := c.PostForm("passwd")
    c.JSON(http.StatusOK, gin.H{
       "name":   name,
       "passwd": passwd,
    })

})
```

获取请求的path参数

```go
r.GET("/:name/:id", func(c *gin.Context) {
    name := c.Param("name")
    id := c.Param("id")
    c.JSON(http.StatusOK, gin.H{
       "name": name,
       "id":   id,
    })
})
```

gin参数绑定

.ShouldBind()

```go
r.GET("/user", func(c *gin.Context) {
    type user struct {
       name     string
       password string
       age      int
    }
    var u user //结构体初始化
    q := c.ShouldBind(&u)

    c.JSON(http.StatusOK, gin.H{
       "name": q,
    })
})
```

文件上传

```
r.POST("/up", func(c *gin.Context) {
    f, _ := c.FormFile("f1")
    dst := fmt.Sprintf("./%s", f.Filename)
    //或者join库
    //dst :=path.Join("./",f.Filename)
    c.SaveUploadedFile(f, dst)
})
```



多文件上传

![image-20230825232009872](/Users/kad/Library/Application Support/typora-user-images/image-20230825232009872.png)

重定向

```go
r.GET("/in", func(c *gin.Context) {
    c.Redirect(http.StatusMovedPermanently, "http://www.baidu.com")
})
```

重定向跳转

```go
r.GET("/a", func(c *gin.Context) {
    c.Request.URL.Path = "/b" //跳转b
    r.HandleContext(c) //后续处理
})

r.GET("/b", func(c *gin.Context) {
    c.Redirect(http.StatusMovedPermanently, "http://www.baidu.com")
})
```

any大杂烩

![image-20230826035642857](/Users/kad/Library/Application Support/typora-user-images/image-20230826035642857.png)

norouter，返回404

![image-20230826035839289](/Users/kad/Library/Application Support/typora-user-images/image-20230826035839289.png)

路由组

```go
vedio := r.Group("/video")
{
    vedio.GET("/index", func(c *gin.Context) {
       c.JSON(200, gin.H{
          "msg": "我是index",
       })
    })
    vedio.GET("/index2", func(c *gin.Context) {
       c.JSON(200, gin.H{
          "msg": "我是index2",
       })
    })
}
```

中间件

![image-20230826042742742](/Users/kad/Library/Application Support/typora-user-images/image-20230826042742742.png)

```go
func index11(c *gin.Context) {
    c.JSON(200, gin.H{
       "msg": "我是中间件",
    })
  c.Next() //调用后续的处理函数
  c.Abort() //阻止调用后续的处理函数
    print("我是中间件")

}
```

```go
func ms(c *gin.Context) {
    //统计使用函数的用时
    st := time.Now()
  	c.Next()
    co := time.Since(st) //计算耗时
    print("co:%v", co)

}
//全局注册
r.use(m1)
```

## gorm



简单创建查询表

```go
package main

import (
    "fmt"
    "gorm.io/driver/mysql"
    "gorm.io/gorm"
)

type ProDuct2 struct {
    //对应的数据表
    gorm.Model
    Id       int64
    Name     string
    Password string
    Name2    string
}

func main() {
    dsn := "root:root@tcp(127.0.0.1:3306)/user?charset=utf8mb4&parseTime=True&loc=Local"
    db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
    if err != nil {
       panic("failed to connect database")
    }

    db.AutoMigrate(&ProDuct2{}) //自动创建表

    insertProduct := &ProDuct2{Id: 1, Name: "可爱多", Password: "123", Name2: "123"} //插入数据


    db.Create(insertProduct) //插入
    fmt.Printf("insert ID: %d, name: %s, password: %s,varname:%s\n",
       insertProduct.Id, insertProduct.Name, insertProduct.Password, insertProduct.Name2)
    //输出

    readProduct := &ProDuct2{}
    //读表
    db.First(&readProduct, "id = ?", "1") // find product with code D42
    fmt.Printf("insert ID: %d, name: %s, password: %s,varname:%s\n",
       readProduct.Id, readProduct.Name, readProduct.Password, readProduct.Name2)

}
```

定义模型

![image-20230827145945339](/Users/kad/Library/Application Support/typora-user-images/image-20230827145945339.png)

