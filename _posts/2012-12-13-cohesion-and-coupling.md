---
layout: post
title: High Cohesion, Low Coupling
category: code
---
It is a shame that as a junior student in computer science, this is my first time hearing the software engineering concept "High Cohesion, Low Coupling". I am pretty sure that I have heard this somewhere. But the first time I heard this in Chinese, that was a big surprise.

On the Chinese online forum *CSDN*, I asked something about MVC model a couple days ago and nobody seemed to be interested. I went back there yesterday, two people in the post were talking some cohesion and coupling stuff. If they were using English, I would know what they were talking about. But these two words in Chinese are just weird! Cohesion, this sounds like some chemistry thing, organic chemistry I promise. Coupling is something even more strange for me which I used to think it is a electrical engineer thing. So I didn't think much and left the post there. After the college physics final today, I was sitting here reading [酷客](http://coolshell.cn), my favorite programming blog these days. The editor Mr. Chen has just post a new article called *How to understand object oriented programming*. After reading the whole critique of misusing object oriented programming, I read the worlds cohesion and coupling in Chinese at the end again. What an awkward moment! Everyone in IT industry were talking about things that I have never heard about! So I googled them and found what those are in English, which I have of course heard in my CS classes.

学习一下其实这俩词儿意思都很简单，高内聚说的是一个模块干一个事儿，低耦合是说增加模块的独立性。这两点导师无论是Java还是C++编程都一再和我强调（我导师挺固执的，不说这些设计模式要严格遵守，就连 **{** 在定义行末还是第二行起始都得按照他意思来）。听起来意思简单，理解起来还是有点困难的。一是为什么？二是怎么做？在学习Java的时候除了英文的教科书，我还曾使用过国内某一流大学使用的Java教材，该教材只能说把Java语言的格式交给了学生，但其中面向对象概念接近没有，所有例程无论多大多长全部使用一个.java文件完成，所有方法都直接扔在主类中。这直接造成了我很长时间对面向对象的困惑，有那么个几个月我都觉得整个源码就一个文件多好啊，看起来也方便。现在想想要是喜欢一个文件的源码，还不如不用面向对象呢，很多事儿反而方便些。至于怎么做，这真的就不是我能写写说说的了，我确实没有深入学习软件工程，自己的代码积累也不足够对此评述。

Actually I am not trying talking about software engineering at all. I am talking about life.

今天我坐在这里想“高内聚，低耦合”到底有什么优点，我突然就想到人生是不是也该这样呢？现在的社会和18世纪已经不同了，信息大爆炸，博学家出现的几率较小了。我们更应该做的是专注做好一件事，在一个领域做精，而不是什么都会点儿，什么弄得都不好。“高内聚”说的正是专注做人的道理，“低耦合”告诉了我们如果对另外的方面感兴趣，可以在进行完一件事以后再进行另一件，减少不同任务相互之间的影响。从软件工程上说，高内聚低耦合的设计模式在短期内看不见较大回报，反而增加了设计难度；但从长远来看，重用性、扩展性大大提高，利于持续发展。生活中更是这样，今天对骑马感兴趣，学学骑马，明天对射箭感兴趣了，强忍着不去射箭，非要把骑马练好再去不可。短期上看，当时情绪被抑制的自己当然是不高兴；但从长远上说呢？如果一天骑马一天射箭，最后可能一事无成，练好骑马再去射箭，哪怕最后因为抑制自己导致了不再想射箭了，至少练好了骑马吧？要是都能练好了，以后至少拿得出手了吧？骑射也能练了吧？

In fact in our daily life we also need reusability, augmentability, and of course sustainability.