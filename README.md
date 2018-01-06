# 百万英雄 自助截屏搜索工具

这是一个**不太好**的方案，仅供学习和参考。还是推荐用抓包和反编译安装包的方法获取相关的Rest-Api接口。

## 本地环境配置

Python3.5或更高（Python2.7请自测）

pytesseract模块

[tesseract-ocr识别引擎<sup>1</sup>](http://digi.bib.uni-mannheim.de/tesseract/tesseract-ocr-setup-4.00.00dev.exe)

[tesseract-ocr中文训练包<sup>2</sup>](https://raw.githubusercontent.com/tesseract-ocr/tessdata/4.00/chi_sim.traineddata)

### 下载必须文件

下载并安装ORC识别引擎<sup>1</sup>，下载中文训练包<sup>2</sup>并复制到 *C:\Program Files (x86)\Tesseract-OCR\tessdata*

### 配置环境变量

Windows用户请设置系统变量：

右键点击我的电脑-高级系统设置-系统属性-高级-环境变量；

用户变量 *Path* 添加 *C:\Program Files (x86)\Tesseract-OCR*

系统变量 *Path* 添加 *C:\Program Files (x86)\Tesseract-OCR*

系统变量添加 *TESSDATA_PREFIX* 设置为 *C:\Program Files (x86)\Tesseract-OCR* 

## 安装支持库

``` 
#下载并解压到 J 盘或者其他盘
#开始-运行-输入CMD回车，每输入一行回车一次
J:
cd millionhero
pip install -r requirements.txt
```

安装失败请尝试
`easy_install Pillow`
`easy_install pytesseract`

## 修改hero.py

如果整张图片进行OCR，会耗费双倍的时间，脚本也是能够正常执行和返回结果的，只是太浪费时间，所以需要根据手机分辨率修改问题尺寸。

box参数设置：手机截一张答题时候的截图，电脑上1比1打开手机截图，用QQ截图分别查看 (黄，红，蓝，绿) 像素长度。


![sc2](https://raw.githubusercontent.com/se4/millionhero/master/screenshot/screenshot2.png)



## 运行脚本

``` 
#安卓手机插电脑，打开 usb调试模式
#开始-运行-输入CMD回车，切换到含有hero.py文件夹目录
J:
cd millionhero
python hero.py
```