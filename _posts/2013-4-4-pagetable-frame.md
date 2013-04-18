---
layout: post
title: 标签页表与物理地址
category: code
---
最近在学习操作系统的内存机制，研究了一下标签列表与物理地址，有一点心得，在这里做点笔记。

我们都知道编译器和汇编器会把我们编写的程序翻译成机器语言，机器只要照着二进制的0和1执行就可以了。机器执行这些程序时是严格对应物理层的，机器语言里的内存地址就是物理上的内存地址。这就为我们带来了一个问题，今天我在我的机器上编译一个太阳神三国杀的程序，想拷贝给二子玩，但是我的操作是Win7，他的是XP，我们俩的无论如何，在运行的时候，太阳神三国杀在我们内存中的位置都不一定是一样的。那我已经编译好的可执行应用，又怎么能在他的机器上正确运行呢？

聪明的你肯定已经想到办法了，就是用相对的__逻辑地址__来表示。很明显，单应用操作系统没有这个问题，早期的Mac OS以及DOS都只需要程序在编译时链接物理地址。后来操作系统钟可以同时运行多个程序了，就有了__加载时链接__和__运行时链接__两种方式。加载时链接是在程序进程创建之后，将一个常量便宜添加到逻辑地址中得到真正的物理地址，这种方式现代个人电脑使用较少，不多赘述。使用更多也更灵活的是运行时链接。程序真正的物理地址直到进程调度时才予以分配。这种方式也有利于CPU中硬件极限缓存器的设计，当然这也不是今天的话题。

我嘚啵嘚啵嘚啵嘚说了这么半天，竟然完全没有提到标签页表，我真是服了我自己了。别着急，这就出现了。

系统里只要有不止一个程序在内存中，就涉及到内存管理的问题。只有一个程序的时候，可以让他随便用，只要别碰内核就行。程序一多，谁放在哪儿总有个说法。相互之间离的太近，一个程序需要分配更多动态空间就不够；相互之间离的太远，内存又有太大浪费。有的时候离的距离俩程序分配动态空间够用，但是第三个程序塞不进去。。总之想当然这么用不科学。

有人想个办法，把程序分为很多__页__，把内存分为很多__帧__，把一个程序打散，一页正好塞进一帧，多出来的帧不就可以有效利用别的程序了？我们来看看图理解一下。
![Alt](http://upload.wikimedia.org/wikipedia/commons/thumb/3/32/Virtual_address_space_and_physical_address_space_relationship.svg/300px-Virtual_address_space_and_physical_address_space_relationship.svg.png)
所以咱们编译时有一个__标签页表__就可以了。这表里存折哪一页对应了哪一帧。而操作系统呢，他知道自己的帧大小，知道了逻辑地址，知道了偏移量，再通过标签页表就可以算出物理地址啦！

写了一段小代码，大概就是操作系统中如何处理这件事儿的：
{% highlight c++ %}
  // Input logical addresses and calculate physical address
  while (getline(cin, line))
  {
    int logicalAddr = atoi(line.c_str());
    uint page = logicalAddr/size;
    // Test if logical address too big or too small
    if (page >= table.size())
      cout << "Logical address " << line <<
        ": illegal address" << endl;
    else
    {
      frame = table.at(page);
      // Test if the page is in frame
      if (frame == -1)
        cout << "Logical address " << line <<
          ": page fault" << endl;
      else
      {
        uint offset = logicalAddr%size;
        uint phsicalAddr = frame * size + offset;
        cout << "Logical address " << line <<
          " = physical address " << phsicalAddr << endl;
      }
    }
  }
{% endhighlight %}
这段代码因为不是直接应用在操作系统中，所以自己加了一段人工输入，现在贴上来删掉感觉有些虎头鼠尾，大家凑合着看看，请多指教！