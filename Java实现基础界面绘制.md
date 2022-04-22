Java实现基础界面绘制

包：  
对于一个完整的逻辑程序，可以将其package成为一个“包”  
在其他程序运行时，可以通过import关键字调用这个“包”   
可以使用这个包里里面的方法、类以及对象的属性等。  
如果使用了包，那么对于包中的类之前要有package申明  
  
对于oracle jdk环境下，Java自带了一个基础的包java.lang  
对于其他项目的开发，可以使用其他包  
关键字为   
import 包路径.类名  
比如  
import java.awt.Color  
  
Java现有的两个常用的教学使用的package:  
java.awt-早期的java界面开发包，常用其中元素规则类；然而其中的组件类、容器类较为老旧，一般不做使用  
javax.swing-是升级之后的界面开发包，一般使用其中的容器类组件类  
对于一个基础的界面开发,一般大致上分为：可视化、元素规则、内容。  

其中可视化包含：  
  -容器：窗体  
  -组件：按钮、输入框、文本框、标签等  

其中元素规则包含：   
 -尺寸、颜色、字体、布局  

其中内容包含：  
 -文本、图片  


开发一个界面的步骤：   
1.创建一个窗体对象 通过JFrame子包实现   
2.设置窗体对象的属性： 标题 尺寸 关闭选项 可视化 位置 不可改变尺寸 ..   
3.设置窗体的布局方式 通过FlowLayout流式布局器进行实现    
4.创建组件对象 JButton  JLabel  JPasswordField  JTextField  JCheckBox   
5.设置组件对象的 属性以及内容  文本  图片 尺寸 背景颜色   
6.添加组件对象到窗体对象中 根据流式布局器的规则 按顺序添加 左 上 为先   

1.创建初始化界面   
	public void initUI()   
{   
	窗体对象：从这一行开始出现窗体画面   
        JFrame jf  = new JFrame();   

2.创建窗体对象的属性   
        设置窗体标题    
        jf.setTitle ("登录界面");  
 
        设置窗体大小   
        jf.setSize (500,700);  

        设置窗体位置（NULL指居中）  
        jf.setLocationRelativeTo (null);  

        设置窗体的关闭操作 退出程序（EXIT_ON_CLOSE为指定关键字，可以通过数字代替）  
        jf.setDefaultCloseOperation (JFrame.EXIT_ON_CLOSE);  
        
	设置可视化  
	在代码最后需要再添加一次，因为现阶段没有内容的情况下代码读到这里会直接显示  
        jf.setVisible (true);   

 3.创建窗体布局方式  
	创建一个流式布局管理器  
        FlowLayout flow = new FlowLayout ();  
        窗体设置流式布局  
        jf.setLayout (flow);  

4.创建组件对象  

	标签  
	JLabel imgjla = new JLabel ();  
        JLabel namejla = new JLabel ();   
        JLabel pwdjla = new JLabel ();  

  文本框    
	JTextField namejtf = new JTextField ();  
        JPasswordField pwdjtf = new JPasswordField ();  

	复选框  
	JCheckBox remjcb = new JCheckBox ();  
        JCheckBox atloginjcb = new JCheckBox ();  

	按钮  
	JButton loginbtn = new JButton ();  
        JButton registbtn = new JButton ();  

	添加图片  
	ImageIcon img = new ImageIcon ("C:\\Users\\ZLYLF\\Desktop\\cat.jpg");  
        imgjla.setIcon (img);  
	
	标签内容  
        namejla.setText ("账号：");  
        pwdjla.setText ("密码：");   

	复选框内容  
	remjcb.setText ("记住密码");  
        atloginjcb.setText("自动登录");  

	按钮内容  
	loginbtn.setText ("登录");  
        registbtn.setText ("注册");  

	设置文本框大小  
	Dimension dim  = new Dimension (400,35);  
        namejtf.setPreferredSize (dim);  
        pwdjtf.setPreferredSize (dim);  

4.添加到窗体对象  
按照顺序依次添加即可   

	jf.add (imgjla);    // 添加图片  
        jf.add (namejla);   // 添加账号标签  
        jf.add (namejtf);   // 添加账号文本框  
        jf.add (pwdjla);    // 添加密码标签  
        jf.add (pwdjtf);    // 添加密码文本框  
        jf.add (remjcb);    // 添加记住密码复选框  
        jf.add (atloginjcb);// 添加自动登录复选框  
        jf.add (loginbtn);  // 添加登录按钮  
        jf.add (registbtn); // 添加注册按钮  

 jf.setVisible (true); 这里把可视化重复一遍即可实现不用二次刷新画面就可以直接显示界面内容  

 public static void main(String[] args){  
        LoginUI loginUI = new LoginUI();  
        loginUI.initUI();  
	}   
	最后添加一个主方法然后调用这个已经写好的方法  

添加完成之后，就完成了整个大致界面  
