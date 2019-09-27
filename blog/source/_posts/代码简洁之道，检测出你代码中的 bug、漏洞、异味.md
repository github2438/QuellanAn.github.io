

title: 代码简洁之道，检测出你代码中的 bug、漏洞、异味

####  代码简洁的重要性

代码就是衔接人脑理解需求的含糊性和机器指令的精确性的桥梁。哪怕未来会有对现在高级编程语言的再一次抽象——但这个抽象规范自身仍旧是代码。所以既然代码会一直存在下去。所以才会出现那么多的祖传代码，
基本上我们读代码时间往往比写代码的时间多，而简洁的代码可以增加可读性，可以让别人快速的理解你代码想要表达或是想做的事情。从而能够更好的拓展和修改。

在工作过程中，我们往往会出现为了拓展一个功能或修改一个bug，调整原来的代码，结果导致出现更多的bug。这总是让我们程序员抱怨写的代码垃圾，这都是因为代码不够简洁，别人没有真正理解而接着开发，积累的坑越来越多，到一定程度，代码就成了累赘了，变得难以拓展和维护。所以代码简洁就显得尤为重要了，我们写代码应该像写文章一样，先自由发挥，再细节打磨，追求完美简洁。

#### 简洁的代码是什么样的

“唯一能有效测量代码质量的方式是每分钟说多少个What-the-Fk ”
− Robert Martin

整洁的代码简单直接。整洁的代码如同优美的散文。整洁的代码从不隐藏
设计者的意图，充满了干净利落的抽象和直截了当的控制语句。
可以对比一下下面这两段代码，哪个更让你舒服呢
![enter image description here](https://images.gitbook.cn/1cb53670-96f6-11e9-bc97-93abff33030c)
![enter image description here](https://images.gitbook.cn/2562e470-96f6-11e9-b265-f1f3c6cbb1c4)
这两段代码实现的功能是一样的，很显然第二种的代码是非常简洁优雅的，通过方法名就能知道这个方法是做什么的，并且很有层次感。第一种的代码就让我们很头痛了，需要花更多的时间去理清逻辑，但是这种代码我们项目中最常见的样式，所以我们在读代码的时候是多么痛苦。

所以简洁的代码是什么样的，让人最快读懂能理解的代码就是简洁的代码。

#### 怎样写出简洁的代码
在这之前，先说说代码的坏味道，看看你写的代码中有没有这些，如果有那就尽早修改。
###### 代码坏味道
1. 重复的代码
2. 过长的方法
3. 过大的类
4. 过长的参数列
5. 散弹式修改（同一个方法在项目中不同的地方出现，需要修改的时候多多处修改）
6. 不同的类别使用switch
7. 临时变量
8. 过多的抽象和代理
9. 无用多余的方法代码
10. 魔法数字（代码中存在一些常量直接使用或者比较，但是这些常量并没有声明和统一管理）

上述的坏味道仅仅是一部分，这些坏味道的代码往往会造成代码很多问题，如：
1. 难于变化
2. 难于重用
3. 设计过于复杂，不利于当前编码
4. 同样的逻辑多处出现，没有进行抽象的统一
5. 命名混乱，结构杂乱，难以阅读和理解
6. 难于测试和验证

##### 代码准则
所以就写代码的时候需要遵循一些准则，每个公司定义的准则不一样，但是整个公司都遵循着一套准则和规范，那么写出来的代码，别人是不是更容易理解呢？

下面给出我们公司实行的准则和规范给大家参考：
我们公司制定代码十三大原则，并附有宣言：整洁的代码从不隐藏设计者的意图，我是程序设计师，我遵循4不超、2个一、7禁止。

**4不超**
1. 函数圈复杂度不超过15
2. 函数代码行数不超过50行
3. 函数参数不超过7个
4. 函数嵌套层次不超过3层

**2个一**
1. 每一行代码只表达一件事
2. 每个变量只用于单一用途

**7禁止**
1. 函数/变量命名要有真实准确的意义 （禁止含有Not、And、OR；禁止具有歧义的命名）
2. 禁止使用do/while语句
3. 禁止使用continue语句
4. 禁止使用魔法数字
5. 禁止使用三元表达式
6. 禁止在if语句中使用运算表达式
7. 禁止提交SVN的代码中含有死代码

另外我们写代码大部分都是写方法，所以针对函数我们公司给出了**函数十个一**
1. 每个变量值用于单一用途
2. 每行代码只想表达一件事
3. 一个循环只做一件事
4. 单一层次抽象原则
5. 代码组织的一次只做一件事
6. 一种变化的仅仅修改一处
7. 函数应该遵守单一职责
8. 函数圈复杂度应该小于一十
9. 函数第一原则是必须短小
10. 编写函数是，必须一心一意，专注，怀有谦卑的心态

不过在写函数的时候其实我们很难做到满足上面所有的要求，我自认为我是做不到的，这些往往是理想的状态，有时候满足这个准则就会冲突另一个准则，所以总结写函数的几点注意，我觉得做到这样，这个函数就可以算得上是比较简洁的了。
1. 函数名必须规范，能体现这个函数的用途最好。
2. 每个函数体进行注释说明，函数功能、参数。返回值
3. 使用卫函数：卫函数是指减少程序的圈复杂度提前返回输出。
4. 如果是一个public函数，尽量保持函数的单一抽象层次原则。即将这个函数抽离分解成若干个子函数组成，每个函数只做一件事情。这样的目的可以使得代码变得简洁易懂。

看如下代码：

![enter image description here](https://img-blog.csdnimg.cn/20181228142124234.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)
If(!readOnly){…}可以使用卫函数，改成if(readOnly){return };然后对函数进行抽象，可以抽成三部分，第一部分判断是否为只读，第二部门扩容，第三部门添加函数。如下：
![enter image description here](https://img-blog.csdnimg.cn/20181228142142491.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)
这样代码就显得很简洁了，让人一眼就能明白是做什么的。最后一个函数addElement()中只有一条语句也单独的抽成一个函数，这样做的好处是保证的函数的单一抽象层次原则。像书的目录一样，整个add()方法中都是函数组成，显得更加的美观，并且抽成函数可以通过函数名就能知道这个函数是做什么的，比直接写语句更加的直观。

##### 代码注释
另外相信大部分小伙伴都觉得注释应该越多越好吧，这样对方法理解通过看注释就可以看懂。但是实际上这是不对的。**简洁的代码，不需要注释就可以让人看懂。** 注释的作用是方便别人理解，所以当你想通过注释来说明一段代码是做什么的时候也许你就应该将其抽离出成函数，通过函数名来解释这个函数的作用，这样使得代码更加简洁。另外一段代码很乱，就不要给它再增加注释了，重写这个方法吧。

这里提倡的是大家不要写无用的注释，而不是不写注释。另外还有一点，我们的程序代码往往很容易变动,但是往往会忘记修改注释，导致最后注释反而起到了误导的作用。所以建议注释也一定要规范。

##### 代码可读性
关于代码的可读性，就是不要隐藏真实意图，不需要阅读者做太多的思考，所以有几点建议

1. 判断中尽量少用非，禁止多重否定。看下面例子
   ![enter image description here](https://images.gitbook.cn/1acd2370-9720-11e9-ae98-dfdddc232198)
   这个结果是多少呢？相信一不小心就判断错了吧，这种写在代码中就严重影响了代码可读性，如果你觉得这个还无所谓，那我们在来看看“我不得不否认,我不是个笨蛋”，这句话是什么意思呢？这种语句就是让你费解，需要思考。所以在代码中尽量少用非，不要多重否定。

2. 命令查询分离原则，比如下面这种代码
   ![enter image description here](https://images.gitbook.cn/91b5da80-9721-11e9-ae98-dfdddc232198)
   是先自增还是先返回结果呢？多线程情况下呢，这种就很让人费解，由于运行环境的不同，有些返回1，有些返回0。所以在写代码的时候最好控制语句和运算语句最好分离。像我们公司禁止使用三元表达式，虽然多花几行但是能让人一眼就看懂不好么。特别是那种嵌套的三元表达式这些只使用在面试中为难面试者，在实际项目中不建议使用，可读性太差。

##### 代码健壮性
注意代码中的空指针异常，比如下面代码
![enter image description here](https://images.gitbook.cn/76ab70a0-9722-11e9-9465-a7e3d006cf60)
如果para为空，就会报空指针异常，导致项目报错，这就是指代码健壮性不够了。上面代码也很好修改，加一个空指针判断或者反过来写(`"".equals(para)`)

函数不要返回null ，如下面代码
![enter image description here](https://images.gitbook.cn/26e28620-9723-11e9-ae98-dfdddc232198)
如果这个对象为空直接返回到上一层，如果没有做空值检验很容易就出现空指针异常，所以推荐函数中不要返回null，最好返回空的实例或者抛出异常。

#### 现有的项目代码优化思路已经代码检索工具
相信看完上面的代码坏味道和一些代码准则，会发现我们手头上写的项目多多少少存在一些问题需要优化的，那现在该从何开始呢，如果按照上面的准则一个类一个方法的看，相信没有什么人能坚持下来的。如果你是公司级别的，建议在公司内网搭建一个SonarQube项目，公司所有项目都进行管理起来。如果是个人级别的可以使用SonarLint，它是一个插件，在eclipse和IDEA中都有插件(下图是IDEA中的插件)
![enter image description here](https://images.gitbook.cn/48d45590-9725-11e9-ae98-dfdddc232198)

安装好插件之后重启IDEA，右击项目，最下面就会出现SonarLint，选择analyze with SonarLint(快捷键：Ctrl+Shift+s),就会对整个项目进行检测，就会检测出你项目中的bug，漏洞，异味。
![enter image description here](https://images.gitbook.cn/b65af830-9725-11e9-ae77-f7748cb4d629)

这是使用的是SonarLint 默认的规则，其实上述的那些准则，SonarLint 默认的规则就差不多了，小伙伴们可以先修复SonarLint 检测出的问题。如下图就是我实际项目中检测出来的问题，报告告诉你有哪些文件有多少问题。
![enter image description here](https://images.gitbook.cn/bfc30010-9726-11e9-9465-a7e3d006cf60)

bug和漏洞，异味的标识都不一样。大家优先清除bug和漏洞，这样提升项目的健壮性，最后修复异味，因为个人习惯不同，往往一个项目中异味数可能达到几万或者几十万都可能。所以这里建议大家通过SonarLint 检测出来的问题，先清除bug和漏洞。最后异味优先清除容易消除的。大家不要觉得bug和漏洞很难清除，以我清理N个项目的经验来看，bug和漏洞的类型不多，往往是我们写代码的时候没有注意到，但是编译不抱错，测试不到位导致的。所以修复起来相对简单的，并且SonarLint 一般都会附加上推荐的写法，所以修改成SonarLint 推荐的写法就可以了。

##### SonarLint和SonarQube检测出的bug、漏洞、异味修复的思路和案例

这里其实有很多，我单独写了一份文档，可以参看我的博文：
[SonarQube检测出的bug、漏洞以及异味的修复整理](https://blog.csdn.net/qq_27790011/article/details/89309694)
或者链接：[clean code整理](https://pan.baidu.com/s/11WXEl6-3VripUMLpylq2EQ )
提取码：c02z 
这里我就调一些我觉得项目中比较常见的讲一下。

1. Use an “instanceof” comparison instead.
   ![enter image description here](https://img-blog.csdnimg.cn/20190415104831783.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)
   上面代码都是报这个bug,提示不应该按照名称来比较类。
   不要求类名是唯一的，只要它们在包中是唯一的。 因此，尝试根据类名确定对象的类型是一种充满危险的练习。 其中一个危险是恶意用户将发送与受信任类同名的对象，从而获得可信访问。
   相反，应该使用instanceof运算符或Class.isAssignableFrom（）方法来检查对象的基础类型。
   下面我是通过isAssignableFrom（）来消除bug的。如下图：
   ![enter image description here](https://img-blog.csdnimg.cn/20190415104846217.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)

2. Use try-with-resources or close this “FileInputStream” in a “finally” clause.
   ![enter image description here](https://img-blog.csdnimg.cn/20190415104306231.png)
   提示资源没有关闭，需要在finally中进行资源关闭，但是把资源关闭放到finally中由提示这样写不规范有异味。所以它推荐的写法是将创建资源流的代码放在try()中，这样系统会自动的关闭资源，不需要我们写.close()方法，如图：
   ![enter image description here](https://img-blog.csdnimg.cn/20190415104336886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)

3. Do something with the “boolean” value returned by “delete”
   ![enter image description here](https://img-blog.csdnimg.cn/20190415120900471.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)
   提示当包含操作状态代码时，不应忽略返回值。也就是说不应该忽略文件删除操作的结果。
   所以进行如下修改，但是如下修改虽然修复了漏洞，但是新增了异味。
   ![enter image description here](https://img-blog.csdnimg.cn/20190415120911365.png)
   异味提示"java.nio.Files#delete" should be preferred (squid:S4042)。应该使用Files.delete()方法，而不能之间文件delete.所以最后修改成：
   ![enter image description here](https://img-blog.csdnimg.cn/20190415120918496.png)

4. Reorder the modifiers to comply with the Java Language Specification.
   ![enter image description here](https://img-blog.csdnimg.cn/20190415121828384.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)
   提示修饰符的顺序应该符合java语言规范，它给出的参考如下：
   ![enter image description here](https://img-blog.csdnimg.cn/20190415121838632.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI3NzkwMDEx,size_16,color_FFFFFF,t_70)

这里就给出这几个吧，更多的大家可以查看我的博客和我提供的文档。

第一次写chat，有什么不足的，欢迎大家指点交流。欢迎大家一起讨论。






