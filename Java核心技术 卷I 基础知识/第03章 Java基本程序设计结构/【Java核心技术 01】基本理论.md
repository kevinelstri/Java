public class HelloWorld{
	public static void main(String[] args){
		System.out.println("This is the first java code");
	}
}

1.Java区分大小写
2.Java全部内容都必须放在类中
3.关键字class后紧跟着类名
4.类名以大写字母开头的名词
5.多个单词构成时，使用驼峰命名法进行命名，每个单词的首字母都大写
6.源代码必须与公共类的类名相同，并用java作为扩展名
7.main方法必须声明为public
8.Java中的任何方法都必须使用“{”开始，使用“}”结束
9.关键字void表示这个方法没有返回值
10.字符串使用双引号“”作为分隔符
11.使用//进行单行注释，使用/\*\*/进行多行注释
12.数据类型：整型，浮点型，字符型，布尔型
13.变量：大小写敏感
14.常量：使用关键字fina来修饰,习惯上，常量全部使用大写字母
15.类常量：使用关键字static final来修饰，类常量的定义位于main方法的外部
16.Math类：java.lang下的类不需要导包，可以直接在类方法中进行调用
17.类型转换：byte-->short-->int-->long-->float-->double
         char-->int-->float-->double
18.强制类型转换：double x = 9.997
           int nx = (int)x
19.赋值运算符，自增自减运算符，关系运算符，boolean运算符，位运算符，运算级别，枚举类型
20.字符串：String类，java.lang下的类
              子串：substring()提取字符串中的子串，注意提取子串的长度和开始标记
              字符串连接：使用“+”来进行字符串的连接
21.字符串类型是不可变类型（★★）
22.Java的垃圾回收机制：Java将自动进行垃圾回收，如果一块内存不再使用了，系统最终会将其回收
23.equals方法检测两个字符串是否相等==>equals检测两个对象是否相等
          判断两个字符串是否相等，而不区分大小写，可以使用equalsIgnoreCase()方法
24.空串和null串：空串“”是长度为0的字符串，空串是一个对象，有自己的串长度(0)和内容(空)
             NULL串表示没有任何对象
25.String API：String类包含50个方法
   char charAt(int index)
   int codePointAt(int index)
   int offsetByCodePoints()
   int compareTo(String other)
   IntStream codePoints()
   new String()
   boolean equals()
   boolean equalsIgnoreCase()
   boolean startsWith()
   boolean endsWith()
   int indexOf()
   int lastIndexOf()
   int length()
   int codePointCount()
   String replace()
   String substring()
   String toLowerCase()
   String toUpperCase()
   String trim()
   String join()
26.构建字符串：使用StringBuilder类来构建字符串，来避免字符串不能添加的问题
   StrigBuilder builder = new StringBuilder();
   builder.append(ch);
   builder.append(str);
   String completedString = builder.toString();//使用toString()来得到一个String对象
   StringBuilder()
   int length()
   StringBuilder append(String str)
   StringBuilder append(char c)
   StringBuilder appendCodePoint(int cp)
   void setCharAt(int i,char c)
   StringBuilder insert(int offerset,String str)
   StringBuilder insert(int offerset, Char c)
   StringBuilder delete(int startIndex, int endIndex)
   String toString()
27.读取输入：Scanner类
   Scanner in = new Scanner(System.in);
   String name = in.nextLine();
   String firstName = in.next();
   int age = in.nextInt();
   Scanner(InoutStrean in)
   String nextLine()
   String next()
   int nextInt()
   double nextDouble()
   boolean hasNext()
   boolean hasNextInt()
   boolean hasNextDouble()
   static Console console()
   static char[] readPassword()
   static String readLine()
28.格式化输出：System.out.println();
29.文件读取：Scanner in = new Scanner(Paths.get("myfile.txt"),"utf-8");
          文件写入：PrintWriter out = new PrintWriter("myfile.txt", "utf-8");
   Scanner(File f)
   Scanner(String data)
   PrintWriter(String fileName)
   static Path get(String pathname)
30.控制流程：选择语句，循环语句，break语句，continue语句
31.大数值：java.math包中两个很有用的类：BigInteger和BigDecimal
   BigInteger:实现了任意精度的整数运算
   BigDecimal:实现了任意精度的浮点数运算
   valueOf():可以将普通的数值转换为大数值
           对于大数值运算：分别使用add()和 multiply()方法来运算
   BigInteger add(BigInteger other)
   BigInteger substract(BigInteger other)
   BigInteger multiply(BigInteger other)
   BigInteger divide(BigInteger other)
   BigInteger mod(BigInteger other)
   int compareTo(BigInteger other)
   static BigInteger valueOf(long x)
   BigDecimal add(BigDecimal other)
   BigDecimal substract(BigDecimal other)
   BigDecimal multiply(BigDecimal other)
   BigDecimal divide(BigDecimal other)
   int compareTo(BigDecimal other)
   static BigDecimal valueOf(long x)
   static BigDecimal valueOf(long x,int scale)
32.数组：数组是一种数据结构，用来存储同一类型值的集合
   Java中数组下标从0开始，且数组大小一旦定义就不能再改变，Java中允许数组大小为0，null表示不存在数组对象
          数字数组：初始化为0；boolean数组：初始化为false；对象数组：初始化为null
         数组拷贝：(1)数组引用：将一个数组拷贝给另一个数组，两个数组将引用同一个数组，就是指向同一个数组
       (2)数组值拷贝：使用Arrays.copyOf()方法，数组地址发生改变，就会变成新的数组，指向不同的数组
       数组排序：对数组进行排序，使用Arrays类的sort()方法，内部使用快速排序算法
   static String toString()
   static type copyOf()
   static type copyOfRange()
   static void sort()
   static int binarySearch()
   static int binarySearch()
   static void fill()
   static boolean equals()       

详情：https://blog.csdn.net/kevinelstri/article/details/84947714

         












