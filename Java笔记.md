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
### 8.3 将二维数组传递给方法
    public static int[][] getArray(int [][] m){
        Scanner input = new Scanner(System.in);

        System.out.println ("Enter " + m.length + " rowa and " + m[0].length + "columns:");
       // loop
       return m;
    }
## 9 对象和类
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
    +Random(seed : long)    //以一个特定值作为种子创建一个 Random 对象
    +nextInt() : int        //返回一个随机的 int 值
    +nextInt(n : int) : int //返回一个 0 到 n（不包括 n）之间的随机的 int 值
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
### 10.1.1 类的抽象和封装
> 类的抽象是指类的实现和类的使用分离开，实现的细节被封装并且对用户ying












## 14 JavaFX 基础
### 14.1 JavaFX 程序的基本结构
    import javafx.appliction.Application;// 客体
    import javafx.scene.Scene;// 场景
    import javafx.scene.control.Button;// 按钮
    import javafx.stage.Stage;// 舞台

    public class MyJavaFX extends Application{// 继承客体
        @Override// 重写 start 方法
        public void start(Stage primaryStage){
            // 创建一个场景并放入一个 button
            Button btOk = new Button ("OK");
            Scene scene = new Scene (btOK,200,200);// 设置了 Scene 中的结点和其初始宽高
                                                // 若不想让用户改变 Stage 的大小则
                                                // stage.setResizable(false);
            // 还可以 Scene scene = new Scene (new Button ("OK"),200,200);
            primaryStage.setTitle ("MyJavaFx");//设置窗口标题
            primaryStage.setScene(scene);//将场景放入舞台
            primaryStage.show();//显示舞台
        }
        public static void main(String args[]){
            // 有这个 main 方法则自己调用，否则 jvm 调用
            Application.launch(args);//main中无此句不调用
        }
    }

### 14.2 面板，组，UI 组件以及形状
> 上面的程序无论如何改变窗体的大小，按钮总是位于场景的中间并且总之占据整个窗体。
- 解决方法
    - 设置按钮的位置和大小属性
    - 使用面板（Pane）的容器类

            可以自动的将结点布局在期望的位置和大小
            具体是将结点放在面板上，再将面板放在场景中
        
>
- 结点是可视化的组件
    
    1.形状 如 文本 直线 圆 椭圆 矩形 弧 多边形 折线

    2.UI 组件 如 标签（Label）按钮（Button）复选框（）单选按钮（）文本域（TextField）文本输入区域（）

    3.组是将结点集合进行分组的容器，将变换或效果应用于一个组上，这将自动应用以组中的每一个子结点上。
***
    这几这的关系图    
                                |——-|
                                |   V
    Stage <- Scene <- Parent ---|->node <- Shape{Line,Circle,Ellipse,Rectangle
                      |         |   |               ,Arc,Polygon,Ployline,Text}
                      |      |——|   V
                      |      |     ImageView(显示图形，UI 组件)
                      V      |
                    {Group， Pane，Control}      
                              |       |------->{Button，CheckBox，RadioButton，TextArea}
                              V
             {FlowPane,GridPane,BorderPane,HBox,VBox,StackPane}
***
    // Button in Pane
    import javafx.appliction.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.stage.Stage;
    import javafx.scene.layout.StackPane;
    public class MyJavaFX extends Application{
        @Override
        public void start(Stage primaryStage){
            StackPane pane = new StackPane();
            // 每个面板和组都有一个无参构造方法和将一个或多个字结点加入面板的构造方法
            //故上下两句可以用StackPane pane = new StackPane(new Button ("OK"));简化
            pane.getChildren().add(new Button ("OK"));// 将结点放在面板上
            Scene scene = new Scene (pane,200,50);// 再将面板放在场景中
            primaryStage.setTitle (" Button in Pane ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
>
    // Circle in Pane
    import javafx.appliction.Application;
    import javafx.scene.Scene;
    import javafx.stage.Stage;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.Color;
    import javafx.scene.shape.Circle;
    public class MyJavaFX extends Application{
        @Override
        public void start(Stage primaryStage){
            // Java 图形的尺寸单位为 px （像素）
            // Java 面板的左上角为（0，0）
            Circle circle = new Circle();// 创建一个圆 
            circle.setCenterX(100);// 其圆心在 （100，100）位置 
            circle.setCenterY(100);// 此位置也是场景的中心因为new Scene (pane,200,200)
            circle.setRadius(50);// 其半径为 50 
            circle.setStroke(Color.BLACK);// 笔画颜色 =》黑
            circle.setFill(Color.WHITE);// 填充颜色 =》白 若为 null 则无色

            StackPane pane = new StackPane();
            pane.getChildren().add(circle);
            Scene scene = new Scene (pane,200,200);
            primaryStage.setTitle (" Circle in Pane ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
### 14.3 属性绑定
> 属性绑定是将一个目标对象绑定到源对象中，源对象的修改将自动反映到目标对象中。

    即源对象改变目标对象也自动改变，目标对象称绑定对象或绑定属性，源对象称可绑定对象或可观察对象。如下
    //
    import javafx.beans.property.DoubleProperty;
    import javafx.beans.property.SimpleDoubleProperty;
    public class BindingTest{
        public static void main(String[] args){
       // DoubleProperty FloatProperty LongProperty IntegerProperty BooleanProPerty
       // 都是抽象类，它们的具体子类 SimpleDoubleProperty SimpleFloatProperty 
       // SimpleLongProperty SimpleIntegerProperty SimpleBooleanProPerty 用于产生这些属性的实例。
            DoubleProperty d1 = new SimpleDoubleProperty(1);
            DoubleProperty d2 = new SimpleDoubleProperty(2);
            d1.bind(d2);//将 d1（目标对象）绑定到 d2（源对象）
            System.out.println("d1 is " + d1.getValue() + "d2 is " + d2.getValue());
            //输出 d1 is 2.0 d2 is 2.0
            d2.setValue(70.2);//将 d2 的值变为 70.2
            System.out.println("d1 is " + d1.getValue() + "d2 is " + d2.getValue());
            //输出 d1 is 70.2 d2 is 70.2
        }
    }
>
    // Circle in Pane can Change
    import javafx.appliction.Application;
    import javafx.scene.Scene;
    import javafx.stage.Stage;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.Color;
    import javafx.scene.shape.Circle;
    public class MyJavaFX extends Application{
        @Override
        public void start(Stage primaryStage){
            StackPane pane = new StackPane();
            Circle circle = new Circle();
            // 将 centerX 和 centerY 分别绑定到面板的 width/2 和 heigth/2上
            // 使得在窗体改变大小后圆还居中
            circle.centerXProperty().bind(pane.widthProperty().divide(2));
            circle.centerYProperty().bind(pane.heigthProperty(),divide(2));
            circle.setRadius(50);
            circle.setStroke(Color.BLACK);
            circle.setFill(Color.WHITE);

            pane.getChildren().add(circle);
            Scene scene = new Scene (pane,200,200);
            primaryStage.setTitle (" Circle in Pane ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
>
    1.centerX 是 Circle 的一个属性，用于表示圆心的 x 坐标，该属性既是目标又是源。
    2.目标用 bind 方法和源绑定 => target.bind(scoure);
        bind 方法在javafx.beans.property.Property 接口中定义。
        源对象是 javafx.beans.value.ObervableValue 的一个实例, ObervableValue 是一个包装了值的实体，当值改变时可被观察
    3.绑定属性是一个对象。
        double float long int boolean String 的绑定属性分别的是
        DoubleProperty FloatProperty LongProperty IntegerProperty BooleanProPerty StringProperty
        这些属性也是 ObservableValue 的子类型。即它们既是目标又是源。
        前四个都有 add substract multiply divide 方法，对一个绑定属性中的值进行加减乘除后返回一个新的可观察属性。
    4.JavaFX 类中每个绑定属性（如 centerX ）都有一个获取方法(如 getCenterX() )和设置方法(如 setCenterX(double) ),
    同时还有一个获取方法返回属性本身，其命名方法是在属性名称后加 Property。（如 centerProperty() ）
        centerProperty() 返回一个 DoubleProperty 类的对象。
        具体代码是
            public class PropertyTest{
               // private PropertyType x;
               private DoubleProperty centerX;
               // public propertyValueType getX(){...}
               public double getCenterX(){
                   ruturn X;
               }
               // public void setX(propertyValueType value){...}
               public void setCenterX(double X){
                   this.X = X;
               }
               // public propertyType XProperty(){...}
               public DoubleProperty centerXProperty(){
                   return centerX;
               }
            }
>
    circle.centerXProperty().bind(pane.widthProperty().divide(2)); 
    等价于
        DoubleProperty centerX = circle.centerXProperty();
        DoubleProperty width = pane.widthProperty();
        centerX.bind(width.divide(2)); 
>
    上例都是单向绑定 有时需要同步两个属性，即双向绑定（即目标又是源，源又是目标）
    可以用 bindBidirectional
### 14.4 结点的共同属性和方法
> 本节介绍两个 style 和 rotate
- style 就是 JavaFX 的 CSS
    - 其语法为 styleName:value

    circle.setStyle("-fx-stroke: black;-fx-fill: red;");
    等价于   circle.setStroke(Color.BLACK);
            circle.setFill(Color.WHITE);
- rotate
    - 可以设定一个以度为单位的角度，让结点围绕它的中心旋转该角度 正值顺时针转，负值逆时针转
- contian(double x,double y)

    检测一个点是否位于结点的边界之内
- setScaleX(double scale) 和 setScaleX(double scale) 

    用于缩放一个结点
### 14.5 Color 类
> javafx.scene.paint.Color 是 Paint 的具体子类

    javafx.scene.paint.Color
    -red: double    //该 Coler 对象的红色值（0.0~1.0）
    -green: double  //该 Coler 对象的绿色值（0.0~1.0）
    -blue: double   //该 Coler 对象的蓝色值（0.0~1.0）
    -opacity: double//该 Coler 对象的透明度（0.0~1.0）
    +Color(r:double,g:double,b:double,opacity:double)//使用指定红绿蓝和透明度创建一个Color对象
    +color(r:double,g:double,b:double):Color//使用指定红绿蓝创建一个不透明的Color对象
    +color(r:double,g:double,b:double,opacity:double):Color//使用指定红绿蓝和透明度创建一个Color对象
    +rgd(r:int,g:int,b:int):Color//使用指定红绿蓝创建一个不透明的Color对象其值 0~255
    +rgd(r:int,g:int,b:int,opacity:double):Color//使用指定红绿蓝和透明度创建一个Color对象其值 0~255
    +brighter():Color//创建一个比该Color对象更亮的Color对象
    +darker():Color//创建一个比该Color对象更暗的Color对象
>
    还可以使用标准色
### 14.6 Font 类
> 设置字体名称 粗细 大小

    javafx.scene.text.Font
    -size: double// 字体大小
    -name: String// 字体名称
    -family: String// 字体系列
    +Font(size: double)
    +Font(name :String,size: double)
    +font(name :String,size: double)
    +font(name :String,w :FontWeigth,size: double)
    +font(name :String,w :FontWeigth,p :FontPosture,size: double)
    +getFontNames():List<String>
>
    Label label = new Label("JavaFx");
    label.setFont(Font.font("Times New Roman",FontWeight.BOLD,FontPosture.ITALIC,20));
### 14.7 Image 和 ImageView 类
> Image 类表示一个图形图像 和 ImageView 用于显现一个图像。

    javafx.scene.image.Image
    -error: ReadOnlyBooleanProperty// 表明图片是否正确载入
    -height: ReadOnlyDoubleProperty// 图片的高度
    -width: ReadOnlyDoubleProperty// 图片的宽度
    -progress: ReadOnlyDoubleProperty// 图像载入已经完成的大致百分比
    +Image(filenameOrURL: String)// 创建一个内容从一个文件或URL载入的 Image
- 用法
    - new Image("image/us.gif")//位于 Java 类目录下的 image 目录下的 us.gif
    - new Image("http://liveexample.pearsoncmg.com/book/image/us.gif")
>
    javafx.scene.image.ImageView
    -fitHeight: DoubleProperty// 图片改变大小来适应边界框的高度
    -fitWidth: DoubleProperty// 图片改变大小来适应边界框的宽度
    -x: DoubleProperty// ImageView原点的 x 坐标
    -y: DoubleProperty// ImageView原点的 y 坐标
    -image: ObjectProperty// 图像视图中的显示的图像
    +ImageView()// 创建一个 ImageView
    +ImageView(image:Image)// 使用给定的图像创建一个 ImageView
    +ImageView(filenameOrURL: String)// 使用从一个文件或URL载入的图像创建一个 ImageView
- 用法
    
     new ImageView("image/us.gif")；等价于
     Image image = new Image("image/us.gif");
     ImageView imageView = new ImageView(image);   
> 注 Image 对象可以被多个结点共享，而 ImageView 不可被多个结点共享。
### 14.8 布局面板和组
> 面板和组(group)是容纳结点的容器
>> Group 类常用于将结点组合成组并作为一个组进行转换和缩放。
>> 面板和 UI 组件对象是可以改变大小的，但是组，形状和文本对象是不能改变大小的。
- 面板
    - Pane => 布局面板的基类，它有 getChildren() 方法来返回面板中的结点列表
    - StackPane => 结点放置在面板中央，并且叠加在其他结点之上
    - FlowPane => 结点以水平方式一行一行地放置，或以垂直的方式一列一列的放置
    - GridPane => 结点放置在一个二维网格的单元格中，结点放在指定的下标的列和行中
    - BorderPane => 将结点放置在顶部，右边，底部，左边以及中间区域
    - HBox => 结点放在单行中
    - VBOx => 结点放在单列中
#### 14.8.1 FlowPane
> 结点以水平方式一行一行地放置，或以垂直的方式一列一列的放置,当一行或一列排满后就开始新的一行或一列。

    javafx.scene.layout.FlowPane
    -alignment: ObjectProperty<Pos>//该面板的整体对齐方式（默认：Pos.LEFT）
    -orientation: ObjectProperty<Orientation>//该面板的方向
                                            //(默认：Orientation.HORIZONTAL)
                                            //还可以是 Orientation.VERTICAL
    -hgap: DoubleProperty//结点之间的水平间距
    -vgap: DoubleProperty//结点之间的垂直间距
    +FlowPane()//创建一个默认的 FlowPane
    +FlowPane(hgap:double,vgap:double)//使用指定的水平和垂直间距创建一个 FlowPane
    +FlowPane(orientation: ObjectProperty<Orientation>)//使用指定的方向创建一个 FlowPane
    +FlowPane(orientation: ObjectProperty<Orientation>,hgap:double,vgap:double)
    //使用指定的方向,水平和垂直间距创建一个 FlowPane
>
    数据域alignment，orientation，hgap，vgap 是绑定属性。
>
    import javafx.appliction.Application;
    import javafx.geometry.Inserts;
    import javafx.scene.Scene;
    import javafx.control.Lebel;
    import javafx.control.TextField;
    import javafx.stage.Stage;
    import javafx.scene.layout.FlowPane;

     public class ShowFlowPane extends Application{
        @Override
        public void start(Stage primaryStage){
            FlowPane pane = new FlowPane();// 创建一个 FlowPane
            pane.setPadding(new Inserts(11,12,13,14));// 用 Inserts 方法设置它的 
                                                      //padding属性，
                //构造方法 Inserts 给出了以像素为单位的边框的大小，即顶11px，右12px，底13px，左14px。
            pane.setHgap(5);
            pane.setVgap(5);

            pane.getChildren().addAll(new Lebel("First Name :"),new TextFeild(),new Label("MI :"));
            // 每个 FlowPane 包含了一个 ObservableList 对象用于容纳结点，可以用 
            // getChildren() 方法来返回该列表。将一个结点添加到 FlowPane 中用的是 add(node)
            // 将多个个结点添加到 FlowPane 中用的是 addAll(node1,node2,...);
            // 可用 remove(node)来从列表中移除一个结点，用 removeAll(node1,node2,...)来从
            // 列表中移除全体结点。
            // 并且程序将标签和文本域添加到面板中。
            TextField tfMi = new TextField();
            tfMi.setPrefColumnCount(1);
            // 将 Mi 文本域的首选项列数设置为 1
            // 注  Mi 文本域 只能加到一个面板中，且只能加一次。
             pane.getChildren().addAll(new Lebel(tfNi,new Lebel("Last Name :"),new TextFeild());
            Scene scene = new Scene (pane,200,250);
            primaryStage.setTitle (" ShowFlowPane ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
#### 14.8.2 GridPane
    javafx.scene.layout.GridPane
    -alignment: ObjectProperty<Pos>//该面板的整体对齐方式（默认：Pos.LEFT）
    -gridLineVisible:BooleanProperty//网格线是否可见
    -hgap: DoubleProperty//结点之间的水平间距（默认：0）
    -vgap: DoubleProperty//结点之间的垂直间距（默认：0）
    +GridPane()//创建一个GridPane
    +add(child: Node,columnIndex: int,rowIndex: int):void //添加一个结点到指定的列和行
    +addColumn(columnIndex: int,child: Node ...):void //添加多个结点到指定的列
    +addRow(rowIndex: int,child: Node...):void //添加多个结点到指定的行
    +getColumnIndex(child: Node):int //对于指定的结点，返回列下标
    +setColumnIndex(child: Node,columnIndex: int):void//将一个结点设置到新的列，该方法重新放置结点
    +getRowIndex(child: Node):int //对于指定的结点，返回行下标
    +setRowIndex(child: Node,rowIndex: int):void//将一个结点设置到新的行，该方法重新放置结点
    +setHalighnment(child: Node,value: HPos):void //为单元格中的子节点设置水平对齐
    +setValighnment(child: Node,value: VPos):void //为单元格中的子节点设置垂直对齐
>
    import javafx.appliction.Application;
    import javafx.geometry.Inserts;
    import javafx.geometry.HPos;
    import javafx.geometry.Pos;
    import javafx.scene.Scene;
    import javafx.control.Button;
    import javafx.control.Lebel;
    import javafx.control.TextField;
    import javafx.stage.Stage;
    import javafx.scene.layout.GridPane;

    public class ShowGridPane extends Application{
        @Override
        public void start(Stage primaryStage){
            GridPane pane = new GridPane();// 创建一个 FlowPane
            pane.setAlignment(Pos.CENTER);//居中对齐，改变窗体，依然居中
            pane.setPadding(new Inserts(11.5,12.5,13.5,14.5));
            pane.setHgap(5.5);
            pane.setVgap(5.5);
            pane.add(new Lebel("First Name :"),0,0);//行和列的下标从0开始
                                                    //且并非每个单元格都需要填充
            pane.add(new TextFeild(),1,0);
            pane.add(new Label("MI :"),0,1);
            pane.add(new TextFeild(),1,1);
            pane.addRow(3,new Lebel("Last Name :"),new TextFeild());
            Button btAdd = new Button("Add Name");
            pane.add(btAdd,1,3);
            GridPane.setHalignment(btAdd,HPos.RIGHT);//使用静态方法 setHalignment() 
                                                     //将按钮在单元格中右对齐
            // 注 场景的大小没有设置，这时会根据放置在场景中的结点大小自动计算场景大小。
            Scene scene = new Scene (pane);
            primaryStage.setTitle (" ShowGridPane ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
#### 14.8.3 BorderPane 
    javafx.scene.layout.BorderPane 
    -top: ObjectProperty<Node>// 放置在顶部的结点（默认：null）
    -right: ObjectProperty<Node>// 放置在右边的结点（默认：null）
    -bottom: ObjectProperty<Node>// 放置在底部的结点（默认：null）
    -left: ObjectProperty<Node>// 放置在左边的结点（默认：null）
    -center: ObjectProperty<Node>// 放置在在中间的结点（默认：null）
    +BorderPane()//创建一个BorderPane 
    +BorderPane(node: Node)//创建一个BorderPane，其中结点放在面板中央
    +setAlighnment(child: Node,value: Pos):void //设置 BorderPane 中的结点的对齐方式
>
    import javafx.appliction.Application;
    import javafx.geometry.Inserts;
    import javafx.scene.Scene;
    import javafx.control.Button;
    import javafx.control.Lebel;
    import javafx.stage.Stage;
    import javafx.scene.layout.BorderPane;

     public class ShowBorderPane extends Application{
        @Override
        public void start(Stage primaryStage){
            BorderPane pane = new BorderPane();// 创建一个 FlowPane
            // 注 面板是一个结点故可以加入另一个面板
            // 要将一个结点移除 用setTop(null)
            //若这一区域没被占据，则不为其分配空间
            pane.setTop(new CustomPane("Top"));
            pane.setRight(new CustomPane("Right"));
            pane.setBottom(new CustomPane("Bottom"));
            pane.setLeft(new CustomPane("Left"));
            pane.setCenter(new CustomPane("Center"));
            Scene scene = new Scene (pane);
            primaryStage.setTitle (" ShowBorderPane");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
        class CustomPane extends StackPane{
            // 该类继承自 StackPane 
            public CustomPane(String title){
                // 该类的构造方法
                getChildren().add(new Label(title));//加入了一个具有指定标题的标签
                setStyle("-fx-border-color: red");//为边框颜色设置样式
                setPadding(new Insert(11.5,12.5,13.5,14.5));//设置内边框
            }
        }
    }
#### 14.8.4 HBox 和 VBox
> 与FlowPane 不同的是，HBox 和 VBox 只能将结点布局在一行或一列。

    //将结点置于一行
    javafx.scene.layout.HBox
    -alignment: ObjectProperty<Pos>//方框中子结点的整体对齐方式（默认：Pos.TOP_LEFT）
    -fillHeight: BooleanProperty//可改变的子结点是否自适应方框的高度（默认：ture）
    -spacing: DoubleProperty//两个结点的水平间距（默认：0）
    +HBox()//创建一个默认的 HBox
    +HBox(spacing: double)//使用结点间指定的水平间距创建一个 HBox
    +setMargin(node: Node,value: Inserts):void// 为面板中的结点设置边界
>
    //将结点置于一列
    javafx.scene.layout.VBox
    -alignment: ObjectProperty<Pos>//方框中子结点的整体对齐方式（默认：Pos.TOP_LEFT）
    -fillWidth: BooleanProperty//可改变的子结点是否自适应方框的高度（默认：ture）
    -spacing: DoubleProperty//两个结点的水平间距（默认：0）
    +VBox()//创建一个默认的 VBox
    +VBox(spacing: double)//使用结点间指定的水平间距创建一个 VBox
    +setMargin(node: Node,value: Inserts):void// 为面板中的结点设置边界
>
    import javafx.appliction.Application;
    import javafx.geometry.Inserts;
    import javafx.scene.Scene;
    import javafx.control.Button;
    import javafx.control.Label;
    import javafx.stage.Stage;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.VBox;

     public class ShowHBoxVBox extends Application{
        @Override
        public void start(Stage primaryStage){
            BorderPane pane = new BorderPane();
            pane.setTop(getHbox());           
            pane.setLeft(getVbox());            
            Scene scene = new Scene (pane);
            primaryStage.setTitle (" ShowHBoxVBox");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
        private HBox getHBox(){
            HBox hbox = new HBox(15);
            hbox.setPadding(new Insert(15,15,15,15));
            hbox.setStyle("-fx-border-color: gold");
            hbox.getChildren().add(new Button("CS"));
            hbox.getChildren().add(new Button("DS"));                  
            ImageView imageView = new ImageView("image/us.gif");
            hbox.getChildren().add(imageView); 
            return hbox;
        }
        private VBox getVBox(){
            VBox vbox = new VBox(15);
            vbox.setPadding(new Insert(15,5,5,5));
            vbox.getChildren().add(new Button("CS"));
            vbox.getChildren().add(new Lebel("Courses"));
            Lebel[] courses = {new Lebel("CSCI 1301"),new Lebel("CSCI 1302"),
                new Lebel("CSCI 2410"),new Lebel("CSCI 3720")};
            for(Label course: courses){
                VBox.setMargin(course,new Insert(15,15,15,15));
                vbox.getChildren().add(course);
            }
            return vbox;
        }
    }
### 14.9 形状
> {文本，直线，圆，矩形，椭圆，弧，多边形和折线}

    Node <- Shape <- { Text,Line,Rectangle,Circle,Ellipse,Arc,Polygon,Polyline} 
> Shape 类是一个抽象基类，定义了所有的形状的共同属性。
- 具体有 
    - fill 指定一个填充形状的内部颜色
    - stroke 用于绘制形状轮廓的颜色
    - strokeWidth 指定形状轮廓的宽度

#### 14.10.1 Text
> Text 类定义一个结点，用于在一个起始点 (x,y) 处显示一个字符串，
> Text 类的对象通常置于一个面板中，面板左上角的坐标是(0,0),右下角的坐标是(pane.getWidth(),pane.getHeight())
> 一个字符串可以通过 \n 分割显示在多行。
>
    java.scene.text.Text
    -text: StringProperty//定义要显示的文本
    -x: DoubleProperty//定义文本的 x 坐标
    -y: DoubleProperty//定义文本的 y 坐标
    -underline: BooleanProperty//定义是否每行文本下面有下划线（默认：false）
    -strikethrough: BooleanProperty//定义是否每行文本中间有删除线（默认：false）
    -font:ObjectProperty<Font>// 定义文本的字体
    +Text()// 创建一个空的 Text
    +Text(text: String)//使用指定的文本创建一个 Text
    +Text(x: double,y: double,text: String)//使用指定的 x,y 坐标和文本创建一个 Text
>
    import javafx.appliction.Application;
    import javafx.geometry.Inserts;
    import javafx.scene.Scene;   
    import javafx.stage.Stage;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.Color;
    import javafx.scene.text.Text;
    import javafx.scene.text.Font;  
    import javafx.scene.text.FontWeight;   
    import javafx.scene.text.FontPosture;   
    
     public class ShowText extends Application{
        @Override
        public void start(Stage primaryStage){
            Pane pane = new Pane();
            pane.setPadding(new Insert(5,5,5,5));    
            Text text1 = new Text(20,20,"Coding is fun");
            text1.setFont(Font.font("Courier",FontWeight.BOLD,
            FontPosture.ITALIC，15));
            pane.getChildren().add(text1);  

            Text text2 = new Text(60,60,"Coding is fun\nDisplay text");  
            pane.getChildren().add(text2);  

            Text text3 = new Text(100,100,"Coding is fun\nDisplay text");  
            text3.setFill(Color.RED);
            text3.setUnderline(true);
            text3.setStrikethrough(true);
            pane.getChildren().add(text2);  
            Scene scene = new Scene (pane);
            primaryStage.setTitle (" ShowText");
            primaryStage.setScene(scene);
            primaryStage.show();
        }        
    }
#### 14.10.2 Line
> 一条直线通过4个参数(startX,startY,endX,endY)连接两个点。

    java.scene.shape.Line
    -startX: DoubleProperty//起点x坐标
    -startY: DoubleProperty//起点y坐标
    -endX: DoubleProperty//终点x坐标
    -endY: DoubleProperty//终点y坐标
    +Line()// 创建一个空的 Line
    +Line(startX: double,startY: double,endX: double,endY: double)
    // 创建一个指定起点终点的 Line
>
    import javafx.application.Application;    
    import javafx.scene.Scene;   
    import javafx.stage.Stage;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.Color;
    import javafx.scene.shape.Line;
        
     public class ShowLine extends Application{
        @Override
        public void start(Stage primaryStage){
            Pane pane = new Pane(new LinePane(),200,200);               
            primaryStage.setTitle (" ShowLine");
            primaryStage.setScene(scene);
            primaryStage.show();
        } 
        class LinePane extends Pane{
            public LinePane(){
                // 程序定义了一个名为 LinePane 的面板类，其中创建了两条交叉直线
                // 并将二者的起点和终点于面板的宽高绑定
                Line line1 = new Line(10,10,10,10);
                line1.endXProperty().bind(widthProperty().subtract(10));
                line1.endYProperty().bind(heightProperty().subtract(10));
                line1.setStrokeWidth(5);
                line1.setStroke(Color.GREED);
                getChildren().add(line1);

                Line line2 = new Line(10,10,10,10);
                line2.startXProperty().bind(widthProperty().subtract(10));
                line2.endYProperty().bind(heightProperty().subtract(10));
                line2.setStrokeWidth(5);
                line2.setStroke(Color.GREED);
                getChildren().add(line2);
            }
        }       
    }
#### 14.10.3 Rectangle
> 矩形通过参数 x y width height arcwidth archeight 定义
> x y 为矩形的左上角
> 参数 aw(arcwidth) 表示圆角处的水平直径
> 参数 ah(archeight) 表示圆角处的垂直直径

    java.scene.shape.Rectangle
    -x: DoubleProperty//x y 为矩形的左上角坐标
    -y: DoubleProperty
    -width: DoubleProperty
    -height: DoubleProperty
    -arcwidth: DoubleProperty//参数 aw(arcwidth) 表示圆角处的水平直径
    -archeight: DoubleProperty//参数 ah(archeight) 表示圆角处的垂直直径
    +Rectangle()// 创建一个空的 Rectangle
    +Rectangle(x: double,y: double,width : double,height : double)// 创建一个指定左上角点宽高的 Rectangle
>
    import javafx.application.Application;
    import javafx.scene.Group;  
    import javafx.scene.Scene;   
    import javafx.stage.Stage;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.paint.Color;
    import javafx.scene.text.Text;
    import javafx.scene.shape.Rectangle;  
    
     public class ShowRectangle extends Application{
        @Override
        public void start(Stage primaryStage){
            Rectangle r1 = new Rectangle(25,10,60,30);
            // 填充默认是黑色
            r1.setFill(Color.WHITE);
            // 画笔默认是白色
            r1.setStroke(Color.BLACK);
            Rectangle r2 = new Rectangle(25,50,60,30);
            Rectangle r3 = new Rectangle(25,90,60,30);
            r3.setArcWidth(15);
            r3.setArcHeight(25);
            // 创建一个 Group 用来容纳结点
            Group group = new Group();
            group.getChildren().addAll(new Text(10,27,"r1"),r1,
                new Text(10,67,"r2"),r2,new Text(10,107,"r3"),r3);
            for(int i = 0; i <= 4; i++){
                 Rectangle r = new Rectangle(100,50,100,30);
                 //循环创建一个矩形并将其旋转
                 r.setRotate(i * 360/8);
                 // 设置一种随机画笔颜色
                 r.setStroke(Color.color(Math.random(),Math.random(),Math.random()));
                 r.setFill(Color.WHITE);
                 group.getChildren().add(r);
            }
            // 将组中结点放大 2 倍
            group.setScaleX(2);
            group.setScaleY(2);
            Scene scene = new Scene (new BorderPane(group),250,150);
            primaryStage.setTitle (" ShowRectangle");
            primaryStage.setScene(scene);
            primaryStage.show();
        }        
    }
#### 14.10.4 Circle 和 Ellipse
> Circle 由 centerX centerY 和 radius 定义
> Ellipse 由 centerX centerY radiusX 和 radiusY 定义

    javafx.scene.shape.Circle
    -centerX: DoubleProperty// 圆心的 x 坐标（默认：0）
    -centerY: DoubleProperty// 圆心的 y 坐标（默认：0）
    -radius: DoubleProperty// 圆的半径（默认：0）
    +Circle()// 创建一个空的 Circle
    +Circle(x: double,y: double,)//使用指定的圆心创建一个 Circle
    +Circle(x: double,y: double,radius: double)////使用指定的圆心和半径创建一个 Circle
>
    javafx.scene.shape.Ellipse
    -centerX: DoubleProperty// 椭圆中心的 x 坐标（默认：0）
    -centerY: DoubleProperty// 椭圆中心的 y 坐标（默认：0）
    -radiusX: DoubleProperty// 椭圆的水平半径（默认：0）
    -radiusY: DoubleProperty// 椭圆的垂直半径（默认：0）
    +Ellipse()// 创建一个空的 Ellipse
    +Ellipse(x: double,y: double,)//使用指定的中心创建一个 Ellipse
    +Ellipse(x: double,y: double,radiusX: double,radiusY: double)////使用指定的中心和半径创建一个 Ellipse
>
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.stage.Stage;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.Color;
    import javafx.scene.text.Text;
    import javafx.scene.shape.Ellipse;

    public class form extends Application{
        //@ Override
        public void start(Stage primaryStage){
            Scene scene = new Scene(new MyEllipse(),300,200);
            primaryStage.setTitle (" ShowEllipse ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }

    }
    class MyEllipse extends Pane{
        //
        public void paint(){
            getChildren().clear();
            for(int i = 0;i <= 16; i++){
                Ellipse e1 = new Ellipse(getWidth()/2,getHeight()/2,
                        getWidth()/2-50,getHeight()/2-50);
                e1.setStroke(Color.WHITE);
                e1.setFill(Color.color(Math.random(),Math.random(),Math.random()));
                //r.setRotate(i * 180/16);
                getChildren().add(e1);
            }
        }
        //@Override
        //当面板改变的时候椭圆也改变
        public void setWidth(double width){
            super.setWidth(width);
            paint();
        }
        //@Override
        public void setHeight(double Height){
            super.setHeight(Height);
            paint();
        }
    }
#### 14.10.5 Arc
> 弧可以视为椭圆的一部分由 centerX centerY radiusX radiusY startAngle length 

> 和弧的类型( ArcType.OPEN ArcType.CHORD 或 ArcType.ROUND )定义

> startAngle 是起始角度，length 是跨度（即弧覆盖的角度）角度以度为单位 0度是正东方向

> 从正东方向开始逆时针旋转角度

    javafx.scene.shape.Arc
    -centerX: DoubleProperty// 椭圆中心的 x 坐标（默认：0）
    -centerY: DoubleProperty// 椭圆中心的 y 坐标（默认：0）
    -radiusX: DoubleProperty// 椭圆的水平半径（默认：0）
    -radiusY: DoubleProperty// 椭圆的垂直半径（默认：0）
    -startAngle: DoubleProperty// 弧的起始角度，以度为单位
    -length: DoubleProperty// 弧的角度范围，以度为单位
    -type: ObjectProperty<ArcType>//弧的闭合类型
    +Arc()// 创建一个空的 Arc
    +Arc(x: double,y: double,radiusX: double,// 使用指定的参数创建一个 Arc
        radiusY: double,startAngle:double,length:double )
#### 14.10.6 Polygon 和 Polyline
> Polygon 类定义一个连接一个点序列的多边形。

> Polyline 是不会自动闭合的 Polygon

    javafx.scene.shape.Polygon
    +Polygon()//创建一个空的 Polygon
    +Polygon(double ... points)//创建指定点的 Polygon
    +getPoints():ObservableList<Double>//返回一个列表作为点的(x,y)
## 15 事件驱动编程和动画
### 15.1 前言
        按钮     ————————>  事件   ————————> 处理器
    单击一个按钮          一个事件           事件处理器
    触发一个动作事件      是一个是对象        处理对象
    (事件源对象)           (事件对象)       (事件处理器对象)
- 成为动作事件处理器的条件
    - 该对象必须是 EventHandler<T extends Event>接口的一个示例。
        - 该接口定义了所有处理器的共同行为
        - < T extends Event>表示 T 是一个 Event 子类型的泛型
    - EventHandler 对象 Handler 必须使用方法 source.setOnAction(Handler)注册到事件源对象
>
    import javafx.appliction.Application;
    import javafx.geometry.Pos;
    import javafx.scene.Scene;
    import javafx.control.Button;
    import javafx.control.Lebel;
    import javafx.stage.Stage;
    import javafx.scene.layout.HBox;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    public class HandlerEvent extends Application{
        @Override 
        public void start (Stage primaryStage){
            Hbox pane = new HBox(10);
            pane.setAlignment(Pos.CENTER);
            Button btOk = new Button("OK");
            Button btCancel = new Button("Cancel");
            OKHandlerClass handler1 = new OKHandlerClass();
            btOK.setOnAction(handler1);
            CancelHandlerClass handler2 = new CancelHandlerClass();
            btCancel.setOnAction(handler2);
            pane.getChildren().addAll(btOK,btCancel);
            Scene scene = new Scene (pane);
            primaryStage.setTitle (" HandlerEvent ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
    }
    // 定义了两个处理器类。每个处理类实现了 EventHandler<ActionEvent>
    // 以处理 ActionEvent。对象  handler1 是一个  OKHandlerClass 的实例，
    // 该实例注册到按钮 btOK 上，当单击 OK 时，OKHandlerClass类的
    // handle(ActionEvent)方法被调用以处理事件。
    class OKHandlerClass implements EventHandler<ActionEvent>{
        @Override
        public void handle(ActionEvent e){
            System.out.println(" OK ");
        }
    }
    class CancelHandlerClass implements EventHandler<ActionEvent>{
        @Override
        public void handle(ActionEvent e){
            System.out.println(" Cancel ");
        }
    }
### 15.2 事件和事件源
> 事件是从一个事件源产生的对象。

> 触发一个事件意味着产生一个事件并委派处理器处理该事件。

    Java 的事件类的根类是 java.util.EventObject.
    JavaFX 的事件类的根类是 javaFX.event.Event
    其关系如下
    - EventObject 
        - Event
            - ActionEvent
            - WindowEvent
            - InputEvent ->{ MouseEvent,KeyEvent }
> 一个事件对象包含于该事件相关所有的属性。

> 可以通过 EventObject 中的 getSource() 实例方法来确定一个事件的源对象。
### 15.3 注册处理器和处理事件
> 处理器是一个对象，它必须注册到一个事件的源对象上，并且它必须是一个恰当的事件处理接口的实例。

> Java 采用一个基于委派的模型来进行事件处理：
    一个源对象触发一个事件，然后一个对该事件感兴趣的对象处理它。后者叫一个事件处理器或事件监听器
  
    import javafx.application.Application;
    import javafx.geometry.Pos;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.Border;
    import javafx.stage.Stage;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.StackPane;
    import javafx.scene.layout.BorderPane;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.paint.Color;
    import javafx.scene.shape.Circle;

    public class form extends Application{
        // 创建一个 CirclePane 的对象 
        private CirclePane circlepane = new CirclePane();
        @Override
        public void start (Stage primaryStage){
            HBox hBox = new HBox(10);
            hBox.setAlignment(Pos.CENTER);
            Button btEnlarge = new Button("Enlarge");
            Button btShrink = new Button("Shrink");
            hBox.getChildren().addAll(btEnlarge,btShrink);

            btEnlarge.setOnAction(new EnlargeHandler());
            btShrink.setOnAction(new ShrinkHandler());
            BorderPane borderPane = new BorderPane();
            borderPane.setCenter(circlepane);
            borderPane.setBottom(hBox);
            borderPane.setAlignment(hBox,Pos.CENTER);

            Scene scene = new Scene (borderPane,200,200);
            primaryStage.setTitle (" ControlCircle ");
            primaryStage.setScene(scene);
            primaryStage.show();
        }
        // 定义一个 EnlargeHandler 实现 EventHandler<ActionEvent>的处理器类
        class EnlargeHandler implements EventHandler<ActionEvent>{
            @Override
            public void handle(ActionEvent e){
                circlepane.enlarge();
            }
        }
        class ShrinkHandler implements EventHandler<ActionEvent>{
            @Override
            public void handle(ActionEvent e){
                circlepane.shrink();
            }
        }
        class CirclePane extends StackPane{
            // 定义一个新的类 CirclePane 用于显示面板中的圆
            private Circle circle = new Circle(50);
            public CirclePane(){
                getChildren().add(circle);
                circle.setStroke(Color.BLACK);
                circle.setFill(Color.WHITE);
            }
            // enlarge 方法用于增加圆的半径
            public void enlarge(){
                circle.setRadius(circle.getRadius()+2);
            }
            // shrink 方法用于增加圆的半径
            public void shrink(){
                circle.setRadius(circle.getRadius()>2?circle.getRadius()-2:circle.getRadius());
            }
        }
    }
### 15.4 内部类
> 又称嵌套类，是定义在另外一个类范围中的类。常常用于处理器。

    public class OuterClass{
        private int data;
        public void m(){}
        class InnerClass{
        // 1.内部类的一个用途是将互相依赖的类结合到一个主类中，可以减少源文件的数量，也使得类文件容易组织，
        // 因为它们都以主类名为前缀，内部类被编译成一个名为 OuterClass$InnerClass.Class 的类
        // 2.内部类可以引用定义在它所在的外部类中的数据和方法。
        // 所以不需要将外部类的引用转递给内部类的构造方法，使得程序更精简。
        // 3.内部类可以使用可见性修饰符所定义，和应用于一个类中的成员的可见性规则一样。
        // 4.内部类可以被定义为 static ,一个 static 的内部类可以使用外部类的名字访问，
        // 但一个 static 的内部类不能访问外部类中的非静态成员。
        // 5.内部类的对象常在外部类中创建。但也可以从另外一个类中来创建一个内部类的对象。
        // 若内部类使非静态的，则必须先创建一个外部类的实例，然后使用以下语句创建内部类
        //    OuterClass.InnerClass innerObject = outerObject.new InnerClass();
        // 若内部类是静态的，使用以下语句创建内部类
        //    OuterClass.InnerClass innerObject = new outerObject.InnerClass();
        // 6.处理器类被设计为针对一个 GUI 组件创建一个处理器对象。处理器类不被其他应用共享，所以将它
        // 定义在主类里面。
            data++;
            m();
        }
    }
### 15.5 匿名内部类处理器
> 匿名内部类是以一个没有名字的内部类。它将定义一个内部类以及创建一个内部类的实例结合在一步实现。

    public void start (Stage primaryStage){
        btEnlarge.setOnAction(
            new ~~EnlargeHandler()implement~~EventHandler<ActionEvent>()
                public void handle(ActionEvent e){
                circlepane.enlarge();
            });
        // 1.匿名内部类必须总是从一个父类继承或实现一个接口，但它不能有显式的 extends 或 implement子句。
        // 2.匿名内部类必须实现父类或接口中的所有抽象方法
        // 3.匿名内部类总是使用它父类的无参构造方法来创建一个实例。
        // 若一个匿名内部类实现一个接口，构造方法是 Object()
        // 4.匿名内部类被编译成一个名为 OuterClass$n.Class 的类,若有两个则为 OuterClass$1.Class和OuterClass$2.Class
    }
### 使用 lambda 表达式简化事件处理
> lambda 表达式可以为使用精简语法的匿名内部类。

     public void start (Stage primaryStage){
        btEnlarge.setOnAction(
            // e 的数据类型可以显示声明，也可以由编译器隐式推断。
            // 若只有一个参数，并且没有显示的数据类型，圆括号可以省略
            // 若只有一条语句，花括号可以省略
            (ActionEvent e)->{circlepane.enlarge();}
            // 或1. (e)->{circlepane.enlarge();}
            // 或2. e->{circlepane.enlarge();}
            // 或3. e->circlepane.enlarge()
            );
        // 编译器对待 lambda 表达式 如同它是从一个匿名内部类创建的对象。
        // 编译器采用三个步骤来处理 lambda 表达式
        // 1.确定 lambda 表达式类型
        //      如上编译器识别该对象是 EventHandler<ActionEvent> 的一个实例，
        //      因为表达式是 setOnAction 方法的参数。
        // 2.确定参数类型
        //      由于 EventHandler 接口定义了具有一个 ActionEvent 类型的参数的 handle 方法
        //      编译器识别出 e 为 ActionEvent 的数据类型
        // 3.确定语句
        //      编译器识别出处理 e 的代码是 handle 方法的方法体中的语句。
        // 注：EventHandler 接口中只有一个名为 handle 的方法，故可用lambda 表达式，若有多个方法则不可使用 lambda 表达式。
        // 实质上，lambda 表达式创建了一个对象，该对象通过调用这个单方法来执行函数。
    }
### 15.8 鼠标事件
### 15.9 键盘事件
### 15.10 可观察对象的监听器
> 可以通过添加一个监听器来处理一个可观察对象中的值的变化。

> Observable 类的实例可以认为是一个可观察对象，它包含了一个 addListener(InvalidationListener Listener)方法

> 用于添加监听器。监听器类必须实现函数接口 InvalidationListener 以重写 invalidated(Observable o)方法，从而

> 可以处理值的改变。一旦 Observable 中的值改变了，通过调用 invalidated(Observable o) 方法通知监听器。每个绑定

> 的属性都是 Observable 的实例。

    import javafx.beans.InvalidationListener;
    import javafx.beans.Observable;
    import javafx.beans.property.DoubleProperty;
    import javafx.beans.property.SimpleDoubleProperty;

    public class ObservablePropertyDemo{
        public static void main(String[] agrs){
            balance.addListener(new InvalidationListener(){
                public void invalidated(Observable ov){
                    System.out.println(balance.doubleValue());
                }
            });
            // balance.addListener(ov -> {
            //     System.out.println(balance.doubleValue());
            // });
            // 执行到此，它引发 balance 中的一个改变，通过调用监听器的 invalidated 方法来通知监听器这一变化。
            balance.set(4.5);
        }
    }
### 15.11 动画
> JavaFX 中的 Animation 类为所有的动画制作提供了核心功能。
> Animation 类有 PathTransition FadeTransition 和 Timeline 等子类

    javafx.animation.Animation 
    -autoReverse: BooleanProperty// 在交替的周期中动画是否需要倒转方向
    -cycleCount: IntegerProperty// 该动画的循环次数
    -rate: DoubleProperty// 该动画的速度和方向 rate 为负表示动画的相反方向
    -status: ReadOnlyObjectProperty<Animation.Status>// 只读属性，表面了动画的状态
    // Animation.Status.PAUSED Animation.Status.RUNNING Animation.Status.STOPPED
    +pause(): void// 暂停动画
    +play(): void// 从当前位置播放动画
    +stop(): void// 停止动画并重置
#### 15.11.1 PathTransition
> PathTransition类制作一个在给定时间内某个结点沿着一条路径从一个端点到另一个端点的移动动画。

    javafx.animation.PathTransition
    -duration: ObjectProperty<Duration>// 变换持续时间
    // 用常量 INDEFINTE ONE UNKNOWN ZERO 
    -node: ObjectProperty<Node>// 变换的目标结点
    -orientation: ObjectProperty<PathTransition.OrientationType>// 结点沿着路径的方向
    -path: ObjectType<Shape>// 一个作为结点移动路径的形状
    +PathTransition()// 创建一个空的PathTransition
    +PathTransition(duration: Duration,path: Shape)
    +PathTransition(duration: Duration,path: Shape,node: Node)

#### 15.11.2 FadeTransition
#### 15.11.3 Timeline
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
        