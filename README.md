#### kettle使用过程中问题
#### 下载地址：http://www.kettle.net.cn/
#### kettl中文api：http://www.kettle.net.cn/
#### 目录 
<a href="#question1"> 1.windows10下spoon.bat闪退问题</a><br/>
<a href="#question2"> 2.数据库连接共享设置</a><br/>
<a href="#question3"> 3.速度问题</a><br/>

##### <a id="question1"> windows10下spoon.bat闪退问题:</a>
###### 1.Java环境配置问题:  
###### java_home：安装jdk路径
###### classpath：.;%java_home%\lib\dt.jar;%java_home%\lib\tools.jar
###### path：在path路径中添加%java_home%\bin;%java_home%\jre\bin;
###### kettle_home：D:\Program Files\data-integration(安装kettle路径)

###### 2、Java版本太低了，jdk1.6以上版本才行，具体的可以查看spoon.bat配置文件。

###### 3、Java环境配置正确,调整内存spoon.bat里内存配置：

###### if "%PENTAHO_DI_JAVA_OPTIONS%"=="" set PENTAHO_DI_JAVA_OPTIONS="-Xms2058m" "-Xmx1024m" "-XX:MaxPermSize=256m"
###### 改为
###### if "%PENTAHO_DI_JAVA_OPTIONS%"=="" set PENTAHO_DI_JAVA_OPTIONS="-Xms512m" "-Xmx512m" "-XX:MaxPermSize=256m"  
###### 4.删除 “C:\Users\Administrator”下.kettle 缓存文件夹 
<br>

##### <a id="question2">数据库连接共享设置:</a>
###### 1.在一个转换文件中新建DB连接
###### 2.右键这个DB连接——>“共享数据库连接”。
###### 3.其他转换中点击下拉可以直接选择
###### 4.在每一个转换文件中，可右键删除DB连接

#####  <a id="question3">100w数据,使用kettle同步数据时,从开始的数据量7k(条)/s,运行越久,速度越慢:</a>
######  解决:修改数据库主键类型(建议设为自增)



