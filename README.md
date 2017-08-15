# Mybatis-Generator
[![][build img]][build]  ![][version img]  [![][license img]][license]  

这是一个自带配置详解的Mybatis Generator模板

# Repository Structure

```
Mybatis-Generator
│  generatorConfigExample.xml  #这是一个栗子
│  generatorConfigTemplate.xml #这个是模板
│  LICENSE
│  mybatis-generator-core-1.3.5.jar
│  mysql-connector-java-5.1.40-bin.jar
│  README.md
│  run.bat #点击这个运行
│  
└─src
```

# Usage

## Step 1
下载或clone这个项目：git@github.com:kuri-leo/Mybatis-Generator.git

## Step 2
复制一份`generatorConfigTemplate.xml`并重命名为`generatorConfig.xml`

## Step 3
修改`generatorConfig.xml`文件：  
1. Line 15: `<jdbcConnection driverClass="YOUR_DATABASE_DRIVER" connectionURL="YOUR_JDBC_ADDRESS" userId="YOUR_USERNAME" password="YOUR_PASSWORD"></jdbcConnection>`  
    - 将`YOUR_DATABASE_DRIVER`改为你的数据库驱动，例如`com.mysql.jdbc.Driver`;  
    - 将`YOUR_JDBC_ADDRESS`改为你的数据库地址，例如`jdbc:mysql://localhost/test?useSSL=true`;  
    - 将`YOUR_USERNAME`改为你的数据库用户名，例如`root`;  
    - 将`YOUR_PASSWORD`改为你的数据库地址，例如`123`.  <!-- 别吐槽这个密码了 -->

2. Line 21:`<javaModelGenerator targetPackage="YOUR_MODEL_PATH" targetProject="src">`
    - 将`YOUR_MODEL_PATH`改成你的Model层路径，例如`com.test.Model.PO`;  

3. Line 34:`<sqlMapGenerator targetPackage="YOUR_MAPPER_FILE_PATH" targetProject="src">`
    - 将`YOUR_MAPPER_FILE_PATH`改成mapping路径，例如`com.test.Model.Dao.Mapping`;  

4. Line 42:`<javaClientGenerator type="XMLMAPPER" targetPackage="YOUR_INTERFACE_PATH" targetProject="src">`
    - 将`YOUR_INTERFACE_PATH`改成你的接口路径，例如`com.test.Model.Dao.Interface`;  

5. Line 52:`<table tableName="YOUR_TABLE_NAME_HERE">`
    - 将`YOUR_TABLE_NAME_HERE`改成你要逆向生成的表的名字，例如`test`;  

## step 4
双击`run.bat`或者控制台运行`java -jar mybatis-generator-core-1.3.5.jar -configfile generatorConfig.xml -overwrite`

## step 5
检查文件夹下的`src`目录看是否生成成功
以``为例，正确运行后的目录结构应当如下

```
Mybatis-Generator
│  generatorConfigExample.xml
│  generatorConfigTemplate.xml
│  LICENSE
│  mybatis-generator-core-1.3.5.jar
│  mysql-connector-java-5.1.40-bin.jar
│  README.md
│  run.bat
│  
└─src
    └─com
        └─test
            └─Model
                ├─Dao
                │  ├─Interface
                │  │      TestMapper.java #生成的
                │  │      
                │  └─Mapping
                │          TestMapper.xml #生成的
                │          
                └─VO
                        Test.java #生成的
                        TestExample.java #生成的
```

~~如果少了啥那肯定是你配置错啦~~

## ~~Step 6~~
~~如果觉得有用麻烦点一下star，谢谢!~~

# License
[WFTDPL](http://www.wtfpl.net/about/)

[license]:LICENSE
[license img]:https://img.shields.io/badge/license-WTFPL-blue.svg

[build]:https://github.com/kuri-leo/Mybatis-Generator
[build img]:https://img.shields.io/badge/build-passing-brightgreen.svg

[version img]:https://img.shields.io/badge/verison-1.0-brightgreen.svg