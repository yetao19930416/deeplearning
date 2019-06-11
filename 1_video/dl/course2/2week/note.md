mini-batch梯度下降法

x=[x(1) x（2）... x(m)]  训练样本
（nx,m）纬度
Y=[y(1) y（2）... y(m)]  样本结果
（1，m）
把整个训练样本集分成多个训练集（mini-batch）
相应也要拆分y
for t =1， ......5000
 Z[1]=W[1]X{t}+b[1]
 A[1]=g[1](Z[1])
 .....
 A[l] = g[l](Z[l])  设计为1000个样本
 cost j = 1/1000
 w[l]:=w[l]-adw[l], b[l]:=b[l]-adb[l]
 

随机梯度下降法缺点：失去向量带给你带加速

优化算法
指数加权平均数 vt=0.9$v_{t-1}$+(1-B)Ot
vt这几天平均温度=1/（1-B）
偏差修正可以使平均数计算更准确（在预算初期）
 vt=1-$B^t$
 v（correct）= vt/（1-$B^t$）

 momentum梯度下降法
 vdw = Bvdw +（1-B）dw
 vdb = Bvdb +（1-B）db
 W：= w -avdw
 b：= b -avdb

 RMSprop加速梯度下降
 sdw = B.sdw+（1-B）$dw^2$
 sdb = B.sdb+(1-B)$db^2$

 Adam优化算法
 vdw =0，sdw=0，vdb=0，sdb=0
 vdw=$B_1$vdw+(1-$B_1$)dw,
 vdb=$B_1$vdb+(1-$B_1$)db,
 sdw=$B_2$sdw+(1-$B_2$)$dw^2$,
 sdb=$B_2$sdb+(1-$B_2$)$db^2$,
 vdw = vdw/(1-$B_1^t$)
 vdb = vdb/(1-$B_1^t$)
 sdw = sdw/(1-$B_2^t$)
 sdb = sdb/(1-$B_2^t$)
 w:= w-a*vdw/($\sqrt{sdw}+\epsilon$)
 b:= b-a*vdb/($\sqrt{sdb}+\epsilon$)
 
  加速学习算法的一个方法就是减少学习率
