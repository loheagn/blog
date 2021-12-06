---
title: JavaScript中的__proto__和prototype
authors: loheagn
---

1. `__proto__`是所有对象都有的属性（function也有）。它的含义是，当前这个对象是根据哪个“模板”创造出来的。

2. `prototype`是构造函数才有的属性（因为所有的function都可以作为构造函数使用，所以这个属性也是所有函数都有的属性）。它的含义是，当前这个function，在被当做构造函数使用时（也就是在被用来创造对象时），该使用哪个“模板”来创造对象。

于是，我们就有了所谓的`.__proto__ == constructor.prototype`（不一定在所有情况都适用）之类的说法。
