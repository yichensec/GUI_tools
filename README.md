<h1 align="center" >GUI-tools</h1>

<h3 align="center" >适用于用户DIV的启动盒子</h3>

## 🏝 0x01 介绍

作者：yichensec

定位：开源，高自由，可DIV的整理工具，使用简单，方便

语言：python3开发

功能：适用于整理文件夹，及个人工具

当前版本：GUI_tools v0.1

## 🎸0x02 安装使用

1、所需库安装

```python
pip3 install -r requirements.txt
```

2、使用

```python
开启：python tools.py
一键启动：GUI启动.VBS
```

3、说明

```python
文件:config.py 			 配置文件。
文件：tools.py 			主配置文件
文件：run.bat  			带cmd框的启动方式
文件：GUI启动.vbs 		   一键启动方式，无cmd框
文件：logo.ico 		    图标可替换
文件：requirements.txt		需下载python第三方库
文件：README.md			工具说明
文件夹：tools			   文件夹，可内置个人文件，并设置路径
文件夹：imgs				   存储工具说明图片文件夹

另外说明：启动后会自动生产__pycache__文件，可删除
```



## 💡0x03 效果展示

配置效果图：

<img src="imgs\1.jpg" alt="效果图" style="zoom:80%;" />



📖0x04 配置文件
---

### （1）tools主文件

```python
#导入ttk模块和同目录下的config配置文件
import ttkbootstrap as ttk
from ttkbootstrap.constants import *
from config import config

#设置实例化类对象
config = config()  

# 设置整体界面按钮宽度大小为25
button_width = 25   

#变量引入主题 多种主题可供切换
themes = 'superhero'      

#可切换主题 ['superhero','purse','yeti','lumen','journal','darkly','solar','morph','vapor' ]                      
#框架主体      
UI = ttk.Window(
                title="逸尘文库",                #设置标题
                themename=themes,               #调用主题名称
                size=(1450, 200),               #设置窗口(宽度，高度）
                resizable=(FALSE, FALSE),       #设置调整窗口是否可以拉伸
                alpha=0.95,                     #设置窗口透明度
                )
#设置ico图标
UI.iconbitmap('logo.ico')   

#框架引用UI变量设置框架大小，标题，主题等等。            
UI.place_window_center() 

#设置分框
Y = ttk.Frame(UI)       
Y.pack(pady=20, fill=X, side=TOP)

#分页
pk = ttk.Notebook(Y)
pk.pack(side=LEFT,padx=(10, 10),expand=YES,fill=X )


####################################################################################################### 
#第一部分
#我的资源
#设定变量:WD 

#设置ttk框架导入pk变量设置，赋值于变量WD
WD = ttk.Frame(pk) 

#第一行设置
#ttk.Button		设置，需变动如下
#text 			名称
#command 		按钮关联的函数，当按钮被点击时，执行该函数
#grid    		网格设置，row是横向排列，column是纵向排列

ttk.Button(WD,text="安全", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD1_click).grid(row=1,column=1,padx=20,pady=10)

ttk.Button(WD,text="工作文档", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD2_click).grid(row=1,column=2,padx=20,pady=10)
            
ttk.Button(WD,text="技术文章", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD3_click).grid(row=1,column=3,padx=20,pady=10)
            
ttk.Button(WD,text="开发", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD4_click).grid(row=1,column=4,padx=20,pady=10)
            
ttk.Button(WD,text="临时文件", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD5_click).grid(row=1,column=5,padx=20,pady=10)
            
ttk.Button(WD,text="文章", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD6_click).grid(row=1,column=6,padx=20,pady=10)
#第二行
ttk.Button(WD,text="学习方向", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD7_click).grid(row=2,column=1,padx=20,pady=10)

ttk.Button(WD,text="运维", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD8_click).grid(row=2,column=2,padx=20,pady=10)
            
ttk.Button(WD,text="杂项", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD9_click).grid(row=2,column=3,padx=20,pady=10)
            
ttk.Button(WD,text="重要资源", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.WD10_click).grid(row=2,column=4,padx=20,pady=10)

pk.add(WD, text='   我的资源    ')

#######################################################################################################
#第二部分
#安全
#设定变量：AQ 

#第一行
AQ = ttk.Frame(pk) 

ttk.Button(AQ,text="WEB渗透", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ1_click).grid(row=1,column=1,padx=20,pady=10)

ttk.Button(AQ,text="修复", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ2_click).grid(row=1,column=2,padx=20,pady=10)
            
ttk.Button(AQ,text="内网渗透", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ3_click).grid(row=1,column=3,padx=20,pady=10)
            
ttk.Button(AQ,text="工具使用", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ4_click).grid(row=1,column=4,padx=20,pady=10)
            
ttk.Button(AQ,text="渗透报告", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ5_click).grid(row=1,column=5,padx=20,pady=10)
            
ttk.Button(AQ,text="漏洞复现", bootstyle=(PRIMARY, "success-outline-toolbutton"),
            width=button_width, command=config.AQ6_click).grid(row=1,column=6,padx=20,pady=10)

###############################################   结尾   ##############################################
pk.add(AQ, text='   安全    ')
UI.mainloop()
```

### （2）config配置文件

```python
#导入subprocess模块
import subprocess

class config():
########################################################################################################
#我的资源
#设定变量：WD 

    def WD1_click(self):
        subprocess.Popen("start tools\安全 ", shell=True)

    def WD2_click(self):
        subprocess.Popen("start tools\工作文档 ", shell=True)
        
    def WD3_click(self):
        subprocess.Popen("start tools\技术文章 ", shell=True)
        
    def WD4_click(self):
        subprocess.Popen("start tools\开发 ", shell=True)
        
    def WD5_click(self):
        subprocess.Popen("start tools\临时文件 ", shell=True)
        
    def WD6_click(self):
        subprocess.Popen("start tools\文章 ", shell=True)

    def WD7_click(self):
        subprocess.Popen("start tools\学习方向 ", shell=True)

    def WD8_click(self):
        subprocess.Popen("start tools\运维 ", shell=True)
        
    def WD9_click(self):
        subprocess.Popen("start tools\杂项 ", shell=True)
        
    def WD10_click(self):
        subprocess.Popen("start tools\重要资源 ", shell=True)

#######################################################################################################
#安全
#设定变量：AQ

    def AQ1_click(self):
        subprocess.Popen("start tools\安全\WEB渗透 ", shell=True)

    def AQ2_click(self):
        subprocess.Popen("start tools\安全\修复 ", shell=True)
        
    def AQ3_click(self):
        subprocess.Popen("start tools\安全\内网渗透 ", shell=True)
        
    def AQ4_click(self):
        subprocess.Popen("start tools\安全\工具使用 ", shell=True)
        
    def AQ5_click(self):
        subprocess.Popen("start tools\安全\渗透报告", shell=True)
        
    def AQ6_click(self):
        subprocess.Popen("start tools\安全\漏洞复现 ", shell=True)

```

💻 0x05 版本更新预告
---

### 更新功能

```
1.加入文件搜索功能
2.加入笔记存储功能
3.加入主题自定义功能
```

### 建议

有想法可联系作者vx：WlZkc2FtRkhWblZqTWxacQ==

注：base多重编码
