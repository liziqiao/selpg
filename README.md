# homework1 selpg


**selpg**的功能主要是通过命令行的方式将一些标准输入或者文件或者管道中的数据按照需要的页数输出到相应的文件或者标准输出或者管道中的程序，课程使用的是使用go语言来实现。

这里使用flag包来帮助我们解析命令行，可以减少很多的工作量，这样可以直接绑定参数到具体的变量中
``` go
flag.IntVar(&args.start, "s", -1, "Start page.")
flag.IntVar(&args.end, "e", -1, "End page.")
flag.IntVar(&args.page_len, "l", 72, "Lines per page.")
flag.BoolVar(&args.isf, "f", false, "Page type")
flag.StringVar(&args.output_dest, "d", "", "Output destination")
flag.Usage = Usage
flag.Parse()
```

接下来就是具体的对文件或者标准输入的读取以及输出，这里首先需要先确定最后是否存在一个非参数，也就是输入的文件的文件名，这里使用flag.Args(0)就可以得到，然后如果存在输入文件就打开输入文件流，否则就使用标准输入作为输入，接着还要确定是否有输出的文件夹，如果没有可以直接输出到屏幕。

-------------------
下面就展示一些测试结果：

首先使用a.txt作为输入进行测试
![pic](https://github.com/liziqiao/selpg/blob/master/pic/pic1.JPG)

使用a.txt再次进行测试
![pic](https://github.com/liziqiao/selpg/blob/master/pic/pic2.JPG)

使用标准输入进行测试
![pic](https://github.com/liziqiao/selpg/blob/master/pic/pic3.JPG)

总结：
通过这次实验可以发现go语言还是有很多非常好用的库的，特别是处理数据文件流的库有很多方便的操作，再加上go语言性能非常好，因此非常适合拿来做数据的处理。
-------------------
