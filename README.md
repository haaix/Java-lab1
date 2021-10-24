# Java-lab1
lab1-阅读程序

## 一、实验目的
1. 基本掌握本人所选择的集成开发工具的使用方法。
2. 掌握Java源程序命名、运行方法。
3. 理解、掌握创建包的方法。
4. 初步了解类的实例化方法。

## 二、实验要求
1. 定义包
2. 组织类
3. 定义类的属性、方法

## 三、实验过程
**1. 阅读程序的源文件，理解其功能、含义，分析这三个Java源程序文件的关系，理解三个源文件表达的实体业务逻辑关系（银行账户、存款人员、测试类）。<br>**
&emsp;&emsp;这三个java源程序文件放在一个包里处理同一个事件。三个源文件分别放置了不同类，前两个类代表了两个不同种类的事物，第三个是一个含有主函数的测试类，主要作用是用来测试前两个类中方法是否能够正常使用。<br><br>
**2. 在开发环境中组织代码并运行。<br><br>**
**3. 在Customer类新添加一个属性，描述其年龄，并补充操作年龄的方法。在测试类中调用这些方法。<br><br>**
**4. 在理解上述程序的情况下，尝试从头分析并复写该程序。<br>**
&emsp;&emsp;这个程序模拟了银行录入以及更改存款人信息的系统。首先建立类银行账户（Account），在里面设置属性余额（balance）。设置构造函数，能够接收输入的账户余额，设置函数getBalance获取余额，设置函数deposit用来增加余额数目，设置函数withdraw用来减少余额数目。在这其中，运用了boolean类型，进行了一下。然后建立类存款人员（Customer）,在里面设置属性Account类account，字符串类型firstName，以及字符串类型lastName,和整型age。构造函数，用来接收存款人的姓名和年龄。设置函数getFirstName、getLastName分别获取姓和名,以及getAccount获取银行账户,getAge获取年龄，还设置了一个setAccount函数用来更改账户，因为一人可以有多个账户。最后设置一个测试类TestBanking用来测试前面两个类中的方法功能。设置main函数，创建新对象，通过调用前两个类里的函数来实现获取某个人员的姓名年龄，并且能够在执行一些账户交易，增加或减少一些价格，最后显示该人物的所有账户信息。

## 四、流程图
![avatar](https://github.com/haaix/Java-lab1/blob/main/%E6%B5%81%E7%A8%8B%E5%9B%BE.png)

## 五、关键代码
1. Account类里面，有两个函数用来实现存钱和取钱。通过布尔类型，来判断取钱的金额是否是这个账户能负担得起的。
```java 
    public double getBalance(){
        return balance;
    }
    public boolean deposit(double amount){
        balance=balance+amount;
        return true;
    }
    public boolean withdraw(double amount){
        boolean result=true;
        if(balance<amount){
            result=false;
        }
        else{
            balance=balance-amount;
        }
        return result;
    }
```
2. Customer类里面，添加age属性，与构造函数的参数相对应。
```java
private int age;
```
3. TestBanking类里，采用如下方式，将Account和Customer实例化，并将两者联系在一起。
 ```java
    Customer customer;
    Account account;
    account = new Account(500.00);
    customer.setAccount(account);
 ```
 
# 六、系统运行截图
主程序TestBanking.java的运行结果，全部功能都得以很好的实现。
![avatar](https://github.com/haaix/Java-lab1/blob/main/%E8%BF%90%E8%A1%8C%E7%BB%93%E6%9E%9C.png)

## 六、实验感想
&emsp;&emsp;这是第一次实验，先是配置环境和装编译器，因为第一次接触，所以也是花费了不少时间才成功运行了起来。中间各种问题也都上百度去查找，和同学们一起交流解决各种问题，最后成功完成。关于程序可能说让自己来写是有写困难的，大体读起来还是比较容易的，但是每行认真去看代码的话，还是有些地方不太懂，同样也是通过查阅最后成功解决了。
<br>&emsp;&emsp;这次实验还是有收获的，通过阅读代码，帮助我更好地了解了程序的整体结构形式，还学会了新的用法。还有就是在学习方法上，我意识到需要我自己充足的主动性。不仅要上课认真，同时也要多加查询资料自学，通过查阅资料也很大程度上提升了我对专有名词的熟悉程度，对于我理解代码也有很大的帮助。
