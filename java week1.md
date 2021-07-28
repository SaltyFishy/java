<h1>JAVA</h1>
回归老本行，毕竟以前学过那么一丢丢java，现在再回来看java，相当于复习了。。第一周就先复习一点以前学过的知识，顺便再推进一下进度吧。
<h2>复习模块</h2>
此模块用于描述复习java的相关知识，包括一些零碎的知识点等。
<ul>
	<li>java中long、float变量的声明:<br>
		java中对long与float类型变量的处理与其他语言相比稍有不同，体现在：<br>
		<img src="https://github.com/SaltyFishy/java/blob/main/long%20float.jpg"><br>
		这样的代码会报错，报错提示:<br>
		<img src="https://github.com/SaltyFishy/java/blob/main/long%20float%E6%8A%A5%E9%94%99%E6%8F%90%E7%A4%BA.jpg"><br>
		原因分析：java默认整数类型为int、浮点数类型为double，而不管你前面的类型写的是什么。<br>
		解决方案：在long声明的变量后面加上L、float加上f<br>
		<img src="https://github.com/SaltyFishy/java/blob/main/long%20float%20correct.jpg">
	</li>
	<li>java中算术表达式包含多个基本类型时，整个表达式的类型会自动提升，由此可能会引发一些小问题：<br>
	<img src="https://github.com/SaltyFishy/java/blob/main/%E7%B1%BB%E5%9E%8B%E6%8F%90%E5%8D%87%E5%B8%A6%E6%9D%A5%E7%9A%84%E9%97%AE%E9%A2%98.jpg" alt="类型提升带来的问题"><br>
	而java中的类型等级：byte,short,char—> int —> long—> float —> double<br>
	可以看到，由于算术表达式的等级提升，编译无法通过（在java中容量大的类型转换为容量小的类型只能用强制转换），此时可以加入强制类型转换解决。<br>
	或有些特别的运算符是包括了强制类型转换的，如：+=、-=、*=等	
	</li>
	<li>位运算：<br>
	菜鸟教程给出了详细的位运算符及其解释,其本质上是二进制的计算。<br>
	<img src="https://github.com/SaltyFishy/java/blob/main/%E4%BD%8D%E8%BF%90%E7%AE%97.jpg" alt="位运算"><br>
	</li>
	<li>JDK12给出了关于switch语句的一个性特性：switch的返回值，传统的swicth case给某个变量赋值是这样的：<br>
	<img src="https://github.com/SaltyFishy/java/blob/main/%E4%BC%A0%E7%BB%9Fswicth%E8%B5%8B%E5%80%BC.jpg" alt="传统swicth赋值"><br>
	新方法可以简单实现（并且使用->可以避开使用break语句）：<br>
	<img src="https://github.com/SaltyFishy/java/blob/main/JDK12%E5%90%8E%E7%9A%84%E6%96%B0%E6%96%B9%E6%B3%95.jpg" alt="JDK12后的新方法"><br>
	当case后面的语句过于复杂要用花括号括起来时，需要用关键字yield来进行赋值：<br>
	<img src="https://github.com/SaltyFishy/java/blob/main/yield.jpg" alt="yield">
	</li>


	<li>
	</li>


	<li></li>


	<li></li>


	<li></li>


	<li></li>




</ul>
