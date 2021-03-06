# 接口
- 使用关键字 implements
- 可继承多个接口（变相多继承）

### 接口不同与类
- 类描述对象的属性与方法
- 接口包含类要实现的方法
- 接口中的方法没有方法体（个人理解，类似C中在开头声明函数，只声明不具体写，在接口被继承之后再类中重写）
- 一个实现接口的类，必须实现接口内所描述的所有方法，否则就必须声明为抽象类。

接口无法被实例化，但是可以被实现。另外，在 Java 中，接口类型可用来声明一个变量，他们可以成为一个空指针，或是被绑定在一个以此接口实现的对象。


### 接口与类的区别：
- 接口不能用于实例化对象。
- 接口没有构造方法。
- 接口中所有的方法必须是抽象方法。
- 接口不能包含成员变量，除了 static 和 final 变量。
- 接口不是被类继承了，而是要被类实现。
- 接口支持多继承。


# 继承
使用关键字extends

- 子类拥有父类非private的属性，方法。
- 子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。
- 子类可以用自己的方式实现父类的方法。
- Java的继承是单继承，但是可以多重继承，单继承就是一个子类只能继承一个父类，多重继承就是，例如A类继承B类，B类继承C类，所以按照关系就是C类是B类的父类，B类是A类的父类，这是java继承区别于C++继承的一个特性。

### 对象转型
举例
```java
Hero h = new Hero();
ADHero ad = new ADHero();
h = ad;
```

```java
Hero h =new Hero();
ADHero ad = new ADHero();
h = ad;
ad = (ADHero) h;
```

- 即子类转父类可以，父类转子类需强制转换，包括接口
- 没有继承关系的类无法相互转换


