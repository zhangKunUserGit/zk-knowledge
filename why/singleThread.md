为什么JavaScript是单线程的？
=====
其实这与它的用途有关。作为浏览器脚本语言，JavaScript的主要用途是与用户互动，以及操作DOM。
若以多线程的方式操作这些DOM，则可能出现操作的冲突。假设有两个线程同时操作一个DOM元素，
线程1要求浏览器删除DOM，而线程2却要求修改DOM样式，这时浏览器就无法决定采用哪个线程的操作。
当然，我们可以为浏览器引入“锁”的机制来解决这些冲突，但这会大大提高复杂性，
所以 JavaScript 从诞生开始就选择了单线程执行。
