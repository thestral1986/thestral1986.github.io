素数指的是因子只有1和本身的数（1不是素数），求解素数在数学上应用非常广泛，而求解n以内的素数也是我们编程时常遇到的问题，在这个问题上，筛选法求解素数运行得非常快。下面首先介绍如何判断一个是不是素数，然后介绍用普通方法求n以内的素数，接着是筛选法求n以内的素数，最后是两种算法的运行时间比较

判断一个数是不是素数

算法思想：判断小于等于一个数的平方的所有大于1的整数是不是能整除这个数，如果能，则表明这个数不是素数；反之，则是素数。

//判断一个数是否为素数 
bool isPlain(int value){
    int m = sqrt(value);
    if (value < 2) return false;
    for (int i = 2; i <= m; i++){
        if ((value%i)==0){
            return false;
        }
    }
    return true;
}
1
2
3
4
5
6
7
8
9
10
11
普通方法求解n以内的素数

算法思想：声明一个n大小的bool数组，初始值为false，然后从2开始判断一个数是否为素数，若是，则将其的布尔值定为true