# java笔记
[TOC]
## 2基本程序设计
### 2.1 引言
    一个简单的Java程序
    public class Welcome {//类名头字大写 类名为一个标识符 
                          //标识符的命名
                          //1.以字母 数字 下划线（_）和 美元符号 ($) 构成 且不以数字开头
                          //2.不能是保留字（见附录A）true false 或 null 
                          //3.可以为任意长度 
                          //4.不要以单独的美元符号 ($)命名
                          //5.Java是区分大小写，故 area 和 Area 为不同变量名 
        pubilc static void main(){
            System.out.println("Welcome to Java");//println("");换行 print("");不换行
        }
    }
### 2.2 常量
    final double PI = 3.14159;
### 2.3 数值类型
    byte short int long float double 
### 2.4 从控制台读取输入
    //1.引入 Scanner 包
         import java.util.Scanner;
    //2.创建 Scanner 类对象 input
        Scanner input = new Scanner(System.in);//只需要创建一次 或在使用结束后释放后 再创建
    //3.调用 Scanner 类的方法
        int a = input.nextInt(); //读取 int 类型的整数
        double b = input.nextDouble(); //读取 double 类型的数
        float c = input.nextFloat(); //读取 float 类型的数
## 3 选择
### 3.1 boolean 数据类型
    可以判断为真或假的数据类型
    //其定义 如 boolean a;
    逻辑操作 ！== 非 
            && == 与
            || == 或
            ^ == 异或
### 3.2 if 语句
    有单分支 if 语句 
    双分支 if-else 语句 
    嵌套 if 语句 
    多分支 if-else 语句
## 4 数学函数 字符 字符串
### 4.1 常用数学函数 
        //数学类 Math 其下有两个常量 Math.PI(3.14159) 和 Math.E(自然对数的底)
#### 4.1.1 指数函数
        exp(x) == e^x;

        log(x) == ln x;

        log10(x) == lg x;

        pow(a,b) == a^b;

        sqrt(x) == x^(-1/2);
#### 4.1.2 取证方法
        //大都 return double 类型数据 ;
        ceil(x) //向上取整 2.1 返回 3.0

        floor(x) //向下取整 2.1 返回 2.0

        rint(x) //取最接近的整数 为 a.5 是返回偶数

        round(x) //if float x 返回 （int） floor(x+0.5)
                 //if double x 返回 （long） floor(x+0.5)
#### 4.1.3 random 方法
        //生成大于等于 0.0 且 小于 1.0 的 doouble
        //生成大于等于 a 且 小于 a+b 的数
            a + Math.random() * b    
### 4.2字符
    char 是数据类型 而 Character 是类
    同理 int / Integer double / Double 
    常用 Character 举例
        System.out.println("toLowerCase('T')"+Character.toLowerCase('T'));

        System.out.println("toUpperCase('a')"+Character.toUpperCase('T'));
### 4.3字符串
#### 4.3.1 String 类方法
        length(); //返回字符串字符数

        charAt(index); //返回字符串指定位置的字符

        concat(s1); //将本字符串与字符串 s1 连接，并返回新字符串

        toUpperCase(); //返回一个新字符串，其中所有的字母大写

        toLowerCase(); //返回一个新字符串，其中所有字母小写

        trim(); //返回一个新字符串，去掉了两边的空白字符
        eg.
            String s = "Welcome to Java";
            System.out.println("The length of " + s + "is" + s.length() );
#### 4.3.2 从控制台读取字符
        大体同 2.3 但 第三步为 String s = input.nextLine();
#### 4.3.3 字符串比较方法
        // str1 == str2 进行的操作为 str1 和 str2 的内存空间是否相同  
        //相同的字符串只分配一次内存空间
        equal( s1 ); //如果该字符串等于字符串 s1 返回 true

        equalIgnoreCase( s1 ); //如果该字符串等于 s1 返回 true ，不区分大小写

        compareTo( s1 ); //返回一个大于 小于 等于 0 的整数，表明该字符串是否大于 小于 等于 s1 （且当内容的第一个不同就返回）

        compareToIgnoreCase( s1 ); //同上 但不区分大小写

        startsWith( prefix ); //如果字符串以特定的前缀开始 返回 true

        endsWith( suffix ); //如果字符串以特定的后缀结束 返回 true

        contains( s1 ); //如果 s1 是该字符串的子串 返回 true
#### 4.3.4 获取子串的方法
        substring(beginIndex); //返回下标 beginIndex 到字符串结束的子串

        substring(beginIndex,endIndex); //返回下标 beginIndex 到下标 endIndex-1 的子串 
                                        //当 beginInedx == endIndex 返回 长度为 0 的空字符串 
                                        //当 beginInedx < endIndex 发生错误
#### 4.3.5 获取下标的方法
        indexOf(ch); // 返回字符串中出现的第一个 ch 的下标 如果无 返回 -1

        indexOf(ch,fromIndex); // 返回字符串从fromIndex之后的中出现的第一个 ch 的下标 如果无 返回 -1

        indexOf(s); // 返回字符串中出现的第一个字符串 s 的下标 如果无 返回 -1

        indexOf(s,fromIndex); // 返回字符串从fromIndex之后的中出现的第一个字符串 s 的下标 如果无 返回 -1

        lastIndexOf(ch); //这四个是从后往前的 上四个 方法
        lastIndexOf(ch,formIndex);
        lastIndexOf(s);
        lastIndexOf(s,formIndex);

        eg.
            String s="Kim Jones";
            k=s.indexOf(" ");
            String xing = s.substring(0,k);
            String name = s.substring(k+1,s.length());
#### 4.3.6 字符串与数字的转换
    string s="123";
    int intValue = Integer.parseInt(s);
    double doubleValue = Double.parseDouble(s);
### 4.3.6 空格的几种方法
    ' ' \t \f \r \n
## 5 循环
    while do-while for
    
    如果条件为 true, 执行，否则不
## 6 方法
### 6.1 定义方法
    public static int max （int num1，int num2）{//public static 为修饰符 int 为返回类型
                                                 //（）内为 形式参数 max 为方法名 其第一个字母小写
        return int类型
    }
### 6.2 方法按值传参
### 6.3 重载方法
    //使用同样的名字来定义不同的方法  只要其参数列表（方法中的参数类型，次序，数量）不同即可
        方法名 + 参数列表 = 方法签名（method signture）
## 7 一维数组
### 7.1 声明数组变量 不赋值
    1. double[] myList;
    2. double myList[];
### 7.2 创建数组 赋值
    1. myList = new double[10];
    2. double[] myList = new double[10];
### 7.3处理数组
#### 7.3.1 使用输入值初始话数组
    // 若未初始化 其为数值类型的则为 0, char 的则为 '\u0000', boolean 为 false
    java.util.Scanner input = new java.util.Scanner(System.in);
    System.out.print("Enter " + myList.length + "values : ");
    for(int i = 0; i < myList.length; i++){
        myList[i] = input.nextDouble();
    }
#### 7.3.2 使用随机数初始化数组
    for(int i = 0; i < myList.length; i++){
        myList[i] = Math.random() * 100;
    }
#### 7.3.3 显示数组
    for(int i = 0; i < myList.length; i++){
        System.out.print(myList[i] + " ");
    }
#### 7.3.4 对全体元素求和
    double sum = 0;
    for(int i = 0; i < myList.length; i++){
        sum += myList[i];
    }
#### 7.3.5 找最大元素
    double max = myList[0];
    for(int i = 1; i < myList.length; i++){
        if(max < myList[i])
            max = myList[i];
    }
#### 7.3.6 找最大元素的最小下标
    int theMaxOfIndex = 0;
    double max = myList[0];
    for(int i = 1; i < myList.length; i++){
        if(myList[i] > max){
            max = myList[i];
            theMaxOfIndex = i;
        }
    }
#### 7.3.7 随机打乱
    for(int i = 0; i < myList.length; i++){
        int j = (int)(Math.random() * myList.length);//生成一个随机数在 0 到 myList.Length() 之间
        double temp = myList[i];
        myList[i] = myList[j];
        myList[j] = temp;
    }
#### 7.3.8 将第一个移动到最后 其他的左移
    double temp = mylist[0];
    for(int i = 1; i < myList.length; i++){
        myList[i-1]=myList[i];
    }
    myList[myList.length - 1] = temp;
### 7.4 foreach 循环
    for(double e: myList){// e必须与 myList 数据类型相同
        System.out.println(e);
    }
### 7.5 复制数组
    int sourceArray = {2, 3, 1, 5, 10};// 不用 new 操作符
    int targetArray = new int [sourceArray.length];
#### 7.5.1 
    for(int i = 0; i < sourceArray.length; i++){
        targetArray[i] = scourceArray[i]
    }    
#### 7.5.2
    //                资源数组    复制位置    目标数组   复制位置  复制数量    
    System.arraycopy(sourceArray, 0,      targetArray, 0,       sourceArray.length);
### 7.6 Arrays 类
    double[] numbers = {6.0, 4.4, 1.9, 2.9, 3.4, 3.5};
#### 7.6.1 排序   
    java.util.Arrays.sort( numbers ); // 用单 CPU　对 number 排序
    java.util.Arrays.parallelsort( numbers );　// 用多 CPU　对 number 排序
    
    java.util.Arrays.sort( numbers, 1, 3); // 用单 CPU　对 number[1] 到 number[3] 排序
    java.util.Arrays.parallelsort( numbers, 1, 3);　// 用多 CPU　对  number[1] 到 number[3] 排序
#### 7.6.2 判断相等
    int[] list1 = {2, 4, 7, 10};
    int[] list2 = {2, 4, 7, 10};
    int[] list3 = {4, 2, 7, 10};
    System.out.println(java.util.Array.equals( list1, list2 )); //true
    System.out.println(java.util.Array.equals( list3, list2 )); //false
#### 7.6.3 填充
    java.util.Arrays.fill( list1, 3);
    java.util.Arrays.fill( list1, 1, 3, 8);
#### 7.6.4 显示
    System.out.println(java.util.Arrays.toString(list1)); // 显示 [ 2, 4, 7, 10]
### 7.7 dome 计算机
    public class Calculator{
        public static void main( String[] args){
            if(args.length != 3){
                System.out.println("Usage : java Calculator operand1 operator operator2");
                System.exit( 1 );
            }
        }
        switch( args[1].charAt(0)){
            case '+' :System.out.println( Integer.parseInt(args[0]) + Integer.parseInt(args[2]) );break;
            case '-' :System.out.println( Integer.parseInt(args[0]) - Integer.parseInt(args[2]) );break;
            case '*' :System.out.println( Integer.parseInt(args[0]) * Integer.parseInt(args[2]) );break;
            case '/' :System.out.println( Integer.parseInt(args[0]) / Integer.parseInt(args[2]) );break;
        }
    }
## 8 多维数组
### 8.1 声明创建多维数组
    // 声明二维数组
    int[][] = matrix;
    int = matrix[][];//不推荐这种方法
    // 创建二维数组
    matrix = new int[5][5];
    // 给其某一个数组赋值
    martrix[2][1] = 7;
    // 获取二维数组的长度
    matrix[0].length;
    matrix[1].length;
    matrix[2].length;
    matrix[3].length;
    matrix[4].length;
    // 不规则数组 不使用 new 创建
    int [][] triangleArray = {
        {1, 2, 3, 4, 5},
        {2, 3, 4, 5},
        {3, 4, 5},
        {4, 5},
        {5}
    };
### 8.2 处理二维数组
    int [][] matrix = new int [10][10];
#### 8.2.1 使用输入值初始话数组
    java.util.Scanner input = new java.util.Scanner(System.in);
    System.out.print("Enter " + matrix.length + " rows and " + matrix[0].length + " columns :");
    for(int row = 0; row < matrix.length; row++){
        for(int column = 0; column < matrix[row].length; column++){
            myList[row][column] = input.nextDouble();
        }
    }
#### 8.2.2 使用随机数初始化数组
    for(int row = 0; row < matrix.length; row++){
        for(int column = 0; column < matrix[row].length; column++){
            myList[row][column] = (int)(Math.random() * 100);
        }
    }
#### 8.2.3 显示数组
    for(int row = 0; row < matrix.length; row++){
        for(int column = 0; column < matrix[row].length; column++){
            System.out.print(myList[row][column] + " ");
        }
        System.out.println();
    }
#### 8.2.4 对全体元素求和
    int sum = 0;
    for(int row = 0; row < matrix.length; row++){
        for(int column = 0; column < matrix[row].length; column++){
            sum += matrix[row][column];
        }
        System.out.println();
    }
#### 8.2.5 按列求和
    for(int row = 0; row < matrix.length; row++){
        int sum = 0;
        for(int column = 0; column < matrix[row].length; column++){
            sum += matrix[row][column];
        }
        System.out.println("Sum for column " + column + "is " + total);
    }
#### 8.2.6 那一行的和最大
    int maxRow = 0;// 求最大元素
    int theMaxRowOfIndex = 0;// 求该行的下标
    for(int column = 0; column < matrix[row].length; column++){
        maxRow += matrix[0][column];
    }
    for(int row = 1; row < matrix.length; row++){
        int totalOfThisRow = 0;
        for(int column = 0; column < matrix[row].length; column++){
            totalOfThisRow += matrix[row][column];
        }
        if(totalOfThisRow > maxRow){
            maxRow = totalOfThisRow;
            theMaxRowOfIndex = Row;
        }
        System.out.println("Sum for column " + column + "is " + total);
    }
#### 8.2.7 随机打乱
    for(int i = 0; i < matrix.length; i++){ // 如果为不规则数组,则不可以
        for(int i = 0; j < matrix[i].length; j++){
        int i1 = (int)(Math.random() * matrix.length);//生成一个随机数在 0 到 myList.Length() 之间
        int j1 = (int)(Math.random() * matrix[i].length);//生成一个随机数在 0 到 myList.Length() 之间
        double temp = matrix[i][j];
        matrix[i][j] = matrix[i1][j1];
        matrix[i1][j1] = temp;
    }
### 8.3 将二维数组传递给方法
    public static int[][] getArray(int [][] m){
        Scanner input = new Scanner(System.in);

        System.out.println ("Enter " + m.length + " rowa and " + m[0].length + "columns:");
       // loop
       return m;
    }
## 9对象和类
### 9.1 一个类
    // 一个文件中可以有多个类，但只能有一个类是 public 的且与文件同名
    //    类名头字大写
    class Circle{
        double radius = 1;//数据域
        //以下构造方法两个
            1.构造方法必须和所在类的名字想同
            2.构造方法没有返回值类型，甚至连 void 也没有
            3.构造方法是在创建一个对象时由 new 操作符调用的，其作用是初始化对象
            4.未初始化对象的 String 型的值会被附上 null，数值 -> 0 char -> "\u0000" boolean -> false
                但未给局部变量赋值就会报错 具体是 nullPointException

                原因 ：
                    局部变量是基本类型变量 -> 值传递
                    类的变量是引用类型变量 -> 址传递
            5.构造方法也可以重载
        Circle(){
            //如果没有上一个构造方法类会隐式定义一个方法体为空的无参构造方法
            //其名为默认构造方法
            //如这个构造方法
            //如果有 coder 写的构造方法着其不会被调用
        }
        Circle(double newRadius){
            radius = newRadius;
        }
        //以下两个方法  也叫实例方法
        double getPerimeter(){
            return 2 * radius * Math.PI;
        }
        void setRadius(double newRadius){
            radius = newRadius;
        }
    }
### 9.2 静态变量 常量 和 方法
    静态变量 常量 和 方法 属于类的变量 常量 和 方法
    静态变量 static int number;
    静态方法 static int getNumber(){
        return number;
    }
    静态常量 final static int A = 1;
    实例方法可以调用实例方法和静态方法以及访问实例数据域和静态数据域
    静态方法只能调用实例方法已经访问静态数据域
### 9.3 可见性修饰符
    // 类中的数据域和方法是否能在该类外被访问
    public 可被任何其他的类访问
    private 只能在它自己的类中被访问
    如果一个类没有被定义为公共类，那么它只能在同一个包内被访问
            // 包 ：用来组织类 作为程序中第一条非注释和非空白行的语句  package packageName;
    数据域应为 private 通过 getData() 和 setData() 调用
    构造方法 和 方法 应为公共的
### 9.4不可变对象和类
    1.所有数据域都是私有的
    2.没有修改器 即 setData()
    3.没有返回一个指向可变数据域的引用的访问器方法
### 9.5 变量的作用域
    1.实例变量和静态变量的作用域为整个类，无论变量是在哪里声明
    2.局部变量和类变量同名局部变量优先，而同名的类变量将被隐藏
        解决方法 -> this 指针
### 9.6 this 指针
> 关键字 this 是一个对象可以用来引用自身的引用名
    
    具体用于：
        1. 在引用被方法或构造方法的参数隐藏的数据域 
            eg
                void setRadius(double radius){
                    this.radius = radius;
                }
        2. 调用一个重载的构造方法
            eg
                Circle(){
                    this(1.0);//这句话要在其他可执行的语句前出现
                              //通常用于参数少或无参数的构造方法调用参数多的构造方法
                }         
### 9.7 java 库中的类
#### 9.7.1 Date 类
    java.util.Date
    +Date()//针对当期时间创建一个 Date 对象
    +Date(elapseTime : long)//针对一个从格林威治时间 （1970.1.1）至今流逝的
                            //以毫秒为单位计算的给定时间创建一个 Date 对象
    +toString() ：String //返回一个代表时间的字符串 如 Mon Dec 26 07：43：39 EST 2011
    +getTime() : long //返回一个从格林威治时间 （1970.1.1）至今流逝的毫秒数
    +setTime(elapseTime : long)//在对象中设置一个新的流逝时间
#### 9.7.2 Random 类
    java.util.Random
    +Random()               //以当前时间作为种子创建一个 Random 对象
    +Random(seed: long)    //以一个特定值作为种子创建一个 Random 对象
    +nextInt() : int        //返回一个随机的 int 值
    +nextInt(n: int) : int //返回一个 0 到 n（不包括 n）之间的随机的 int 值
    +nextLong() : long      //返回一个随机的 long 值
    +nextDouble() : double  //返回一个 0.0 到 1.0（不包括 1.0）之间的随机 double 的值
    +nextFloat() : float    //返回一个 0.0F 到 1.0F（不包括 1.0F）之间的随机 float 的值
    +nextBoolean() : boolean//返回一个随机的 boolean 的值
        eg
             java.util.Random r = new  java.util.Random(3);
             r.nextInt();
### 9.7.3 Point2D 类
    javafx.geometry.Point2D
    +Point2D( x: double, y: double )  //用给定的 x 和 y 坐标来创建一个 Point2D 对象
    +distance( x: double, y: double ) : double //返回该定点到给定点 (x,y) 之间的距离
    +distance(  p: Point2D ) : double //返回该定点到给定点 p 之间的距离
    +getX() : double                  //返回该点的 x 坐标
    +getY() : double                  //返回该点的 y 坐标
    +midpiont( p: Point2D ) : Point2D  //返回该点和点p的中间点
    +toString() : String              //返回该点的字符串表示 如 [ x = 5, y = 6]
        eg
            Point2D p1 = new Point2D(3,4);
            Point2D p2 = new Point2D(4,3);
            p1.distance(p2).toString();
            p1.midpoint(p2).toString();
## 10 面对对象思考
### 10.1 类的抽象和封装
> 类的抽象是指类的实现和类的使用分离开，

    类的抽象(class abstraction)是将类的实现和使用分离。类的创建者描述类的功能，让使用者明白如何使用类。
    从类外可以访问的 public 构造方法，普通方法和数据域的集合以及对这些成员预期行为的描述，构成了类的合约(class's contract)
> 类的封装实现的细节被封装并且对用户隐藏。

    类的使用者是不知道类是如何实现的。实现的细节通过封装对用户隐藏起来，这成为类的封装（class encapsulation）
### 10.2 面对对象的思想
> 面对过程的范式重点在于设计方法。

> 面对对象的范式将数据和方法耦合在一起构成对象，软件设计的重点在于对象以及对象上的操作。
### 10.3 类的关系
> 类的关系有 关联，聚合，组合，继承。
- 关联是两个类有关系
- 聚集是关联的一种特殊形式，代表了两个对象之间的归属关系 has - a 建模
    - 设计者对象称为聚集对象，它们类称为聚集类。而从属对象称为被聚集对象，它的类被称为被聚集类。
    - 聚集关系通常表现为聚集类中的一个数据域
    - 聚集关系可以存在于同一个类的对象之间，如一个人可能有一个管理者
- 组合 若被聚集对象的存在依赖于聚集对象，称这两个对象之间的关系为组合（composition）。

    即被聚集对象不能单独存在。也就是组合暗示了独占性的拥有
    如 一个学生有一个名字就是学生类与名字类之间的一个组合关系，因为 Name 依赖于 Student
      一个学生有一个地址就是学生类与地址类之间有一个聚集关系，因为一个地址可以单独存在
- 聚集和组合关系通常不做区分，都称为组合。
### 10.4 将基本数据类型作为对象处理
> 基本数据类型不是对象，但是可以使用Java API 中的包装类来包装成一个对象。

    java.lang 包里面为基本数据类型提供了 Boolean Character Double Float Byte Short Integer Long 等包装类
> 
    java.lang.Integer
    -value: int                    
    +MAX_VAlUE: int // 表示对应的基本数据类型的最大值
    // 对于 Byte Short Integer Long 表示对应的基本数据类型的最小值
    // 对于 Double Float 表示对应的基本数据类型的最小正值
    // 如 Double.MIN_VAlUE= 1.4E-45
    +MIN_VAlUE: int
    // 包装类中没有无参构造函数。故所有包装的实例都是不可变的，
    +Integer(value: int)// new Integer(5)
    +Integer(s: String)// Integer("5")
    // 可以将int 转化为其他数据类型
    +byteValue(): byte
    +shortValue(): short
    +intValue(): int
    +longValue(): long
    +floatValue(): float
    +doubleValue(): double
    // new Integer(5).compareTo(new Integer(5))return 0(等于 0)
    // new Integer(5).compareTo(new Integer(6))return -1（小于 -1）
    // new Integer(5).compareTo(new Integer(4))return 1（大于 1）
    +compareTo(o: Integer): int 
    +toString():String
    // 创建一个新对象，并将它的初始值为指定字符串表示的值
    // radix 进制
    +valueOf(s: String):Integer
    +valueOf(s: String,radix: int):Integer
    +parseInt(s: String):int 
    +parseInt(s: String,radius: int):int 
### 10.5 基本类型和包装类之间的自动转化
> 装箱（boxing）将基本类型转化为包装类对象的过程。

     Integer intObject = new Integer(2); <=> Integer intObject = 2;
> 拆箱（unboxing）相反的转化过程。      

    int i = 1; <=> int i = new Integer(1);
### 10.6 BigInteger 和 BigInteger 类
> BigInteger 和 BigInteger 类可以用于表示任意大小和精度的整数或十进制数，常用于非常大的数的计算或者高精度的浮点数值的计算。

    java.math.BigInteger
    +BigInteger(s: String)
    +add(o: BigInteger)
    +subtract(o: BigInteger)
    +multiple(o: BigInteger)
    +divide(o: BigInteger)
    // scale 小数点后最小的整数位数，roundingMode 四舍五入的方式
    +divide(o: BigInteger,scale: int,roundingMode: int)
    // 求余
    +remainder(o: BigInteger)
    +compareTo()
### 10.7 String 类
> String 类对象是不可改变的。
#### 10.7.1 构造字符串
    1.
        String stringLiteral = "Test";
        String newString = new String(StringLiteral);
    2. 
        String message = new String("Welcome to Java");
    3. 
        String message = "Welcome to Java";
       注 2 和 3 需要两块内存空间
    4. 
        char[] charArray = new {'G','o','o','d','','D','a','y'};
        String message = new String(charArray);
#### 10.7.2 不可变字符串与驻留字符串
    String s = "Java"; // 存放Java的内存的地址存放在 s 中
    s = "HTML";// s又存放了 HTML 的地址
> 驻留字符串 因为字符串在程序设计中是不可变的，但又会频繁地使用，故具有相同字符序列的字符串字面值使用同一个实例，其称为驻留字符串。
#### 10.7.3 替换和拆分字符串
    java.lang.String
    +replace(oldChar: char,newChar :char): String// 将字符串中所有的匹配的字符替换成新的字符，然后返回新的字符串。
    +replaceFirst(oldString: String,newString :String): String// 将字符串中第一个匹配的子字符串替换成新的子字符串，
                                                              //然后返回新的字符串。
    +replaceAll(oldString: String,newString :String): String// 将字符串中所有的匹配的子字符串替换成新的子字符串，
                                                            //然后返回新的字符串。
    +split(delimiter: String): String[]// 返回一个字符串数组，其中包含被分隔符拆分的子字符串集
>
    如下
        String[] tokens = "Java#HTML#Perl".split("#");
        for(int i =0 ; i <= tokens.length; i++){
            System.out.print(tokens[i]+ " ");// 返回 Java HTML Perl
        }
#### 10.7.4 使用模式匹配，替换和拆分
> 正则表达式(regular expression)(缩写 regex)是一个字符串，用于描述匹配一个字符串集的模式
> 可以通过指定某个模式来匹配，替换或拆分一个字符串。

    "Java".equals("Java");
    "Java".matches("Java");
    // 两句均为 true，但是 match 的方法更加强大。
    // 它不但可以匹配固定的字符串，还能匹配一组遵从某种模式的字符串

    如下语句均为 true
    "Java is fun".matches("Java.*");
    "Java is cool".matches("Java.*");
    "Java is powerful".matches("Java.*");
> 前面语句中的"Java.*"是一个正则表达式。描述了字符串模式是以字符串 Java 开头的后面紧跟任意0个或多个字符

    "440-02-4534".matches("\\d{3}-\\d{2}-d{4}");
    // \\d表示单个数字，\\d{3}表示三个数字
>
    replaceAll ,replaceFirst 和 split 也可以和正则表达式结合使用
    如下
    String s = "a+b$#c".replaceAll("[$+#]","NNN");
    // 用 NNN 替换 $ + 或# 输出为 aNNNbNNNNNNc
    String[] tokens = "Java，C?C#,C++".split(".,:;?");
    for(int i =0 ; i <= tokens.length; i++){
        System.out.print(tokens[i]+ " ");// 返回 Java C C# C++
    }   
#### 10.7.5 字符串与数组之间的转换

    char[] chars = "Java.".toCharArray();
    // 得到 Char[0] = 'J', Char[1] = 'a',Char[2] = 'v',Char[3] = 'a'

    getChars(int srcBegin,int srcEnd,char[] dst,int dstBegin)
    //从srcBegin到srcEnd-1的字串复值到字符数组 dst 中下标从 dstBegin 开始的位置。
    如
        char[] dst = {'J','A','V','A','1','3','0','1'};
        "CS3720".getChars{2,6,dst,4};
        //这样 dst 变成了 {'J','A','V','A','3','7','2','0'}
    
    // 将一个字符数组转换成一个字符串，应该使用构造方法 String(char[])或 valueOf(char[])
    如
        String str = new String(new Char[]{'J','A','V','A'});
        String str = String.valueOf(new Char[]{'J','A','V','A'});
#### 10.7.6 将字符串和数值转换字符串
    java.lang.String
    +valueOf(c: char): String
    +valueOf(data: char[]): String
    +valueOf(d: double): String
    +valueOf(f: floar): String
    +valueOf(i: int): String
    +valueOf(l: long): String
    +valueOf(b: boolean): String
#### 10.7.7 格式化字符串

    String s = String.format(" %7.2f %6d %-4s ",45.556,14,"AB");
    显示 [][]45.56[][][][]14AB[][]
#### 10.8 StringBuilder 和 StringBuffer类
> StringBuilder 和 StringBuffer类是可改变的 String 类。

>  StringBuilder用于单任务 和 StringBuffer 用于多任务 
## 11 继承和多态
### 11.1 引言
> 面对对象编程支持从已经存在的类中定义新的类，这称为继承

    好处避免冗余和使系统易于理解和维护
### 11.2 父类和子类
> 继承使得你可以定义一个通用的类（即父类），之后继承该类为一个更特定的类（即子类）

    在 Java 术语，如果类 C1 继承自另一个类 C2，那么就将 C1 称为子类（subclass），将 C2 称为超类(superclass).

    超类也称为父类（parent class）或基类（base class），子类又称为继承类（extends class）或派生类（derived class）。

> 子类和它的父类形成了“是一种”（is-a）的关系。

> 继承的关键点

- 和习惯性说法不同，子类并不是父类的子集。一个子类通常比它的父类包含更多的信息和方法。
- 父类中的私有数据域在该类外是不可访问的。只有父类中定义了公共的访问器和修改器，那么可以通过这些公共的访问器或修改器来访问修改它们。
- 不是所有的“是一种”（is-a）的关系都用继承来建模。
- 继承是用来为“是一种”关系建模的。不要仅仅为了重用方法这个原因而盲目的继承一个类。
- Java 不可以多继承，一个 Java 类只可能直接继承一个父类。但可以用接口实现多重继承。
### 11.3 使用super关键字
> 关键字 super 指代父类，可以用于调用父类中的普通方法和构造方法。
#### 11.3.1 调用父类的构造方法
> 父类的构造方法不会被子类继承。它们只能使用关键字 super 从子类的构造方法中调用。

    super();// 调用父类的无参构造方法
    super(arguments);// 调用父类与 arguments 的匹配的构造方法
    其必须出现在子类构造方法的第一行，这是显式调用父类构造方法的唯一方式。
    在子类中调用父类构造方法的名字会引起一个语法错误。
#### 11.3.2 构造方法链
> 构造方法可以调用重载的构造方法或父类的构造方法。若其都没有被显式的调用，编译器就会自动的将 super() 作为构造方法的第一条语句。

    故一般情况下，做好能为每一个类提供一个无参构造方法，以便对于该类进行继承，同时避免错误。
> 
    在任何情况下，构造一个类的实例时，将会调用沿着继承链的所有父类的构造方法。
    当构造一个子类的对象时，子类的构造方法会在完成自己的任务之前，首先调用它的父类构造方法。
    
    public class Faculty extends Employee{
    public static void main(String[] args){
        new Faculty();
    }
    public Faculty(){
        System.out.print("(4)");
    }
    }
    class Employee extends Person{
        public Employee(){
            this("(2)");
            System.out.print("(3)");
        }
        public Employee(String s){
            System.out.print(s);
        }
    }
    class Person{
        public Person(){
            System.out.print("(1)");
        }
    }
    // 输出 (1)(2)(3)(4)
#### 11.3.3 调用父类的普通方法
> 调用父类的普通方法所用语法

    super.方法名(参数);
### 11.4 方法重写
> 要重写一个方法，需要在子类中使用和父类一样的签名来对该方法进行定义。

> 子类从父类中继承方法。有时，子类需要修改父类中定义的方法的实现，这称为方法重写( method overriding )

> 重写需要注意的几点

    1. 重写的方法必须与被重写的方法具有一样的签名，以及一样或者兼容的返回类型。
        兼容即重写方法的返回类型可以是被重写方法的返回类型的子类型。
    2. 仅当实例方法可访问时，它才能被重写。
    3. 与实例方法一样，静态方法也能被继承。但是静态方法不能被重写。
        如果父类中定义的静态方法在子类中被重新定义，那么在父类中定义的静态方法将被隐藏。
        可以通过使用 父类名.静态方法名(SuperClassName.staticMethodName) 调用隐藏的静态方法
### 11.5 方法重写于重载
> 重载意味着使用同样的名字但是不同的参数列表来定义多个方法。

> 重写意味着在子类中提供一个对方法的新的实现。

- 重载需要注意的几点
    - 方法重写发生在具有继承关系的不同类中；方法重载可以发生在同一个类中，也可以发生在具有继承关系的不同类中
    - 方法重写具有同样的签名，方法重写具有同样的名字但是参数列表
>
    为了避免错误，可以使用一种特殊的 Java 语法，称为重写标注（override annotation）
        即在子类的方法前面放一个 @Override
    
    public class Circle extends GeometricObject{
        @Override// 又此标注的地方必须重写一个父类的方法，否则报错
                 // 若不使用此标注而重写父类的方法，不会报错
        public String toString(){
            return super.ToString +"\nradius is" + radius; 
        }
    }
### 11.6 Object类及其 toString()
> Java 中的所有类都继承自 java.lang.Object 类
    
    如果在定义一个类时没有指定继承，那么这个类的父类默认是 Object。

    Object 类的 toString() 方法的签名
    public String toString()
    调用一个对象的 toString() 会返回一个描述该对象的字符串。默认情况下，它返回一个该对象所属的类名
    和 @加其用十六进制形式表示的该对象的内存地址组成的字符串。
>
    System.out.println(object); <=> System.out.println(object.toString());
### 11.7 多态
> 多态意味着父类型的变量可以引用子类型的对象。

    实现条件 ：继承 重写 父类引用指向子类的对象
### 11.8 动态绑定
> 方法可以在沿着继承链的多个类中实现。JVM 决定运行时调用哪个方法。

> 方法可以在父类中定义而在子类中重写。

    Object o = new GeometricObject();
    System.out.println(o.toString());
    // 声明类型（declared type）：一个类型必须被声明为某种类型
    // 实际类型（actual type）：是被变量引用的对象的实际类。
        一个引用类型变量可以是一个 null 值或是一个对声明类型的实例的引用。
        实例可以使用声明类型或它的字类型的构造方法创建。
    在这里，o 的实际类型是 GeometricObject，因为 o 引用使用 new GeometricObject() 创建的对象。
    o 调用那个 toString() 方法由 o 的实际类型决定，这叫动态绑定（dynamic binding）
> 
    public classDynamicBinding{
        public static void main(String[] args){
            m(new GraduateStudent());
            m(new Student());
            m(new Person());
            m(new Object());
        }
        public static void m(Object x){
            System.out.print(x.toString());
        }
    }
    class GraduateStudent extends Student{}
    class Student extends Person{
        @Override
        public String toString(){
            return "Student";
        }
    }
    class Person extends Object{
        @Override
        public String toString(){
            return "Person";
        }
    }
    // 输出 StudentStudentPersonjava.lang.Object@66048bfd
    // 引用变量的声明类型决定了编译是匹配那个方法
    // 在编译时，编译器会根据参数类型，参数个数和参数顺序找到匹配的方法。
    // 一个方法可能在沿着继承链的多个类中实现。
    // Java 虚拟机在运行时动态绑定方法实现，这是由变量的实际类型决定的。
### 11.9 对象转换和 instanceof 操作符
> 对象转换是一个对象的引用可以类型转换为对另外一个对象的引用

    m(new Student());
    等价于
    Object o = new Student();// 由于 Student 的实例也是 Object 的实例，故其合法，它称为**隐式转换**（implicit casting）
    m(o);
> 
    但是 Student b = o;
    会发生编译错误 因为 Student 对象总是 Object 的实例，但是 Object 对象不一定是 Student 的实例。
>
    若Object 对象是 Student 的实例，我们可以用使用显式转换（explicit casting）如下
         Student b = (Student)o;//
> 向上转换 子变父

> 向下转换 父变子 这时必须使用转换标记“(子类名)”进行显式转换

> 若父类对象不是子类的一个实例，就会出现一个运行时异常 ClassCastException。

    处理方法是在进行显式转换之前判断该对象是否是另一个对象的实例。可以使用操作符 instanceof 来实现
    void someMethod(Object myObject){
        if(myObject instanceof Circle){                     // . 优先于类型转换操作符
            System.out.println("The circle diameter is " + ((Circle)myObject).getDiameter);
        }
    }
> instanceof 是 Java 的关键字。 Java 的关键字的每个字母都是小写的。
### 11.10 Object 类的 equals 方法
    Object 类的 equals() 方法的签名
    public boolean equals(Object o)
    其默认实现是
     public boolean equals(Object obj){
         // 检测两个引用变量是否指向同一个对象
         // 常常根据需求被重写
         return (this == obj);
     }
>
    equals 方法在 Java API 的许多类中被重写，比如 java.lang.String 和 java.util.Date 
    中用于比较两个对象的内容是否相等
> 
    比较操作符 == 用来比较两个基本数据类型的值是否相等，或者判断两个对象是否具有相同的引用

    在子类中，使用签名 equals(SomeClassName obj) 重写 equals 方法是错误的
    应该是 equals(Object obj) 
### 11.11 ArrayList 类
> ArrayList对象可以用于储存一个不定对象列表。
    数组一旦被创建它的大小就固定了
> ArrayList是一个泛型类, 泛型 E 不可为基本数据类型 如 int 但可以使用 Integer

    java.util.ArrayList<E>
    +ArrayList()// 创建一个空的列表

    +add(e: E): void// 增加一个新元素 e 到该列表的未尾

    +add(index: int,e: E): void// 增加一个新元素 e 到该列表的指定下标处

    +clear(): void// 删除列表中的所有元素

    +contains(o: Object): boolean// 如果该列表包含元素 o ，则返回 true

    +get(index: int): E// 返回该列表指定下标位置的元素

    +indexOf(o: Object): int// 返回列表中第一个匹配元素的下标

    +isEmpty(): boolean// 如果该列表不包含任何元素，则返回 true

    +lastIndexOf(o: Object)//返回列表中最后一个匹配元素的下标

    +remove(o: Object): boolean// 去除列表中的第一个元素，若去除，则返回 true

    +size(): int// 返回列表中的元素个数

    +remove(index: int): E// 去除列表中的指定下标位置的元素，若去除，则返回被去除的元素

    +set(index: int,e: E): E// 设置指定下标位置的元素

    创建一个 ArrayList 的方法
    ArrayList<AConcreateType> list = new ArrayList<AConcreateType>();
    ArrayList<AConcreateType> list = new ArrayList<>();
### 11.12 关于列表的一些有用方法
- 从数组中创建列表
>
    String[] array = {"red","green","blue"};
    ArrayList<String> list = new ArrayList<>(Arrays.asList(array));
- 从列表中创建数组
>
    String[] array = new String[list.size()];
    list.toArray(array);
- 对列表排序并找出最大最小值和随机打乱
》
    Integer[] array = {3,5,95,4};
    ArrayList<Integer> list = new ArrayList<>(Arrays.asList(array));
    java.util.Collection.sort(list);
    java.util.Collection.max(list);
    java.util.Collection.min(list);
    java.util.Collection.shuffle(list);
### 11.13 protected 数据和方法
> public protected private 都称为可见性修饰符（visibility modifier）或可访问性修饰符（accessibility modifier）

| | | | ||
-:|:-:|:-:|:-:|:-:|
类中成员的修饰符|同类可访|同包可访|不同包的子类可访|不同包可访|
public        |       O|      O|             O|         O|
protected     |       O|      O|             O|         X|
default       |       O|      O|             X|         X|
private       |       O|      X|             X|         X|
|||||
> 类可以以两种方式使用:一种是用于创建该类的实例；另一种是通过继承该类创建它的子类

> protected 和 private 只能用于类的成员，public 和 default 可以用于类和类的成员

> 一个没有修饰符的类是不能用其他包中的类访问的

> 子类可以重写其父类的 protected 方法并将其可见性该为 public，但不能将 public 变为 protected 
### 11.14 防止继承和重写
> 一个被 final 修饰的类和方法都不能被继承。被 final修饰的数据域是一个常数。

    public static final 顺序
## 12 异常处理和文本I/O
### 12.1 引言
> 异常是运行时错误。异常处理使得程序可以处理运行时错误，并继续通常的执行。

    在程序运行的过程中，如果 JVM 检测出一个不可能执行的操作就会出现运行时错误(runtime error)。
        如，若使用越界下标访问数组，会产生 ArrayIndexOutOfBoundsException
            若输入整数时输入了 double 值，会得到一个 InputMismatchException
    
    在 Java 中，运行时错误会作为一个异常抛出。
    异常就是一种对象。表示阻止正常运行的错误或情况。如果异常没有被处理，那么程序会非正常终止。
    如何处理异常是本章讨论的主题。
### 12.2 异常处理概念
> 异常是从方法抛出的。方法的调用者可以捕获以及处理该异常。

    import java.util.Scanner;
    public class Faculty {
        public static int quotient(int number1,int number2){
            if(number2 == 0){
                // throw 语句的执行称为抛出一个异常(throwing an exception)
                // 异常就是一个从异常类创建的对象，
                // 这个情况下，异常类就是 java.lang.ArithmeticException。
                // 构造方法 ArithmeticException(str) 被调用以构建一个异常对象
                // str 是用于描述异常的消息
                // 当异常被抛出时，正常的执行流程被中断。
                // “抛出异常的”就是将异常从一个地方传递到另一个地方。
                // 调用方法的语句包含在一个 try 块和 catch 块中
                throw new ArithmeticException("Divisor cannot be zero");
            }
            return number1/number2;
        }
        public static void main(String[] args){
            Scanner input = new Scanner(System.in);
            
            System.out.println("Enter two integers");

            int number1 = input.nextInt();
            int number2 = input.nextInt();
            
            try{
                // try 块包含了正常情况下执行的语句，
                int result = quotient(number1,number2);
                System.out.println(number1+" / "+number2+" is "+result);
            }   
                    // 标识符 ex 的作用很像是方法中的参数，故这个参数称为 catch 块的参数
                    // ex前的类型（如 ArithmeticException）指定了可以捕获的异常类型
                    // 一旦捕获该异常，就能从 catch 块中的参数访问这个抛出的值
            catch (ArithmeticException ex){
                // 异常被 catch 块所捕获。catch 块中的代码被执行以处理异常。
                // 之后 catch 块的语句被执行。
                System.out.println(" Exception: an integer "+"cannot be divided by zero ");
            }
            
            System.out.println("Execution continues");
        }
    }
> 
    throw 语句类似于方法的调用，但不同于调用方法的是，它调用的是 catch 块。
    catch 块就像带参数的方法定义，这些参数匹配抛出的值的类型。
    但是，在执行完 catch 块之后，程序控制不返回 throw 语句；而是执行 catch 块后的下一条语句
### 12.3 异常类型
> 异常是对象，而对象都采用类来定义。异常的根类是 java.lang.Throwable
> 预设异常类的关系

    - Object
        - Throwable
            - Error(系统异常)
                - LinkageError
                - VirtualMachineError
            - Exception(异常)
                - ClassNotFoundException// 试图使用一个不存在的类
                - IOException // 输入输出相关的操作
                - RuntimeException // 运行时异常，它同系统异常一样不需要检查
                    - ArithmeticException // 一个整数除以 0
                    - NullPointerException // 试图通过一个 null 引用变量来访问一个对象
                    - IndexOutOfBoundsException // 数组的下标超出范围
                    - IllegalArgumentException // 传递给方法的参数非法或不合适

    Error(系统异常)和 RuntimeException 以及它们的子类都时免检异常( unchecked exception)
    其他的异常称为必检异常(checked exception), 意味着编译器会强制 coder 检查并通过 
    try-catch 块处理它们
### 12.4 关于异常处理的更多讨论
> 异常的处理器是通过从当前的方法开始，沿着方法调用链，按照异常的反向传播方向找到的。

    Java 的异常处理模型基于三种操作：声明一个异常( declaring an exception ),
    抛出一个异常( throwing an exception) 和捕获一个异常( catching an exception )
#### 12.4.1 声明异常
    在 Java 中，当前执行的语句必属于某个方法。Java 解释器调用 main 方法开始执行一个程序
    每个方法都必须声明它可能抛出的必检异常的类型。这称为声明异常。
> 
    因为免检异常在任何代码中都可能存在。
    只有必检异常在方法头中显式声明，这样，方法的调用者会被告知有异常
    在方法中声明一个异常
    public void myMethod() throws Exception1,Exception2,...,ExceptionN{}
> 注意在父类中的方法没有声明异常，那么就不能在子类中对其重写时声明异常
#### 12.4.2 抛出异常
> 检测到错误的程序可以创建一个合适的异常类型的实例并抛出它，称抛出一个异常

    如下
    IllegalArgumentException ex = new IllegalArgumentException("wrong Argument");
    throw ex;
    或 throw new IllegalArgumentException("wrong Argument");
    
    IllegalArgumentException 是 Java API 中的一个异常类。
    通常，Java API 中的每个异常类至少有两个构造方法：一个无参一个带可以描述这个异常的 String 参数的构造方法。
    该参数称为异常消息(exception message),它可以通过一个异常对象调用 getMessage() 获取。
> 声明异常的关键字是 throws 抛出异常的关键字是 throw
#### 12.4.3 捕获异常
> 处理方法如下

    try{
        // statement
    }
    catch(Exception1 exVar1){
        handler for exception1;
    }
    catch(Exception2 exVar2){
        handler for exception2;
    }
    ...
    catch(ExceptionN exVarN){
        handler for exceptionN;
    }
    // 还可以是 
    catch(Exception1 |Exception2 |...|ExceptionN ex){
        // 每个异常类型使用一个 |
        handler for exception;
    }
> 如果在执行 try 块的过程中没有出现异常，则跳过 catch 语句

    如果 try 块中的某条语句抛出一个异常， Java 就会跳过 try 块中剩余的语句，然后开始查找处理这个异常的代码

    处理这个异常的代码称为异常处理器(exception handler);可以从当前的方法开始，沿着方法调用链，按照异常的反向

    传播方向找到这个处理器。从第一个到最后一个逐个检查 catch 块，判断在 catch 块中的异常类实例是否是该异常对象的

    类型。如果是就将该异常对象赋值给所声明的变量，然后执行 catch 块中的代码。如果没有发现异常处理器，Java 会退出这
    
    个方法，把异常传递给这个方法的调用者，继续同样的过程来查找处理器。如果在调用的方法链中找不到处理器，程序就会终止

    并且在控制台上打印出错误的信息。查找处理器的过程称为捕获一个异常。
> 各种异常类可以从一个共同的父类中派生。如果一个 catch 块可以捕获一个父类的异常对象，它就能捕获那个父类的所以子类的异常对象。
#### 12.4.4 从异常中获取信息
    可以利用 java.lang.Throwable 中的实例方法来获取和有关异常的信息
>
    java.lang.Throwable 
    +getMessage(): String// 返回描述该异常对象的信息
    +toString(): String// 返回三个字符串的连接 1.异常类的全面 2.": " 3.getMessage() 方法
    +printStackTrace(): void// 在控制台上打印 Throwable 对象和它的调用栈的跟踪信息
    +getStackTrace(): StackTraceElement[]// 返回一个栈跟踪元素的数组，表示和该异常对象相关的栈的跟踪信息
#### 12.4.5 a dome
    public class Faculty{
    public static void main (String[] argc){
        try{
            Faculty f1 = new Faculty(5);
            Faculty f2 = new Faculty(-5);
            Faculty f3 = new Faculty(0);
        }
        catch (IllegalArgumentException ex){
            System.out.println(ex);
        }
        // 输出 1
        System.out.println(" Number of Objects created:"+ Faculty.getNumberOfObject());
    }
    private double radius;
    private static int numberOfObject = 0;
    public Faculty(double newRadius){
        setRadius(newRadius);
        numberOfObject++;
    }

    public void setRadius(double newRadius) throws IllegalArgumentException{
            if(newRadius >= 0){
                radius = newRadius;
            }
            else throw new IllegalArgumentException("Radius cannot be negative");
        }
    public static int getNumberOfObject(){
        return numberOfObject;
    }
   
}
### 12.5 finally 子句
> 无论异常是否产生，finally 子句总会被执行

    try{
        // statement
    }
    catch(Exception1 exVar1){
        handler for exception1;
    }
    finally{
        // finallyStatement
    }
    // 即使 catch 中有一个return，还会执行
### 12.6 何时使用异常
> 在一个项目中多个类都会发生的共同异常应该考虑为其设计一个异常类
### 12.7 重新抛出异常
> 若异常处理器不能处理一个异常，或者只是简单的希望它的调用者注意到该异常， Java 允许该异常处理器重新抛出。

    语法如下
    try{
        // statement
    }
    catch(Exception ex){
        // 执行操作之前退出
        throw ex;
        // 重新抛出给调用者，以便调用者的其他处理器获得处理异常 ex 的机会
    }
### 12.8 链式异常
> 与一个异常一起抛出一个异常，构成了链式异常

    public class ChainedException{
        public static void main (String[] argc){
            try{
                method1();
            }
            catch (Exception ex){
            ex.printStackTrace();
            }
        }

        public static void method1()throws Exception{
            try{
                method2();
            }
            catch (Exception ex){
                throw new Exception("new info from method1",ex);
            }
        }
        public static void method2()throws Exception{
            throw new Exception("new info from method1");
        }
    }
### 12.9 创建自定义异常类
### 12.10 File 类
> File 类包含了获得一个文件/目录的属性，以及对文件/目录进行改名和删除的方法

    java.io.File
    +File(pathname: String)//为一个指定的路径名创建一个 File 对象。路径名可能是一个目录或者一个文件

    +File(pathname: String,child: String)// 在目录 parent 下创建一个子路径的 File 对象。parent 是一个 File 对象。
                                         // 之前的构造方法中，parent 是一个字符串

    +exists(): boolean// File 对象代表的文件或目录存在，返回 true 

    +canRead(): boolean// File 对象代表的文件存在且可读，返回 true 

    +canWrite(): boolean/// File 对象代表的文件存在且可写，返回 true 

    +isDirectory(): boolean// File 对象代表的是一个目录，返回 true 

    +isFile(): boolean// File 对象代表的是一个文件，返回 true 

    +isAbsolute(): boolean// File 对象是采用绝对路径名创建的，返回 true 

    +isHidden(): boolean// 若 File 对象代表的文件是隐藏的，返回 true 

    +getAbsolutePath(): String// 返回 File 对象代表的完整的文件或目录的绝对路径名

    +getCannoicationPath(): String// 返回 File 对象代表的完整的文件或目录的相对路径名

    +getName(): String// 返回文件名

    +getPath(): String// 返回 File 对象代表的完整的文件或目录的绝对路径名

    +getParent(): String// 返回父路径(绝对路径名)

    +lastModified(): long// 返回文件最后修改时间

    +length():long// 返回文件的大小，若不存在或是一个目录的话，返回 0

    +listFile(): File[]// 返回一个目录 File 对象下面的文件

    +delete(): boolean// 删除 File 对象代表的文件或目录。若删除成功，方法返回 true 

    +renameTo(dest: File): boolean// 将该 File 对象代表的文件或目录该名为 dest 中指定的名字。如操作成功，方法返回 true 

    +mkdir(): boolean// 创建该 File 对象代表的目录。若目录创建成功，方法返回 true 

    +mkdirs(): boolean// 和 mkdir() 相同，除了在父目录不存在的情况下，将父目录不存在的情况下，将其一并创建
### 12.11 文件的输入于输出
> 使用 Scanner 类从文件中读取文本数据，使用 PrintWriter 类向文本文件写入数据

    File 对象封装了文件或路径的属性，但是它即不包括创建文件的方法，也不包括向/从文件读/写数据（称为数据的输入
    输出简称I/O）的方法。

    有两种类型的文件：文本和二进制的。文本文件的本质上是储存在磁盘上的字符。
#### 12.11.1 使用 PrintWriter 来写数据
>  PrintWriter 类可用来创建一个文件并向文本文件写入数据。首先要创建一个 PrintWriter 对象。如下

    PrintWriter output = new PrintWriter(filename);
>
    java.io.PrintWriter 
    +PrintWriter(file: File)// 为指定文件夹对象创建一个 PrintWriter 对象
    +PrintWriter(filename: String)// 为指定文件名字符串创建一个 PrintWriter 对象
    +print(s: String): void// 将字符串写入文件
    +print(c: char): void//
    +print(cArray: char[]): void//
    +print(i: int): void//
    +print(l: long): void//
    +print(f: float): void//
    +print(d: double): void//
    +print(b: boolean): void//
>
    public class WirteData{
    public static void main(String[] args)throws java.io.IOException{
        java.io.File file = new java.io.File("scores.txt");
        if(file.exists()){// 若该文件存在则退出
            System.out.println("File Exists");
            System.exit(1);
        }
        // 若不存在 PrintWriter 创建一个新文件
        // System.out 是代表控制台的标准 Java 对象。
        java.io.PrintWriter output = new java.io.PrintWriter(file);
        
        output.print("john T smith");
        output.println(90);
        output.print("eric k jones");
        output.print(85);
        // 必须使用完后关闭
        output.close();
    }
}
#### 12.12.2 使用 try-with-resources 自动关闭资源
    public class WirteDataWithAutoClose{
        public static void main(String[] args)throws java.io.IOException{
            java.io.File file = new java.io.File("scores.txt");
            if(file.exists()){
                System.out.println("File Exists");
                System.exit(0);
            }
            // 关键字 try 声明和创建一个资源。资源放在 () 中。资源必须是 AutoCloseable 的子语句
            // 声明和创建必须在同一行语句
            try(
                java.io.PrintWriter output = new java.io.PrintWriter(file);
                )
            {
                // 在 {} 中使用资源 这个块结束后，资源的 close() 方法自动调用
                output.print("john T smith");
                output.println(90);
                output.print("eric k jones");
                output.print(85);
            }
        }
    }
#### 12.11.3 使用 Scanner 读取数据
> Scanner 类用来从控制台读取字符串和基本类型值。

> 为从键盘读取，需要为 Syatem.in 创建一个 Scanner 如下

    Scanner input = new Scanner(System.in);
> 为从文件中读取，需要为文件类创建一个 Scanner 如下

    Scanner input = new Scanner(new File(filename));
>
    java.util.Scanner
    +Scanner(scource: File)// 创建一个 Scanner，从指定的文件中产生扫描的值
    +Scanner(scource: String)// 创建一个 Scanner，从指定的字符串中产生扫描的值
    +close()// 关闭 Scanner
    +hasNext(): boolean// 如果 Scanner 还有更多数据可以读取，则返回 true
    +next(): String// 从 Scanner 读取下一个标记作为字符串返回
    +nextLine(): String// 从 Scanner 读取一行作为字符串返回
    +nextByte(): byte// 从 Scanner 读取下一个标记作为byte返回
    +nextShort(): short
    +nextInt(): int
    +nextLong(): long
    +nextFloat(): float
    +nextDouble(): double
    +useDelimiter(pattern: String):Scanner// 设置 Scanner 的分隔符，并且返回 Scanner
                                          // 默认分割符是空格
> 
    import java.util.Scanner;
    class Faculty{                          // 构造方法 new Scanner(new java.io.File("scores.txt"))
                                            // 可能抛出 I/O 异常
        public static void main(String[] args)throws Exception{
            
            Scanner input = new Scanner(new java.io.File("scores.txt"));

            while(input.hasNext()){
                String firstName = input.next();
                String mi = input.next();           // scores.txt
                String lastName = input.next();     // john T smith 90
                int score = input.nextInt();        // eric k jones 85
                System.out.println(firstName+" "+mi+" "+lastName+" "+score);//
            }
            input.close();
        }
    }
#### 12.11.4 Scanner 如何工作
> 一个标记读取方法首先跳过任意分隔符，然后读取一个以分隔符结束的标记。

> 然后针对使用的方法 next基本类型() 就被分别被自动转换为一个对应的基本类型的值。

> 若不能转换就会抛出一个运行异常 java.util.InputMismatchException
### 12.12 从 Web 上读取数据
## 13 抽象类和接口
### 13.1 引言
> 父类中定义了相关的子类中的共同行为，接口可以用于定义类的共同行为
### 13.2 抽象类
> 抽象类不可用于创建对象。抽象类可以包含抽象方法，这些方法将在具体的子类中实现

    // 抽象类和常规类很像，但是不能使用 new 操作符创建它的实例。
    // 抽象类在类的头部使用 abstract 修饰符表示该类为抽象类。
    public abstract class ClassName{
        private dataType data;
        // 抽象类的构造方法定义为 protected，因为其只能被子类使用。
        // 创建一个具体子类的实例时，其父类的构造方法被调用初始化定义的数据域。
        protected ClassName(){
            method
        }
        // 抽象方法只有定义没有实现。它的实现由子类提供。
        // 一个包含抽象方法的类必须声明为抽象类。
        public abstract dataType methodName();
    }
#### 13.2.1 为何使用抽象方法
> 可以使用动态绑定。
#### 13.2.1 抽象类的几点说明
- 抽象方法不能包含在非抽象类中。若抽象父类的子类不能实现所有的抽象方法，那子类也必须定义为抽象类。

    即继承自抽象类的非抽象子类中，必须实现所有的抽象方法。抽象方法是非静态的。
- 抽象类不能使用 new 操作符来初始化。但是，仍然可以定义它的构造方法，这个构造方法在它的子类的构造方法中调用。
- 包含抽象方法的类必须是抽象类。但可以定义一个不包含抽象方法的抽象类。
- 子类可以重写父类的方法并将它定义为抽象的。在当父类的方法实现在子类中变的无效时使用。但此时子类必须定义为抽象的。
- 即使子类的父类是具体的，这个子类也可以是抽象的
- 不能使用 new 操作符从一个抽象类创建一个实例，但是抽象类可以作用一种数据类型。因此，如下正确。
>
    AbstractBaseClass[] obj = new AbstractBaseClass[10];
    obj[0] = new subClass();
### 13.3 接口
> 接口是一种于类相似的结构，用于为对象定义共同的共同的操作。

> 接口和抽象相似，但是它的目的是指明相关或者不相关的对象的共同行为。

    // 限定符 接口  接口名
    modifier inferface InterfaceName{
        // 定义
        // 抽象方法签名 
    }
    public interface Edible{
        public abstract String howToEat();
    }
> 在 Java 中接口被看作一种特殊的类。就像常规类一样，每个接口都被编译为独立的字节码文件。使用接口很像抽象类。
- 可以使用接口作为引用变量的数据类型或类型转换的结果
- 接口不可使用 new 操作符创建接口实例
- 使用接口时需要 implements 关键字如下

    class Chicken implements Edible{}
>
    由于接口中所有的数据域都是 public static final 而且所有的方法都是 public abstract，所以Java 可以忽略这些修饰符
    public inferface T{
        public static final int k = 1; <=> int k = 1; 
        // 但在子类中实现是，必须是 public 的
        public abstract void p(); <=> void p(); 
    }
> Java 8的关于接口的新特性

    引入了使用关键字 default 的默认接口方法。
    一个默认接口方法中的方法提供了一个默认实现。
    实现该接口的类可以简单地使用方法的默认实现，或者使新的实现来重写该方法。

    还可以在接口中存在共有的静态方法。
    接口中的公有的静态方法和类的公有的静态方法一样使用。
### 13.4 Comparable 接口
>  Comparable 接口定义了 comparableTo 方法，用于比较对象。

    其定义如下
    package java.lang;
    public interface Comparable<E>{
        public int comparableTo(E o);
    // comparableTo 方法判断这个对象相对于给定对象 o 的顺序，并且当这个对象小于，等于或大于给定
    // 对象的 o 时，分别返回负整数 0 或正整数。
    }
### 13.5 Cloneable 接口
> Cloneable 接口指定了一个对象可以被克隆
    
    其定义如下
    package java.lang;
    public inferface Cloneable{}
    // 这个接口是空的。这种方法体为空的接口称为标记接口(marker interface)
    // 为定义一个实现 Cloneable 接口的自定义类，这个类必须重写 Object 类中的 clone() 方法
>
    Object 类中的定义的 clone 方法
    protected native Object clone() throws CloneNotSupportedException;

    1. native 表示这个方法不是用 Java 写的。
    2. 浅复制 => 如果一个数据域是基本类型复制它的值，如果是对象就复制他的引用
    3. 深复制 => 如果一个数据域是基本类型或对象都复制它的值。
    4. 上式为 protected 的而非 public 是因为不是每个对象都可以被克隆。若其可克隆则重写这个方法。
    5. 为啥 clone 方法不是定义在 Cloneable 接口中呢?
        因为 Java 提供了一个本地方法来执行一个浅复制以克隆一个对象。由于接口中的方法是抽象的，该本地
        方法不能在接口中实现。因此，Java 的设计者决定在 Object 类中定义了和实现本地 clone 方法。
### 13.8 接口和抽象类
> 一个类可以实现多个接口，但是只能继承一个父类。

    抽象类对变量无限制，但接口要求变量都是 public static final
    抽象类的子类通过构造方法链调用构造方法，接口没有构造方法，二者都不能用 new 操作符实例化
    抽象类对方法无限制，但接口要求可以包含 public 的抽象实例方法，public 的默认方法以及 public 的静态方法

    类是强关系，接口时弱关系。
### 13.9 类的设计原则
> 内聚性 一致性 封装性 清晰性 完整性 实例与静态 继承和聚合 接口和抽象类
## 17 二进制I/O
## 18 递归
[TOC]
JavaFX的内容在下一页  [JavaFX](JavaFX.md)




        