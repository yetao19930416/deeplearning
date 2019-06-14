第二部分第三周
超参数的调试中a（学习速率）调试最为重要

调试两种方法（随机取值，精准搜索）

r = -4*np.random.road()<- r属于[-4,0]

a= $10^r$   a<-属于 $10^{-4}$......$10^n$

给B取值，指数加权平均值

0.9........0.99999

1-B = 0.1........0.001

 r属于[-3,-1]

 1-B =$10^r$

 B = 1-$10^r$

超参数搜素过程
batch归一化
$z^{（1）}$........$z^{（m）}$

u=1/m$\sum_{i}^{n}Z^i$ 
    ...
    ...
  公式下次再补
（方差）

流程首先是$z^{[1]}$,$a^{[1]}$,先由参数$w^{[1]}$，$b^{[1]}$

来获取$z^{[1]}$，本身$z^{[1]}$通过激活函数来变成$a^{[1]}$，但

是有来Batch后通过$B^{[1]}$，$L^{[1]}$两个超参数进行归一化，参

数获取$z^{[1]}$，然后再进行激活，batch归一化通常和mini-btach一

起用也可以和其他算法Adam等等一起用

btach归一化可以使你的权重比你的网络更滞后

均值为0，方差为1（不懂）

有轻微的正则化效果给隐藏单元加了噪音，不让过分依赖隐藏单元，可以和dropout一起用

batch归一化一次只能处理一个mini-batch在计算均值方差的时

单独计算u，$o^{2}$需要指数加权平均

soft回归
激活$Z^{[L]}$ =$W^{L}$ $a^{[L-1]}$+$b^{[L]}$
softmax函数 t = $t^{Z[L]}$   (4,1)纬度
这里没听懂


TensorFlow（框架基本运用）
w =tf.variable(0,dtype = tf.float32)
coefficients = np.array([[1],[-20],[25]])
w = tf.variable([0],dtype = tf.float32)
x = tf.placeholder(tf.float32,[3,1])
cost = x[0][0]*W**2 + x[1][0]*w + x[2][0]
train = tf.train.GradientDescentoptimizer(0.01).minimize(cost)

init = tf.global-variables(这个公式写的有点问题)

session = tf.session()

session.run(init)

print(session.run(w))

for i in range(1000):
     session.run(train,feed_dict = {x:coefficients})
print(session.run(w))

具体函数代表的内容后续再补