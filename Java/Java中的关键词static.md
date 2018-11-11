# static的用法

## 类属性
当一个属性被static修饰的时候，就叫做类属性，又叫做静态属性 
当一个属性被声明成类属性，那么所有的对象，都共享一个值 
- 类属性： 又叫做静态属性,用static修饰
- 对象属性： 又叫实例属性，非静态属性   
  如果一个属性声明成类属性，那么所有的对象，都共享这么一个值 

```java
package charactor;

public class Hero {
    public String name; //实例属性，对象属性，非静态属性
    protected float hp;
    static String copyright;//类属性,静态属性
     
    public static void main(String[] args) {
           Hero garen =  new Hero();
           garen.name = "盖伦";
            
           Hero.copyright = "版权由Riot Games公司所有";
            
           System.out.println(garen.name);
           System.out.println(garen.copyright);
            
           Hero teemo =  new Hero();
           teemo.name = "提莫";
           System.out.println(teemo.name);    
           System.out.println(teemo.copyright);
         
    }
     
}
```

#### 访问类属性
1.对象.类属性
2.类名.类属性（建议）


## 类方法
- 类方法： 又叫做静态方法，访问类方法，不需要对象的存在，直接就访问
- 对象方法： 又叫实例方法，非静态方法，访问一个对象方法，必须建立在有一个对象的前提的基础上 

- 一个方法调用了对象属性，它一定是对象方法
- 一个方法不调用对象属性，与具体对象无关，所有对象相同，科设计为类方法

```java
package charactor;
 
public class Hero {
    public String name;
    protected float hp;
 
    //实例方法,对象方法，非静态方法
    //必须有对象才能够调用
    public void die(){
        hp = 0;
    }
     
    //类方法，静态方法
    //通过类就可以直接调用
    public static void battleWin(){
        System.out.println("battle win");
    }
     
    public static void main(String[] args) {
           Hero garen =  new Hero();
           garen.name = "盖伦";
           //必须有一个对象才能调用
           garen.die();
            
           Hero teemo =  new Hero();
           teemo.name = "提莫";
            
           //无需对象，直接通过类调用
           Hero.battleWin();
         
    }
}
```

#### 调用类方法
1.对象.类方法
2.类名.类方法（建议）


