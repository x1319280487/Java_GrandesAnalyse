# Java_GrandesAnalyse
<font color="#4590a3" size = "4px">一、题目要求</font>

**实验类型：**综合性

**实验目的：**综合运用Java语言和面向对象技术开发一个小型软件系统

**实验内容：**

**已经提供的数据：**

<1> 班级学生名单：学生的学号和姓名已经分别存储在以学生所在班级命名的文本文件中，每行存储一个学生的学号和姓名，中间用一个空格分隔。例如：2010级网络工程1班.txt文件中存放该班学生名单。内容为：

	201030720102 陈纯
	201030720103 陈娟娟
	201030720104 陈伟健
	201030720105 陈伊纯
	……
<2> 开设课程保存在名为：course.txt的文本文件中，每行存放一门课程的名称，如：

	面向对象程序设计
	操作系统
	数据库系统
 
**实现以下功能，所有功能以图形用户界面完成。**

<1> 新建课程考试成绩单，功能描述如下：

	n  程序界面显示已经开设的课程（从course.txt中读取），用户选择本次输入的课程。
	n  程序界面通过文件对话框要求用户选择为哪个班输入成绩（即选择相应班的名单文件）。
	n  如果该班的成绩已经输入（已经存在对应成绩单文件），则提示无需输入。
	n  程序提供界面为该班的每个学生输入考试成绩。
	n  输入的成绩单以对象文件格式存储到文件中（不能是文本文件），文件命名为：班级-课程名.dat。
	例如：2010级网络工程1班-面向对象程序设计.dat。
<2> 打开课程考试成绩单，功能描述如下：
	
	n  程序通过文件对话框要求用户选择打开的成绩单文件。
	n  程序打开并读取成绩单文件内容，并显示在界面中。
<3> 修改课程考试成绩单，功能描述如下：

	n  完成第<2>功能后，即打开某班某课程的成绩单后。
	n  可以选择修改其中某个或某几个考试成绩，并保存。
<4> 课程考试成绩分析，功能描述如下：

	n  完成第<2>功能后，即打开某班某课程的成绩单后。
	n  点击成绩分析按钮或菜单，显示如下分析内容：
	u  最高分：XX分，最低分：XX分，平均分：XX分
	u  不及格（分数<60）：XX人，占XX.XX%
	u  及格（60<=分数<70）：XX人，占XX.XX%
	u  中等（70<=分数<80）：XX人，占XX.XX%
	u  良好（80<=分数<90）：XX人，占XX.XX%
	u  优秀（90<=分数<100）：XX人，占XX.XX%
<5> 成绩图形分析，功能描述：显示考试成绩分布的饼图和柱形图。

<font color="#4590a3" size = "4px">二、源码中类和函数的含义</font>

**类的含义：**

GradesAnalyse.java 提供程序入门，创建相关界面及其事件

User.java 实现对象的序列化，用于读取，写入，修改 .dat 对象文件

SampleAnalyse.java 显示对象的简单分析，对应要求<4>

PieChart.java 实现饼图

BarChart.java 实现柱状图

**函数的含义：**
 
 init( ) 置于构造函数中，在创建GradesAnalyse类的对象的时候进行初始化

createPanel( ) —— 创建主界面
createPanel_course( ) —— 创建课程选择界面
createPanel_class ( ) —— 创建班级选择界面
createPanel_save( ) —— 创建保存界面
createPanel_modify( ) —— 创建修改界面

Panel_event( ) —— 主界面事件
Panel_course_event( ) —— 课程选择界面的事件
Panel_class_event( ) —— 班级选择界面的事件
Panel_save_event( ) —— 保存界面的事件
Panel_modify_event( ) —— 修改界面的事件

getDirectoryFile(String path) —— 获取目录中文件的文件名

createStudentList( ) ——  根据班级学生名单 ( .txt ) 创建学生列表

createFile() —— 创建 .dat 文件
writeFile(File file) —— 写入 .dat 文件
readFile(File file) —— 读取 .dat 文件
modifyFile(File file) —— 修改 .dat 文件

readObject(File file) —— 读取序列化对象
writeObject(File file, LinkedList<User> msg) —— 写入序列化对象

analyse( ) —— 实现对象的简单分析

clean() —— 分析结束后对变量进行清零，防止重复计数。