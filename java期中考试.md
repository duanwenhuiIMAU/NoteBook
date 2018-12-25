# java期中考试
## 选择
## 二.判断 
    1.JAVA类的成员缺省权限不需使用修饰词，表示可在同一个包内访问(√)
    2.JAVA中的所有的数值类型变量都是有符号数(√)
    3.ArithmeticExpection是一种必检异常(×)
    4.在JAVA中创建子类对象时，父类对象也被自动创建(√)
    5.JAVA中的重载方法可用参数列表或返回值类型区别(×)
    6.对按钮ActionEvent事件采用set()Action方法(√)
    7.在JAVA中使用线程唯一方法是继承Thread类(×)-》使用Runnable接口
    8.JAVAFX场景类是Scene(√)
    9.在JAVA中允许将数值型变量当布尔类型使用(×)
    10.JAVA中的对象赋值，是将一个对象创建副本保存到另一个对象中(×)
    11.JAVA中的抽象类不可使用new操作符实例化，但依然可为其定义构造方法(√)
    12.在一个JAVA类中，变量初始化的顺序由定义的顺序决定(×)-> 引用的顺序
    13.文件按存储方式可分为文本文件和二进制文件(√)
    14.在JAVA语言定义数组，数组容量必须为常量(√)
## 三.填空
###
    ①
    1.public  classs IfTest{

    2.public static void main(String[] args)  {

    3.int x=3;

    4.int y=1;

    5.if(x=y)

    6.System.out.println("Not equal");

    7.else

    8.System.out.println("Equal");

    9.}

    10.}

    以上代码中，哪一行导致编译错误(5)=》if(x==y)
###
    ②
    请用数组的Length属性填空，完成二维数组的遍历

    public class Example{

    public static void main(String args){

    int matrix[][]=new  int[10][10];

    for(int i=0;i<matrix.length;i++)

    for(int j=0;j<matrix[i].length;j++)

    System.out.print(maxtrix[i][j]);

    }

    }
###
    ③
    请在空白处填写代码，完善异常处理

    class Test{

        public static void main(String args[]){

            try{

            int d=0;

            int a=42/d;

            }catch{

            System.out.println("division by zero");

            }

        }

    }
###
    ④
    请在空白处填写代码，完成Person对象双参构造

    class  Person{

        String name, departent;

        int age;

        public Person(String n){name=n;}

        public Person(String n,int a){name=n;age=a;}

        public Person(String n,String d,int a){

        this(n,a);

        department=d;

        }

    }
###
    ⑤
    请在空白处填写表达式，随即生成整数X（-15<=x<=15）

    public class Example{

        public static void main(String[] args){

        Random r=new Random();

        int x=r.nextInt()%16;

        }

    }
###
    ⑥
    请用标准输入完成Scanner对象构造

    public class Example{

        public static void main(String[] args){

        Scanner s=new Scanner(System.in);

        int i=s.nextInt();


        }

    }
###
    ⑦
    请将输入框中读入的数据转换为整型

    public class Example{

    public static void main(String args){

    String s=JOptionPane.show.InputDialog(null,"input a integer","Input Dialog",JOptionPane.QUESTION_MESSAGE);
    ***
    int i=Integer.parseInt(s);

    }

    }

    ⑧
    请为Max方法定义参数，完成程序运行

    public class Example{

    public static void main(String args){

    System.out.println(3,4);

    }

    public static int max(int num1,int num2){

    if(num1>num2)

    return num1;

    else

    return num2;

    }

    }

    ⑨
    请为形如"400-820-8820"的电话号码设计JAVA正则表达式，用于校验号码的有效性，其中每位号码为任意数字

    "\\d{3}-\\d{3}-\\d{4}"

    ⑩
    以下代码中，BufferedReader的什么方法可以从命令行读入一行数据，请填到空白处

    import java.io.*;

    class Test{

    public static void main(String[] args)  throws IOExpection{

    BufferedReader	stdin=new	BufferedReader(new	InputStreamReader(System.in));

    System.out.println(“Enter a Line:”)

    System.out.println( stdin.readLine());

    }

    }

    ⑩+①
    class A{

    public String toString(){return "4";}

    }

    class B extends A{

    public String toString(){return super.toString()+"3";}

    }

    public class Test{

    public static void main(String[] args){

    System.out.println(new B());

    }

    }

    以上代码运行的结果是(43)


    ⑩+②
    请将数组num中的最大元素[manindex]与第一个元素交换，最小元素[minindex]与最后一个元素交换，并用outArray方法输出数组

    public class Test{

    public static void main(String[] args){

    int num[]={23,56,1,8,10,2,34,5,7,67};

    int maxIndex=0;

    int minIndex=0;

    int temp=0;

    int i=0;

    for(int i=0;i<num.length;i++){

    if(num[i]>num[maxindex])

    maxindex=i;

    if(num[i]<num[minindex])

    minindex=i;

    }

    temp=num[0];

    num[0]=num[maxindex];

    num[maxindex]=temp;

    temp=num[num.length-1];

    num[num.length-1]=num[minindex];

    num[minindex]=temp;

    System.out.println(“变化后的数组:”);

    outArray(num);

    }

    private static void outArray(int[] num){

    for(int i=0;i<num.length;i++)

    System.out.print(num[i]+””);

    System.out.println();
    }

    }

    ⑩+③
    用JAVAFX在窗体上显示园，圆心(80,90),半径50，边线黑色

    public class  ShowCircle  extends Application {

    public void start(Stage primaryStage){

    Circle circle=new Circle();

    circle.setCenterX(80);//横坐标

    circle.setCenterY(90);//纵坐标

    circle.setRadius(50);//半径

    circle.setStack(Color.BLACK);

    Pane pane=new Pane();

    pane.getChildren().add(circle);

    Scene scene  new Scene(pane,200,200);

    primaryStage.setTitle(“ShowCircle”);

    primaryStage.setSence(sence);


    primaryStage.show();

    }

    public static void main(String[] args){

    launch(args);
    }

    }

    ⑩+④
    请用Point2D累计算p1(1,1) .p2(1,2)点之间的距离和中点

    import  javafx.geometry.Point2D;

    public class Test{

    public static void main(String[] args){

    Point2D p1=new Point2D(1,1);

    Point2D p2=new Point2D(1,2);

    System.out.println(p1.distance（p2）);//距离

    System.out.prinetln(p1.midPoint（p2）);//中点


    }

    ⑩+⑤
    用JAVAFX在窗体上显示图片“image.jpg”

    public class ShowImage extends Application{

    public void start(Stage primaryStage){

    Pane pane=new Pane();


    Image image=new Image(“image.jpg”);

    ImageView view=new ImageView(image);

    pane.getChilderen().add(view);

    Scene scene=new Scene(pane);

    ;

    primaryStage.setTitle(“ShowImage”);

    primaryStage.setSence(sence);


    primaryStage.show();

    }

    public static void main(String[] args){

    launch(args);
    }

    }


    ⑩+⑥
    请在空白处填写代码，输出键入的一行数据

    public class input {

        
        public static  void  main(String[] args) throws IOException{
            
            BufferedInputStream input=new 
    BufferedInputStream(System.in);
            
            int r;
            
            while((r=input.read())!=-1)
                
                System.out.println(r);
            
            
        }
    }

    ## 1
        /*
        注意：
        考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
        请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
        题目所需变量均已声明，请勿声明新变量。
        编写完成请在考生文件夹下编译调试。
        题目要求：接收命令行参数,形式如"3  +  2",输出两个数的和.
        */
        public class Test{
        public static void main(String[] args){
            int x,y; /*操作数*/
        /****************begin***************/
            if(args.length==3){
            x=Integer.parseInt(args[0]);
            y=Integer.parseInt(args[2]);
            System.out.println(x+y);
            }

        /****************end***************/		
        }
        }
    ## 2
        /*
        注意：
        考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
        请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
        编写完成请在考生文件夹下编译调试。
        题目要求：输入一个大写英文字母，输出相应的小写字母。例：输入G输出g，并输出g的ASCII码值。
        */
        import java.util.Scanner;
        public class Test{
        /****************begin***************/
            public static void main(String[] args)
            {
                Scanner input=new Scanner(System.in);
                String a=input.next();
                char c=a.charAt(0);
                char d=Character.toLowerCase(c);
                System.out.println(d);
                int x=(int)d;
                System.out.println(x);
            }

        /****************end***************/
        }
## 3
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：设计类Test1期中包含成员方法order(),接收1个整型数组，实现该数组的升序排列，空返回值，使得可以在Test类中调用该方法。
    请勿自行设计排序法。
    */
    import java.util.Arrays;
    public class Test{
    public static void main(String[] args){
        int[] a={9,5,1,4,7};
        Test1.order(a);
        for(int i=0;i<a.length;i++)
        System.out.println(a[i]);
    }
    }
    /****************begin***************/
    class Test1
    {
        public static void order(int []x)
        {
            Arrays.sort(x);	
        }
    }

    /****************end***************/
## 4	
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：设计类Test1期中包含成员方法max(),接收两个整型变量，返回较大值，使得可以在Test类中调用该方法。
    */

    public class Test{
    public static void main(String[] args){
        System.out.println(Test1.max(3,5));
    }
    }
    /****************begin***************/
    class Test1
    {
        public static int max(int x,int y)
        {
            int max;
            if(x>y)
                max=x;
            else
                max=y;
            return max;		
        }
    }
## 5
    /****************end***************/	
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    编写完成请在考生文件夹下编译调试。
    题目要求：用Scanner输入3个数，输出最大值。
    */
    import java.util.Scanner;
    public class Test{
    /****************begin***************/
    public static void main(String[] args)
    {
    Scanner input=new Scanner(System.in);
    int a=input.nextInt();
    int b=input.nextInt();
    int c=input.nextInt();
    int m,n;
    if(a>b)
    {
        m=a;
    }
    else
    {
        m=b;	
    }
    if(m>c)
    {
        n=m;
    }
    else
    {
        n=c;
    }
    System.out.println(n);
    }

    /****************end***************/
    }
## 6
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：请将形如"Kim Jones"的姓和名分别取出保存到字符串变量中,并输出.
    */
    public class Test{
    public static void main(String[] args){
        String s="Kim Jones"; /*姓名*/
        int k; /*用于记录字符串下标*/
    /****************begin***************/
    k=s.indexOf(' ');
    String firstName=s.substring(0,k);
    String lastName=s.substring(k+1);
    System.out.println(firstName+" "+lastName);

    /****************end***************/		
    }
    }

## 7
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    编写完成请在考生文件夹下编译调试。
    题目要求：请按照面向对象思想设计一个House类来描述房子，只有编号、面积两个属性，再使用接口技术实现房子对象的克隆。
    */
    public class Test{
        public static void main(String[] args) throws Exception{
            House h1=new House("1001",175);
            House h2=(House)h1.clone();
            System.out.println(h2.getArea());
        }
    }
    /****************begin***************/
    class House implements Cloneable{
        private String id;
        private double area;
        House(String id,double area){
            this.id = id;
            this.area = area;
        }

        public double getArea(){
            return area;
        }

        @Override
        public Object clone() throws CloneNotSupportedException {
            return super.clone();
        }
    }
    /****************end***************/
## 8
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：随机产生10个100以内的随机整数保存到a数组中，再用arraycopy()将a数组的内容复制到b数组，然后输出b数组的内容。
    */
    public class Test{
    public static void main(String[] args){
        int[] a=new int[10];
        int[] b=new int[10];
    /****************begin***************/
    for(int i=0;i<a.length;i++)
    {
        a[i]=(int)(Math.random()*100);
    }           //资源数组    复制位置   目标数组   复制位置  复制数量 
    System.arraycopy(   a,    0,        b,        0,       a.length);
    for(int i=0;i<b.length;i++)
    {
    System.out.print(b[i]+" ");
    }

    /****************end***************/
    }
    }
## 9     
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：设计成员方法sign()和main(),其中sign()接收一个整型变量，如果其值大于0返回1，等于0返回0，小于0返回-1，
    在main()方法中调用sign()方法。
    */

    public class Test{
        /****************begin***************/
    public static void main(String[] args)
    {
        System.out.println(sign(1));
    }
    public static int sign(int x)
    {
        if(x>0)
            return 1;
        else if(x==0)
            return 0;
        else
            return -1;
    }

        /****************end***************/	
    }
## 11
    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：请设计产生随机字符的方法，该方法形参为char ch1,char ch2，返回该范围内随机字符。
    */
    import java.util.Scanner;
    public class Test{
    public static void main(String[] args){
        System.out.println(getRandomChar('b','y'));		
    }
    /****************begin***************/
    public static char getRandomChar(char ch1,char ch2)
    {
        // ((int)ch2-(int)ch1)
        char a=(char)((int)ch1+Math.random()*((int)ch2-(int)ch1));
    return a;

    }

    /****************end***************/
    }
## 12

    /*
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：以矩阵的形式打印输出二维数组,并在每行的行尾输出该行的和.
    */
    import java.util.Arrays;
    public class Test{
    public static void main(String[] args){
        int[][] a={{1,2},{3,4},{5,6}};
        int i,j; /*循环变量*/
        int sum=0; /*行和变量*/
    /****************begin***************/
    for(i=0;i<a.length;i++)
    {
    sum=0;
        for(j=0;j<a[i].length;j++)
        {
            System.out.print(a[i][j]+" ");
            sum=sum+a[i][j];
        }
    System.out.println(sum);
    }

    /****************end***************/		
    }
    }
## 15
    注意：
    考生文件夹中存有Test.java的文件，该程序是不完整的，请在begin到end间填写代码实现要求的功能。
    请勿删除注释行或改动已有内容，保存时不得更改原有文件名。
    题目所需变量均已声明，请勿声明新变量。
    编写完成请在考生文件夹下编译调试。
    题目要求：用Scanner类读取键盘输入的一个字符，保存到char类型变量中，并输入。
    */
    import java.util.Scanner;
    public class Test{
    public static void main(String[] args){
    /****************begin***************/
    Scanner input=new Scanner(System.in);
    String s=input.next();
    char a=s.charAt(0);
    System.out.println(a);

    /****************end***************/		
    }
    }


##
##
##
##
##
## 1题目要求：以矩阵的形式打印输出二维数组,并在每行的行尾输出该行的和.
    import java.util.Arrays;
    public class Test{
    public static void main(String[] args){
            int[][] a={{1,2},{3,4},{5,6}};
            int i,j; /*循环变量*/
            int sum=0; /*行和变量*/
        /****************begin***************/
        for(i=0;row<a.length;i++){
            int sum_row=0;
            for(j=0; column<a[i].length;j++){
                System.out.print(a[i][j]+"  ");
                sum_row+=a[i][j];
            }
            System.out.print(sum_row); // out 为小写
            System.out.println();
        }
        /****************end***************/		
        }
        //用 sublime text 时要退出win + e
    }
## 2题目要求：接收命令行参数,形式如"3  +  2",输出两个数的和.

    public class Test{
    public static void main(String[] args){
        int x,y; /*操作数*/
    /****************begin***************/ 
        x=Integer.parseInt(args[0]);
        y=Integer.parseInt(args[2]);
        switch(args[1].charAt(0)){
            case'+':System.Out.println(x+y);break;
            case'-':System.Out.println(x-y);break;
            case'*':System.Out.println(x*y);break;
            case'/':System.Out.println(x/y);break;
        }
     /****************end***************/
    }
## 3题目要求：设计成员方法sign()和main(),

    其中sign()接收一个整型变量，如果其值大于0返回1，等于0返回0，小于0返回-1，
    在main()方法中调用sign()方法。

    public class Test{
        /****************begin***************/
        public static void main(String[] args){
            sign(1);
        }
        public static int sign(int a){
            if(a>0)return 1;
            else if (a==0)return 0;
            else return -1;
        }
        /****************end***************/	
    }
## 4题目要求：题目要求：用Scanner输入3个数，输出最大值。

    import java.util.Scanner;
    public class Test{
    /****************begin***************/
        Scanner input = new Scanner(System.in);
        int max = input.nextInt();
        int b = input.nextInt();
        if(max < b)max = b;
        int c = input.nextInt();
        if(max < c)max = c;
        System.out.println( max );
    /****************end***************/
    }
## 5用字符串输入一个小写字母输出它的大写字母和ASCII码
    import java.util.Scanner;

    public class test{
        //
        public static void main(String agrc[]){
            Scanner input = new Scanner(System.in);
            String str = input.nextLine();//用Scanner类读取键盘输入的一个字符
            char ch =str.charAt(0);//保存到char 类型变量中 
            System.out.println("upper char :"+ Character.toUpperCase(ch)+ "\n "+" ACSII of char : "+  ch+32);
            input.close();
        }
    }
## 6将形如 Kim Jones 的姓和名分别取出保存到字符串中
    public class Test{
    public static void main(String[] args){
        String s="Kim Jones"; 
        int k; 
    /****************begin***************/
        k=s.indexOf(" ");
        String xing = s.substring(0,k);
        String name = s.substring(k+1,s.length());
        System.out.println(xing + " " + name );
    /****************end***************/