<h1>JAVA</h1>
回归老本行，毕竟以前学过那么一丢丢java，现在再回来看java，相当于复习了。。第一周就先复习一点以前学过的知识，顺便再推进一下进度吧。
<h2>复习板块</h2>
此模块用于描述复习java的相关知识，包括一些零碎的知识点等。
<ul>
	<li>java中long、float变量的声明:<br>
		java中对long与float类型变量的处理与其他语言相比稍有不同，体现在：<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/long%20float.jpg" alt="long float"><br>
		这样的代码会报错，报错提示:<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/long%20float%E6%8A%A5%E9%94%99%E6%8F%90%E7%A4%BA.jpg"alt="long float报错提示"><br>
		原因分析：java默认整数类型为int、浮点数类型为double，而不管你前面的类型写的是什么。<br>
		解决方案：在long声明的变量后面加上L、float加上f<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/long%20float%20correct.jpg" alt="long float correct">
	</li>
	<li>java中算术表达式包含多个基本类型时，整个表达式的类型会自动提升，由此可能会引发一些小问题：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E7%B1%BB%E5%9E%8B%E6%8F%90%E5%8D%87%E5%B8%A6%E6%9D%A5%E7%9A%84%E9%97%AE%E9%A2%98.jpg" alt="类型提升带来的问题"><br>
	而java中的类型等级：byte,short,char—> int —> long—> float —> double<br>
	可以看到，由于算术表达式的等级提升，编译无法通过（在java中容量大的类型转换为容量小的类型只能用强制转换），此时可以加入强制类型转换解决。<br>
	或有些特别的运算符是包括了强制类型转换的，如：+=、-=、*=等	
	</li>
	<li>位运算：<br>
	菜鸟教程给出了详细的位运算符及其解释,其本质上是二进制的计算。<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E4%BD%8D%E8%BF%90%E7%AE%97.jpg" alt="位运算"><br>
	</li>
	<li>JDK12给出了关于switch语句的一个性特性：switch的返回值，传统的swicth case给某个变量赋值是这样的：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E4%BC%A0%E7%BB%9Fswicth%E8%B5%8B%E5%80%BC.jpg" alt="传统swicth赋值"><br>
	新方法可以简单实现（并且使用->可以避开使用break语句）：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/JDK12%E5%90%8E%E7%9A%84%E6%96%B0%E6%96%B9%E6%B3%95.jpg" alt="JDK12后的新方法"><br>
	当case后面的语句过于复杂要用花括号括起来时，需要用关键字yield来进行赋值：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/yield.jpg" alt="yield">
	</li>
	<li>不同于C++，java并不支持多重继承，也就不存在C++特有的菱形继承
	</li>
	<li>类似C++，java中也存在继承、函数重写、深浅拷贝，java中使用extends关键字表示继承，函数重写、深浅拷贝同C++一致</li>
	<li>同C++一样，java存在对方法（函数）的重载，要求一致：参数类型或参数个数或参数顺序至少有一个不同</li>
	<li>this的两种用法：<br>
	1.与C++中的this一致，指对象本身，但调用格式有所不同:this.xxxx<br>
	2.this(),必须放在构造方法的第一行，表示一个构造方法对其它构造方法的调用
	</li>
	<li>abstract，类似于C++的virtual，有两种用法：<br>
	1.抽象类，格式为public abstract class ....{....}<br>
	2.抽象方法，格式为abstract 返回类型 function(参数);<br>
	一个包含了抽象方法的类必为抽象类，它的子类需要为该超类写出抽象方法的具体实现</li>
</ul>
<h2>新知识板块</h2>
<ul>
	<li>数据输入：</li>
	
```java
import java.util.Scanner;//导包，不可修改
Scanner sc = new Scanner(System.in);//创建对象，除sc外均不可修改
int i = sc.nextInt();//接收数据
```
<br>
	<li>随机数：</li>

```java
import java.util.Random;//导包，不可修改
Random r = new Random();//创建对象，除r外均不可修改
int i = r.nextInt(10);//获取随机数，10表示上限为10（不包括），取值为从0（包括）开始。
```
<br>
	<li>super及其用法：<br>
	1.super调用超类的构造方法：<br>
	格式为super(参数);<br>
	必须放在第一行，表示子类的构造方法调用了超类的构造方法。<br>
	2.用来访问被子类的成员隐藏的超类成员<br>
	格式为super.参数(方法、变量等);
	</li>
	<li>finalize()方法的使用<br>
	格式为

```java
	protected void finalize() throws throwable
	{……}
```
<br>
	如果为子类调用该方法，需要同时调用父类的该方法，需要在语句中加上super.finalize();
	</li>
	<li>final关键字:<br>
	在类名前加final表示该类为最终类，不可被继承(不可与abstract同时使用)，在方法名前加表示该方法不可被重写(override)，在变量前加表示该变量为常量不可被修改。</li>
	<li>static静态初始化块：<br>
	格式为：static {.........}<br>
	用于初始化类变量，一个类中可以定义一个或多个静态初始化块，他只会在加载类时被调用一次。</li>
	<li>interface（接口）<br>
	是抽象方法的集合，以interface来声明。一个类通过继承接口的方式，从而来继承接口的抽象方法。<br>
	接口并不是类，编写接口的方式和类很相似，但是它们属于不同的概念。类描述对象的属性和方法。接口则包含类要实现的方法。
	除非实现接口的类是抽象类，否则该类要定义接口中的所有方法。<br>
	接口无法被实例化，但是可以被实现。一个实现接口的类，必须实现接口内所描述的所有方法，否则就必须声明为抽象类。<br>
	<strong>总的来说，接口是一个需要被类所实现的抽象方法的集合，并且它支持多继承。</strong><br>
	故：接口中的成员变量只能是常量（因为有public final关键字），接口中的方法只能是抽象方法（public abstract），即使不写也会默认是抽象方法。<br>
	声明格式： 

```java
public interface 接口名称 (extends 其它接口名) 
{........}
```
<br>
	类实现接口：（一个类可以实现多个接口的实现）

```java
public class 类名 implements 接口名
{...}
```
<br>
	</li>
	<li>package包：<br>
	包的作用：
	<ul>
		<li>把功能相似或相关的类或接口组织在同一个包中，方便类的查找和使用。</li>
		<li>如同文件夹一样，包也采用了树形目录的存储方式。同一个包中的类名字是不同的，不同的包中的类的名字是可以相同的，当同时调用两个不同包中相同类名的类时，应该加上包名加以区别。因此，包可以避免名字冲突。</li>
		<li>包也限定了访问权限，拥有包访问权限的类才能访问某个包中的类。</li>
	</ul>
	定义格式： 

```java
package 包名;//多级包用.分开
```
<br>
	包的使用：(txt版本，两种方法)<br>
	第一种方法，手动：<br>
	<ol>
		<li>编写一个包<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%8C%85.jpg" alt="包"></li>
		<li>编译（正常写编译代码），生成class文件</li>
		<li>将class文件放入包文件夹下</li>
		<li>带包名执行<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%8C%851.jpg" alt="包1"></li>
	</ol>
	第二种方法：自动生成目录<br>
	<ol>
		<li>编写一个包（同方法1）</li>
		<li>编译：<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E8%87%AA%E5%8A%A8%E7%94%9F%E6%88%90%E7%9B%AE%E5%BD%95.jpg" alt="自动生成目录"></li>
		<li>带包名执行（同方法1）</li>
	</ol>
	</li>
	<li>import导包：（有点像C++的namespace、python的py）<br>
	为了能够使用某一个包的成员，我们需要在 Java 程序中明确导入该包。<br>
	import 语句应位于 package 语句之后，所有类的定义之前，可以没有，也可以有多条，其语法格式为：import 包名;<br>
	如输入import java.util.Scanner;就是一个导包代码。<br>
	<strong>注意：当一个类想要使用另外（本包内的类有点不同，在下面会提及）的包的类的时候，就需要导包，或全名描述的方式，有以下三种写法：
	<ul>
		<li>全名描述：如java.util.Sanner sc = new java.util.Sanner(System.in);</li>
		<li>引入包：如import haha.wuhu.*;（若一个类使用的是本包内的类则不用加通配符*，如import haha.wuhu;）</li>
		<li>引入类：如import haha.wuhu.helloworld;</li>
	</ul>
	</strong>
	</li>
	<li>java中的访问权限修饰：
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90%E4%BF%AE%E9%A5%B0.jpg" alt="访问权限修饰"><br>
	protected有一种特殊情况，当子类与基类不在同一包中：那么在子类中，子类实例不能访问基类实例的protected方法。</li>
	<li>内部类：<br>
	内部类的特点：<br>
	<ol>
		<li>内部类可以直接访问外部类的成员（包括private）</li>
		<li>外部类要访问内部类的成员必须要先创建对象</li>
	</ol>
	基本结构：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%86%85%E9%83%A8%E7%B1%BB%E5%9F%BA%E6%9C%AC%E7%BB%93%E6%9E%84.jpg" alt="内部类基本结构"><br>
	非静态内部类的三种操作：<br>
	<ul>
		<li>非静态内部类访问外部类（不常用）<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E9%9D%9E%E9%9D%99%E6%80%81%E5%86%85%E9%83%A8%E7%B1%BB%E8%AE%BF%E9%97%AE%E5%A4%96%E9%83%A8%E7%B1%BB.jpg" alt="非静态内部类访问外部类">
		</li>
		<li>在外部内中访问非静态内部类<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9C%A8%E5%A4%96%E9%83%A8%E5%86%85%E4%B8%AD%E8%AE%BF%E9%97%AE%E9%9D%9E%E9%9D%99%E6%80%81%E5%86%85%E9%83%A8%E7%B1%BB.jpg" alt="在外部内中访问非静态内部类">
		</li>
		<li>在外部类外访问非静态内部类<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9C%A8%E5%A4%96%E9%83%A8%E7%B1%BB%E5%A4%96%E8%AE%BF%E9%97%AE%E9%9D%9E%E9%9D%99%E6%80%81%E5%86%85%E9%83%A8%E7%B1%BB.jpg" alt="在外部类外访问非静态内部类">
		</li>
	</ul>	
	<strong>注意这里,在外部类外声明内部类变量有两种方法：
	<ol>
		<li>直接声明一个内部类对象<br>
			格式:外部类类名.内部类类名 对象名 = new 外部类类名().new 内部类类名();<br>
			例:

```java 
Outer.Inner on1 = new Outer().new Inner();
```
<br>
		</li>
		<li>先声明一个外部类对象，再由此生成一个内部类对象<br>
			格式: 外部类类名 外部类对象名 = new 外部类类名();<br>
				外部类类名.内部类类名 内部类对象名 = 外部类类名.new 内部类类名();<br>
			例:

```java
Outer ot = new Outer();
Outer.Inner on2 = ot.new Inner();
```
<br>
		</li>
	</ol>
	</strong>
	静态内部类的两种操作：<br>
	<ol>
		<li>在外部类中访问静态内部类<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9C%A8%E5%A4%96%E9%83%A8%E7%B1%BB%E4%B8%AD%E8%AE%BF%E9%97%AE%E9%9D%99%E6%80%81%E5%86%85%E9%83%A8%E7%B1%BB.jpg" alt="在外部类中访问静态内部类">
		</li>
		<li>在外部类外访问静态内部类<br>
		<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9C%A8%E5%A4%96%E9%83%A8%E7%B1%BB%E5%A4%96%E8%AE%BF%E9%97%AE%E9%9D%99%E6%80%81%E5%86%85%E9%83%A8%E7%B1%BB.jpg" alt="在外部类外访问静态内部类">
		</li>
	</ol>
	<strong>注意静态内部类在外部类外的声明与非静态的有不同：<br>
	格式:外部类类名.内部类类名 内部类对象名 = new 外部类类名.内部类类名();<br>

```java
Outer.Inner ot=new Outer.Inner();    
```
<br>
	</strong>
	</li>
	<strong>对于静态内部类，它的外部类对象可以有不止一个内部类对象，而对于非静态内部类，一个外部类对象只能有一个内部类对象</strong><br>
	<h4>局部（local）内部类：</h4>
	基本结构<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%B1%80%E9%83%A8%E5%86%85%E9%83%A8%E7%B1%BB%E5%9F%BA%E6%9C%AC%E7%BB%93%E6%9E%84.jpg" alt="局部内部类基本结构"><br>
	在局部内部类中访问外部类成员变量<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9C%A8%E5%B1%80%E9%83%A8%E5%86%85%E9%83%A8%E7%B1%BB%E4%B8%AD%E8%AE%BF%E9%97%AE%E5%A4%96%E9%83%A8%E7%B1%BB%E6%88%90%E5%91%98%E5%8F%98%E9%87%8F.jpg" alt="在局部内部类中访问外部类成员变量"><br>	
	<h4>匿名内部类</h4>
	本质上是一个继承了外部类或者或者实现了该接口的内部类对象<br>
	基本结构<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%8C%BF%E5%90%8D%E5%86%85%E9%83%A8%E7%B1%BB%E5%9F%BA%E6%9C%AC%E6%A0%BC%E5%BC%8F.png" alt="匿名内部类基本格式"><br>
	实例：<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%8C%BF%E5%90%8D%E5%86%85%E9%83%A8%E7%B1%BB%E5%AE%9E%E4%BE%8B.jpg" alt="匿名内部类实例"><br>
	tips:匿名内部类也可以写在外部类的成员函数内部，成为局部匿名内部类。<br>
	tips:由于匿名内部类本质上是一个对象（继承了外部类或实现了该接口），在某些情况下它可以直接作为参数,这样使用的目的是为了避免创建更多的类。<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%8C%BF%E5%90%8D%E5%86%85%E9%83%A8%E7%B1%BB%E5%81%9A%E5%8F%82%E6%95%B0.jpg" alt="匿名内部类做参数"><br>
	<a href="https://www.bilibili.com/video/BV18J411W7cE?p=193" target="_blank">详情可参考此处</a>
	<li>自动装箱与拆箱<br>
	要理解什么是自动装箱，首先要理解箱指的是什么。正如c、c++等编程语言一样，java存在一些基本数据类型，如int、char、float，同时在java中还存在着<strong>与之对应的包装类</strong><br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%8C%85%E8%A3%85%E7%B1%BB.jpg" alt="基本数据类型包装类"><br>
	包装类有许多方法，具体可以在<a href="https://tool.oschina.net/apidocs/apidoc?api=jdk-zh" target="_blank">在线帮助文档</a><br>
	那么什么是自动装箱与拆箱？自动装箱就是Java自动将原始类型值转换成对应的对象，可以将原始类型数据打包为包装类。比如将int的变量转换成Integer对象，这个过程叫做装箱，反之将Integer对象转换成int类型值，每当需要一个值时，被包装对象中的值就被自动地提取出来，这个过程叫做拆箱。<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E8%87%AA%E5%8A%A8%E8%A3%85%E7%AE%B1%E4%B8%8E%E8%87%AA%E5%8A%A8%E6%8B%86%E7%AE%B1.jpg" alt="自动装箱与自动拆箱"><br>
	</li>
	<li>枚举<br>
	枚举是一种特殊的类，一般表示一组常量，这些常量总体上具有某种关系，如红色、蓝色、绿色都属于颜色，就可以写出这样的枚举类<br>
	<img src="https://github.com/SaltyFishy/java/blob/week-1/%E9%A2%9C%E8%89%B2%E6%9E%9A%E4%B8%BE%E7%B1%BB.jpg" alt="颜色枚举类"><br>
	枚举还有很多自带的定义好的方法，在枚举类中也可以自己写方法，构造函数等<br>
	<a href="https://www.runoob.com/java/java-enum.html" target="_blank">菜鸟教程——枚举</a></li>
	<li>注解<br>
	注解的内容繁多复杂，总结起来较为繁琐，因此暂时列出一个<a href="https://blog.csdn.net/qq1404510094/article/details/80577555?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162799387216780265456577%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=162799387216780265456577&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-80577555.pc_search_download_positive&utm_term=java%E6%B3%A8%E8%A7%A3&spm=1018.2226.3001.4187">注解参考</a>以供参考，未来进行总结
	</li>
	<li>Lambda 表达式<br>
	要了解Lambda表达式，首先要理解的一个关键是函数式编程<br>
	与之前我们所学的过程性编程（命令式编程）、声明式编程（以数据结构的形式表达程序执行的逻辑）、面向对象编程（创建对象，做出行为）不同，函数式编程关注的是<strong>我们要做什么，而不是怎么做（这一点上与声明式编程相似，但函数式编程不仅仅局限于声明式编程）</strong><br>
	有关函数式编程的东西很多，但我们的重点是Lambda表达式，所以这里给出一个<a href="https://zhuanlan.zhihu.com/p/363757919" target="_blank">链接</a>，不展开<br>
	在前面我们学习了利用匿名内部类直接作为函数参数，可以减少有关于类的设计，但是它的本质还是创建了一个对象，仍然是面向对象程序设计的思想，并且代码看起来似乎有些过于冗长了，借由函数式编程，Java也引入了这一思想，实现了Lambda表达式。<br>
	标准格式：<br>
	
···java
(形式参数) -> {代码块} //代码块的内容为方法体的内容
```
<br>
	适用前提：
	<ol>
		<li>有一个接口</li>
		<li>接口中有且仅有一个抽象方法</li>
	</ol>
	无参无返回值实例：<br>
	<img src="" alt="Lambda表达式无参无返回值"><br>
	有参无返回值实例：<br>
	<img src="" alt="Lambda表达式带参无返回值"><br>
	有参有返回值实例：<br>
	<img src="" alt="Lambda表达式带参带返回值"><br>
	省略模式：<br>
	<ol>
		<li>参数的类型可以忽略</li>
		<li>多个参数时不能只忽略其中某些个（要么全省略要么全不省略）</li>
		<li>如果参数有且仅有一个，小括号可以不写</li>
		<li>如果代码块的语句有且仅有一条（除非仅有的一条语句为return语句），可以省略大括号跟分号</li>
		<li>如果代码块的语句有且仅有一条return语句，则return、大括号、分号都可不写</li>
	</ol>
	注意事项：<br>
	<ol>
		<li>Lambda表达式必须要求有接口，并且接口中有且仅有一个抽象方法</li>
		<li>使用Lambda表达式必须要有上下文环境，比如不能直接单独写一个Lambda表达式语句，详情参考<a href="https://www.bilibili.com/video/BV18J411W7cE?p=361">链接</a></li>
	</ol>
	Lambda表达式与匿名内部类的区别：<br>
	<ol>
		<li>匿名内部类new后面跟的可以是具体类、抽象类跟接口，Lambda则只能是接口</li>
		<li>匿名内部类new后面的接口可以是多个抽象方法组成的接口，Lambda只能是一个抽象方法组成的接口</li>
		<li>匿名内部类编译后会单独产生一个class字节码文件，Lambda则不会</li>
	</ol>
	</li>
</ul>
