1、spring-boot-maven-plugin在构建SpringBoot工程时，默认将resources目录下的资源文件(xml、properties)编译到target的classes目录下，
   而忽略Java目录下的xml文件，可以在父工程的pom文件里的build标签下添加如下配置来解决此问题
   ```
	<resources>
		<resource>
			<directory>src/main/java</directory>
			<includes>
				<include>**/*.xml</include>
			</includes>
			<filtering>false</filtering>
		</resource>
	</resources>
   ```
2、有时候在父工程下创建子模块时，子模块的resources文件夹不被idea识别为资源目录，即在此目录下建立的资源文件在build工程时不会被编译到target
   的classes目录下，可以通过如下方式解决：<br/>
   File　→　Project Settings　→　Modules　→　选中对应工程　→　右侧区域展开目录选中resources文件夹　→　点击上方Mark as: Resources　→　OK
