Consider a 3 * 3 Network-on-Chip (NoC) as shown in the following picture.

    1-1 -- 1-2 -- 1-3
     |      |      |
    2-1 -- 2-2 -- 2-3
     |      |      |
    3-1 -- 3-2 -- 3-3

In a given NoC, each node is a CPU that can send a message to any other CPU using XY routing algorithm. For example, for the case of sending a message from the upper-left CPU (1-1) to the lower-right CPU (3-3), at the first step, the message travels in x dimension and goes to the upper-right CPU (1-3), then it goes down in y dimension to arrives to its destination.

To have a successful sending a message from a CPU to one of its neigh- boring CPUs, the neighboring CPU has to be empty . In this case, the neighboring CPU accept the message. In the case of not being empty, the neighboring CPU do nothing and the sender CPU sends the same request one second later. It takes one second for a message to goes from one CPU to one of its neighboring CPUs. Moreover, when a CPU receives a message, it sends an ack message to its sender CPU to make clear that it received the message. So, if the sender doesn’t receive this ack message it will resend that message. Note that this scenario repeats until the sender CPU receives the corresponding ack message.

1. Model this problem using Timed Rebeca. Send a message from the upper-left CPU (1-1) to lower-right CPU (3-3). Check at the desti- nation CPU that the amount of time that takes for the message to travel from its source to its destination is less than five seconds, using assertions.

2. Consider the collision scenario. Two CPUs want to send a message to the same CPU. Check if the two sender CPUs (1-1 and 1-3) send message to same destination CPU (2-2), both will receive their ack messages.
