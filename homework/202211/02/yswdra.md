### TCP 是否可以改为两次握手？（请从 ISN 的角度思考）

------

首先，TCP 是全双工通信，而且 TCP 是通过 序列号来实现可靠传输的，因此一个连接首先要 同步双方起始序列号(ISN)，才可以保证通信双方的数据准确性；而 ISN 的生成规则告诉我们只有生成 ISN 的一方才可以确认这个 ISN 是不是正确的，因此，需要三次握手来保证通信双方 ISN 的同步，如果只有两次握手，只能保证 发起方的 ISN 被确认，也就只能保证发起方向服务方的单向通信的数据可靠性。