## cocos 游戏开发

#### 历史

1、cocos2d-x 旧时代的c++游戏引擎，支持lua游戏逻辑开发

2、cocos centor -->工具cocos2d+h5 +方便的开发工具+组件化开发模式

3、cocos 2.5d--->cocos 3d 

4、cocos 3.x ---->2d/3d开发



### ts

```typescript
//输出语句
document.write("我是可爱多")
//声明变量
let person = "keaiduo"
//声明常量
const width = "11"
//变量类型
let tmp:number/undefind/int/string
let tmp:number[]=[1,2,3,4,5]
//两种类型都可以
let tmp:number|string
//枚举,方便归类
enum color{
  red,
  blue,
  green
}
let color:color = color.green
//运算符
++放前面，先执行，再自增
++后面，先自增，再使用
//条件控制语句
if (age>18){
  document.write("已经成年")
  
}else{
  document.write("未成年")
}

if(age>0 && age<12){
  document.write("小孩")
}else if(age>12 && age<18){
  document.write("青年")
}else{
  document.write("老人了")
}

//三目运算符 
num = num > 100 ? 100 : num;

//循环控制语句
while(i=1){
  xxx
  //死循环
}
//do，while
do{
  xx
}while(i < 0);

//函数
let arr = string[] = ["a","b","c","d","e"]
let cha:string ="b";
for(let i = 0;i<5;i++){
  if(char = string[i]){
    document.write("当前是第"+i)
  }
}
//输入=参数，输出=返回值
function fun(ch:string){
  let arr = string[] = ["a","b","c","d","e"]
	for(let i = 0;i<5;i++){
  	if(char = string[i]){
  	  document.write("当前是第"+i)
  }
}
  return i;
}
let add = function(num1,num2):void{
  
}
let add = (num1,num2):void =>{
  
}

//面向过程编程
//谁吃xx
let eat =(name:string,food:string):void=>{
  document.write(name+"吃"+food)
}

//面向对象编程
//一个人有手，头，脚，身体
//类，人
//属性=方法
class person{
  name:string = "可爱多";
  age:number = 18;
  say(){
    document.write(this.name)
  }
  eat(){
    document.write(this.name)
  }
  
}
//实例化对象
let a = new person();
//原本定义=虚拟，实例化=变成具体，再赋值=对象
a.name = "xxx"
a.age = 18
a.say()
a.eat()

//构造方法,通过构造方法传参
class person{
  name:string = "可爱多";
  age:number = 18;
  constructor(name:string,age:number){
    this.name=name;
    this.age=age;
  }
}
//成员属性和成员方法
class person{
  static des:string = "这是一个person类";
  name:string = "可爱多";
  age:number = 18;

}
//继承
class person{
  static des:string = "这是一个person类";
  name:string = "可爱多";
  age:number = 18;

}
class student extends person{
  book:number = 33
}
//继承相同会覆盖 super.say()父类方法
//抽象类,本身不允许实例化对象，可以被继承
abstract class person{
  abstract say()
}


//接口
//多继承的一种实现方式
class person{
  name:string;
}
interface wofe{
  attack();
  
}
class wolfman extends person implements wofe{
  attack(){
    xxx
  }
  eat(){
    
  }
}
//接口和属性扩展
//属性寄存器
class person{
  _hp:number = 100;
  sethp(value){
    if(value<0){
      this._hp = 0;
    }else{
      this._hp = value;
    }
    
  }
  //取值
  get hp(){
    return this._hp
  }
  //赋值
  set hp(value){
    if(value<0){
      this._hp = 0;
    }else{
      this._hp = value;
    }
    
  }
}
let a = new person();
a.hp -=180;


//命名空间
namespace aa{
  export class Person{
    name:string;
  }
}
namespace bb{
  class Person{
    name:string;
  }
}
let person = new aa.Preson();

//范型
function add(num:any):any{
  //传进去数字加1出，其他原路返回
  if(typeof num == "number"){
    num++;
    return num;
  }
  return num;
}
//T类型
function add<T>(num:T):T{
   if(typeof num == "number"){
    num++;
    return num;
  }
  return num;
}
document.write(add<number>(3))


//集合
//元组,一组数据
let kk:[string,number] = ["111",111]
kk[0]="2222"
//数组
let arry1:number[] = [1,2,3];
let arry2:Array<number> = new Array<number>();
array.push()//追加元素
array.unshift()//头部加元素
array.shift()//头部减元素
array.pop //删除最后一位
array.splice(0,1)//从第几位开始删除第几个
arr3 = array.concat(arr2) //合并array和arr2
let x =array.indeof(3)//返回元素位置
array.sort();//排序
array.reverse();//排序

//字典map
let dic：{[key:string]:string}={
  "name":"xxxx",
  "name2":"xxx"
  //键值都是string
}
//回调=函数传参，函数当参数
function func(value:function){
  value();
  //传进来，调用
}
function test(){
  document.write("test")
}
func(test)
func ((name)=>{
  document.write("test3")
})

//正则表达式
. 匹配除换行符以外的任意字符
\w匹配字母、数字、下划线、汉字
\s匹配任意空白符
\d匹配数字
\b匹配单词的开始或结束
^匹配字符串的开始
$匹配字符串的结束
全数字^[0-9]$
qq号[1-9][0-9]{4,}
let reg = /\d{4}-\d{7}/g
let str = "123456788";
let res = reg.exec(str)
res.forEach(function (value,index){
  
})


//访问修饰符
class person{
  name:string;
  //public=公开，protected=受保护的，private=私人的
  public say(){
    
  }
}
let a = new person();
a.say()

//单例模式
class sound{
  static Instance = new sound();
  private constructor(){}
}
//管理类
sound.Instance

class sound{
  private static instance:sound;
  private constructor(){ 
    //懒加载
    if(!sound.instance){
      sound.instance = new sound()
    }
    return sound.instance
  }
}
sound.Instance()

//代理模式
interface i{
  c(num1,num2):number;
}
class npc1 implements i{
  c(num1,num2){
    return num1 + num2;
  }
}
class npc2 implements i{
  c(num1,num2){
    return num1 - num2
  }
}
class person{
  getnum(num1,num2){
   
  }
}

//观察者模式，例如白天和黑夜
class person{
  private _name:string;
  obeserver:array<IObserver> = new Array<IObserver>();
  set name(value){
    this._name=value;
    //给观察者发消息
    for(let observer of this.observers){
      observer.namechanged(this._name)
    }
   
  }
  get name (){
    return this._name;
  }
}
class Test implements IObserver{
  nameChanged(newName){
    document.write("监听到变化"+newName)
  }
}
let person =new person();
let test = new Test();
person.observers.push(test);
person.name = "哈哈哈"

//工厂模式
enum carTybe{
  bwm;
  audi;
  benz;
}
class car{
  name:string;
  //工厂方法
  static Create(carType:carType):car{
    let car:car;
    switch(carType){
        case carType.audi;
        	car = new audi();
        	break;
        case carType.benz;
        	car = new benz();
        	break;
    }
  }
}

let bwn = car.create(carType.bwm)

//链表
class person{
  name:string;
  next:person;
  constructor(name){
    this.name = name;
  }
  
}
let person = new person("李逍遥")；
person.next = new person("赵琳儿")；
person.next.next = new.person("可爱多")

while(person){
  document.write(person.name);
  person = person.next;
}
//删除
person.next = person.next.next


//开机

```

## cocos目录介绍

- `assets`：资源目录
- `build`：构建目录（在构建某平台后会生成该目录）
- `library`：导入的资源目录
- `local`：日志文件目录
- `profiles`：编辑器配置
- `temp`：临时文件目录
- `package.json`：项目配置
