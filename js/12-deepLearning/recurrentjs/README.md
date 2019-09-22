# RecurrentJS

## rnn01.js

關鍵：把步伐從 0.01 調到更小的 0.0002 ，然後加多代數 maxLoop 從 100 到 1000
如果 cost 跑到 0.000.... 的話就是對了 (大約有 50% 的機率正確！)

把 hiddenSizes 從 [4, 4] 調到 [10, 10] 之後，就幾乎每次都正確了！

```
$ node rnn01
...
probs={"0":0.9999999999999871,"1":1.294090696125599e-14} target=0
probs={"0":1,"1":2.6052204137676396e-25} target=0
probs={"0":0.9999920167124444,"1":0.000007983287555617702} target=0
probs={"0":0.00291291026340679,"1":0.9970870897365933} target=1
ppl = 1.0010903464457135 cost= 0.010897524497625943
probs={"0":0.9990832931114474,"1":0.000916706888552645} target=0
probs={"0":0.9992904888030705,"1":0.0007095111969294251} target=0
probs={"0":0.0019968905595077967,"1":0.9980031094404922} target=1
probs={"0":0.9999999999999898,"1":1.0168207653323533e-14} target=0
probs={"0":1,"1":1.841520771189419e-24} target=0
probs={"0":0.999741487978582,"1":0.0002585120214179733} target=0
probs={"0":0.0019968905595077967,"1":0.9980031094404922} target=1
probs={"0":0.9999999999999027,"1":9.727021465754803e-14} target=0
probs={"0":1,"1":1.218642614008918e-22} target=0
probs={"0":0.9984811737300123,"1":0.001518826269987542} target=0
probs={"0":0.0019968905595077967,"1":0.9980031094404922} target=1
ppl = 1.0009406498987572 cost= 0.009402077648816436
```

## lstm01.js

```
$ node lstm01
x=[{"n":1,"d":1,"w":{"0":0}},{"n":1,"d":1,"w":{"0":0}},{"n":1,"d":1,"w":{"0":0}},{"n":1,"d":1,"w":{"0":1}},{"n":1,"d":1,"w":{"0":0}},{"n":1,"d":1,"w":{"0":0}},{"n":1,"d":1,"w":{"0":0}}]
y=[{"n":2,"d":1,"w":{"0":1,"1":0}},{"n":2,"d":1,"w":{"0":1,"1":0}},{"n":2,"d":1,"w":{"0":0,"1":1}},{"n":2,"d":1,"w":{"0":1,"1":0}},{"n":2,"d":1,"w":{"0":1,"1":0}},{"n":2,"d":1,"w":{"0":1,"1":0}},{"n":2,"d":1,"w":{"0":0,"1":1}}]
probs={"0":0.5,"1":0.5} target=0
probs={"0":0.5,"1":0.5} target=0
probs={"0":0.5,"1":0.5} target=1
probs={"0":0.49945968194755386,"1":0.5005403180524461} target=0
...
ppl = 1.0000359774310883 cost= 0.00021586070349577496
probs={"0":0.9999801160528626,"1":0.00001988394713743294} target=0
probs={"0":0.9999610685480252,"1":0.00003893145197488935} target=0
probs={"0":0.0000586843063836189,"1":0.9999413156936163} target=1
probs={"0":0.9999774274156923,"1":0.00002257258430764508} target=0
probs={"0":0.999996708562783,"1":0.000003291437216866206} target=0
probs={"0":0.9999701877642357,"1":0.00002981223576425564} target=0
probs={"0":0.00002883380046168788,"1":0.9999711661995383} target=1
ppl = 1.0000336694936467 cost= 0.00020201356105164445

```