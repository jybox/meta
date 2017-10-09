---
title: 读代码是好的学习方式么
permalink: reading-code
date: 2015-02-24
reviews:
  -
    author: 马隆博
    body: 不完全赞同。我则认为读代码和读书都是好的学习方式，只是适用阶段不同。不建议初学者或者初接触一门语言时就读别人代码。在自己入了门，有了一点实践，需要进阶时，可以多读优秀开源项目的源代码，吸取优秀的部分。
---

自我开始编程以来，我一直觉得读别人的代码的难度，要几倍于自己写代码。一直以来我都很困惑，难道是我技艺不精，所以读别人的代码很困难么。

其实不是，我能看懂代码中的每一句话，并没有我不认识的语法，但连在一起就不懂为什么作者要这么安排代码了。

后来我渐渐有了一些想法，代码是程序员给计算机的命令，是作者思考过后的产物，但思考的过程却没有体现在代码上，这就好比一道数学题，只有一个最终答案，所有的计算过程都被省略掉了，自然难以理解作者的意图。一段代码一开始写出来，后来发现存在问题，陆陆续续地改过好几版是很常见的事情。最终版本中可能每个小的细节，都是作者花了很多时间试错的结果，但这个试错的过程并没有直接地体现在代码上。

另一方面，代码中往往存在一些「隐含前提」，例如假定函数的参数已经在传入之前被以某种方式处理过了，这个假定很可能与另一个文件的某行代码有关，这种联系很难引起阅读者的注意。当然，好的设计可以缓解这个问题，但很难被彻底地解决。

代码的历史会被保存在版本控制系统里，但说实话，按我的经验，很少真的有人去翻版本历史，因为正确地使用版本控制工具相比起写代码是一项比较不受重视的技能，在这种情况下翻历史是非常耗时的。当然，有些人会将一些细节以注释的形式添加到代码中，但注释也只能承载很小的一部分信息，因为维护注释也是一项很高的成本，我个人一向是反对添加注释来解释代码的。

所以阅读代码实际上并没有看上去那么轻松，为了彻底理解一段代码，很有可能你需要付出和编写这段代码差不多的努力，来了解这段代码的历史和前提。

前面提到的是阅读「好的代码」的情况，比如大多数活跃的开源项目，如果是面对质量较差的代码情况就更为糟糕了。

所以我的观点是，读代码绝对不是一种好的学习方式，我认为学习一项技术应当先阅读书籍，然后尝试自己实践，最后再参考代码质量较高开源项目。

对于大多数项目而言，可能从未把「供他人学习」当作目标，只有当你自己实践过，积累了一些经验并且也遇到过一些困难的时候，你才能读懂代码并且从中学到解决问题的技巧。而在开始实践之前，最好的知识来源是书籍，因为书籍的内容是经过精心的安排的，最高目标就是供他人阅读。