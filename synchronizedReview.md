# synchronized字段原理
> + 每个对象都有一个监视器锁，如果被占用则会进入锁定状态
> + 如果监视器锁被其他线程占用，则其他线程获取不到锁，直到monitor为0，则重新尝试获取锁

# 同步的对象
> + 同步普通方法:若两个线程使用同一个对象调用的方法，则无法并发执行，需要竞争同一个对象上的锁
> + 同步静态方法:若两个线程使用不同的对象去调用同步方法，因为是静态方法无法并发执行，本质上是对类(class)的加锁，
> + 同步对象(this):若两个线程使用不同对象去调用同步方法，并发执行 锁的是对象

# 同步方法,对象原理
> + 同步方法: 在常量池中新增一个ACC_sync标示符，jvm会检查标识符有没有别设置，如果设置了，线程去尝试获取monitor，隐式处理
> + 同步对象 ，通过在字节码中加入monitor来实现 显示处理