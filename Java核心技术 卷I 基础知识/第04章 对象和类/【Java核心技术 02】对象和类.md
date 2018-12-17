1、面向对象的程序是由对象组成的，每个对象包含对用户公开的特定功能部分和隐藏的实现部分
2、类是构造对象的模板或蓝图，由类构造的对象的过程称为创建类的实例
3、对象中的数据称为实例域，操作数据的过程称为方法，对于每个特定的类实例都有一组特定的实例域值
4、实现封装的关键在于绝对不能让类中的方法直接访问其他类的实例域，程序仅通过对象的方法与对象数据进行交互
5、在Java中，所有的类都源于一个“神通广大的超类”，它就是Object类
6、扩展一个类时，这个扩展后的新类具有所扩展的类的全部属性和方法
7、通过扩展一个类来建立另一个类的过程称为继承
8、对象包括行为、状态和标识
9、对象和对象变量：想要使用对象，就必须首先构造对象，并指定其初始状态
  在Java中，使用构造器构造新实例，构造器是一种特殊的方法，用来构造并初始化对象
10、构造器的名字应该与类名相同
11、Java作为一种面向对象语言，支持多态、继承、封装、抽象、类、对象、实例、方法和重载
12、一个类中包含以下类型变量：
局部变量：在方法、构造方法或者语句块中定义的变量称为局部变量。变量声明和初始化都在方法中，方法结束后，变量就会自动销毁。
成员变量： 成员变量是定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化，成员变量可以被类中方法、构造方法和特定类的语句块访问。
类变量：类变量也声明在类中，方法体之外，但必须声明为static类型
13、每个类都有构造方法，如果没有显式的为类定义构造方法，Java编译器将会为该类提供一个默认的构造方法。
在创建一个对象的时候，至少要调用一个构造方法，构造方法的名称必须与类同名，一个类可以有多个构造方法。
14、对象是根据类创建的，在Java中，使用关键字newl类创建一个新的对象，创建对象需要以下三步：
   声明：声明一个对象，包括对象名称和对象类型
   实例化：使用关键字new来创建一个对象
   初始化：使用new创建对象时，会调用构造方法初始化对象
15、当在一个源文件中定义多个类，并且还有import语句和package语句时，要使用以下规则：
- 一个源文件中只能有一个public类
- 一个源文件可以有多个非public类
- 源文件的名称应该和public类的类名保持一致
- 如果一个类定义在某个包中，那么package语句应该在源文件的首行
- 如果源文件包含在import语句，那么应该放在package语句和类定义之间，如果没有package语句，那么import语句应该在源文件中最前面
- import语句和package语句对源文件中定义的所有类都有效，在同一源文件中，不能给不同的类不同的包声明
16、Java中创建对象的5种方式：
（1）使用new关键字：调用了构造函数，包括无参数的和带参数的
Employee emp1 = new Employee();
（2）使用Class类的newInstance方法，这个newinstance方法调用无参的构造函数创建对象
Employee emp2 = (Employee)
Class.forName("org.programming.mitra.exercises.Employee").newInstance();
或
Employee emp2 = Employee.class.newInstance();
（3）使用Constructor类的newInstance方法，调用了构造函数
和Classl类的newInstance方法很像，java.lang.reflect.Constructor类里也有一个newInstance方法可以创建对象；可以通过这个newInstance方法调用有参数的和私有的构造函数
Contructor<Employee> constructor = Employee.class.getConstructor();
Employee emp3 = constructor.newInstance();

（4）使用clone方法，没有调用构造函数
无论何时我们调用一个对象的clone方法，jvm就会创建一个新的对象，将前面对象的全部内容全部拷贝进去，用clone方法创建对象并不会调用任何构造函数
要使用clone方法，需要先实现Cloneable接口并实现其定义的clone方法
Employee emp4 = (Employee) emp3.clone();
（5）使用反序列化，没有调用构造函数
当我们序列化和反序列化一个对象，jvm会给我们创建一个单独的对象，在反序列化时，jvm创建对象并不会调用任何构造函数
为了反序列化一个对象，我们需要让我们的类实现Serializable接口
ObjectInputStream in = new ObjectInputStream(new FileInputStream("data.obj"));
Employee emp5 = (Employee) in.readObject();
17、Date类，用于描述时间点
   System.out.println(new Date());//返回当前的日期和时间
   toString()方法，用于将时间转换成字符串类型
   String s = new Date().toString();//使用toString()方法来将时间转化成String类型
   Date birthday = new Date()
   在Java中，任何对象变量的值都是对存储在另外一个地方的一个对象的引用，new操作符的返回值也是一个引用
18、LocalDate类：用来表示日历表示法
   不要使用构造器来构造LocalDate类的对象，应当使用静态工厂方法代表你调用构造器
   LocalDate.now()会构造一个新对象，表示构造这个对象时的日期
   LocalDate.of(1999,12,31)用来对提供的年月日来构造一个特定日期的对象
   LocalDate newYearEve = LocalDate.of(1999,12,31)将构造的对象保存在一个对象变量中
   int year = newYearEve.getYear();//1999
   int month = newYearEve.getMonthValue();//12
   int day = newYearEve.getDayofMonth();//31
   LocalDate aThousandDayslater = newYearEve.plusDays(1000); //向后增加1000天的日期
   year = aThousandDayslater.getYear();// 2002
   month = aThousandDayslater.getMonthValue();// 09
   day = aThousandDayslater.getDayofMonth();// 26
   注意：plusDays()并不会改变原来对象的日期，而是重新创建一个对象，将新的日期赋值给一个新的对象
   LocalDate date = LocalDate.now();
   int month = date.getMonthValue();
   int day = date.getDaysOfMonth();
   date = date.minusDays(today-1); // set to start of month
   DaysOfWeek weekday = date.getDayOfWeek();
   int value = weekday.getValue();
19、面向对象的基本特性
封装：封装就是尽可能的隐藏对象内部细节，对外形成一道边界，只保留有限的接口和方法与外界进行交互。封装的原则使对象以外的部分不能随意的访问和操作对象的内部属性，从而避免了外界对对象内部属性的破坏。
- private：只能被这个类本身进行访问，如果一个类的构造方法声明为private，则其它类不能生成该类的一个实例。
- default:类中不加任何访问权限限定的成员属于缺省访问状态，可以被这个类本身和同一个包中的类所访问。
- protected:类中限定为protected的成员，可以被这个类本身、它的子类和同一个包中的所有其他的类访问。
- public:类中限定为public的成员，可以被所有的类访问。

继承：子类的对象拥有父类的全部属性与方法，称作子类对父类的继承。
- Java中符类可以拥有多个子类，但是子类只能继承自一个父类
- Java中所有的类都是通过直接或间接地继承java.lang.Object类得到的，也称为超类
- 子类不能继承父类中访问权限为private的成员变量和方法
- 子类可以重写父类的方法，即命名与父类同名的成员变量

Java中通过super来实现对父类成员的访问，super用来引用当前对象的父类。
super使用的三种情况：
- 访问父类被隐藏的成员变量
- 调用父类中被重写的方法
- 调用父类的构造函数

多态：指在父类中定义的属性或方法被子类继承之后，可以具有不同的数据类型或表现出不同的行为。
Java多态性体现在两个方面：由方法重载实现的静态多态性（编译时多态）和方法重写实现的动态多态性（运行时多态）。
- 编译时多态：在编译阶段，具体调用哪个被重载的方法，编译器根据参数的不同来静态确定调用相应的方法。
- 运行时多态：由于子类继承父类的所有的属性，所以子类对象可以作为父类对象使用。程序凡是使用父类对象的地方，都可以用子类对象来代替，一个对象可以通过引用子类的实例来调用子类的方法。

重载：
- 方法重载是让类以统一的方式处理不同数据类型的手段
- 一个类中可以创建多个方法，它们具有相同的名字，但具有不同的参数和不同的定义。调用方法时通过传递给它们的不同参数个数和参数类型具体使用哪个方法。
- 返回值类型可以相同，也可以不相同，无法以返回值类型作为重载函数的区分标准。

重写：
- 子类对父类的方法进行重新编写，如果在子类中的方法与其父类有相同的方法名、返回类型和参数表，就说该方法被重写。
- 如需父类中原有的方法，可使用super关键字，该关键字引用了当前类的父类
- 子类函数的访问修饰权限不能低于父类的






