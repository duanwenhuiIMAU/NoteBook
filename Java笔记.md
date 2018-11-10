# java笔记
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
### 2.3 从控制台读取输入
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
                                        //当 beginInedx == endIndex 返回 长度为 0 的空字符串 当 beginInedx < endIndex
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
## 5 循环
    while do-while for
## 6 方法
### 6.1 定义方法
    public static int max （int num1，int num2）{//public static 为修饰符 int 为返回类型 （）内为 形式参数 max 为方法名 其第一个字母小写
        return int类型
    }
### 6.2 方法按值传参
### 6.3 重载方法
    //使用同样的名字来定义不同的方法  只要其参数列表不同即可
## 7 一维数组
### 7.1 声明数组变量
    1. double[] myList;
    2. double myList[];
### 7.2 创建数组
    1. myList = new double[10];
    2. double[] myList = new double[10];
### 7.3处理数组
#### 7.3.1 使用输入值初始话数组
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
    myList[myList.length() - 1] = temp;
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
## 9 对象和类
### 9.1 一个类
    //    类名头字大写
    class Circle{
        double radius = 1;//数据域
        //以下构造方法两个
            1.构造方法必须和所在类的名字想同
            2.构造方法没有返回值类型，甚至连 void 也没有
            3.构造方法是在创建一个对象时由 new 操作符调用的，其作用是初始化对象
            4.构造方法也可以重载
        Circle(){
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
    2.局部变量和类变量同名局部变量优先
### 9.6 this 指针
###
###
###
###
###
##
##
##
##
##
##
##
##
##
##
##
##
###
###
###
###
###
###
###
###
###
###
###
        