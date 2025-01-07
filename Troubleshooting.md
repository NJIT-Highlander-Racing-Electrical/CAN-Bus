# Troubleshooting

A list of issues I have ran into, with fixes, if applicable


## Received message data not correct

I had an issue where the message data was not updating on the receiving end even though the changing end was sending new values. This turned out to be a result of Serial prints in the receiving program. The sender was sending data about every 1 ms, but the serial prints themselves in each loop were taking 2 or more ms. Increasing the baud rate and making messages more concise fixed this.

## CAN packets jumping to wrong case

This follows similarly to the issue above with serial prints. The long serial prints and low baud rate resulted in RTR messages that we sent out returning to us. 

## Received Message data bouncing between value and zero 

This stemmed from the switch...case statement not being included in the "if" statement that runs when a packet is received. Since the packet was never being parsed in the if statement, it would run forever even if there were no packets

## Subsystem that receives RTR transmits its response many times

This was due to the issue listed above. the switch..case was not in the if statement, so the RTR was never processed properly, and it kept sending. Another part of this issue is that it would still send four times after this. This was due to not checking the packetId, only checking if the packet was an Rtr. Thus, it was picking up all four different RTRs that were sent, even if they weren't CVT RTRs

## Message data on logic analyzer does not match what was sent

We use CAN.print which has the same functionality as Serial.print. If you send it a "1", it will interpret that as an ASCII 1, and send the hex code for that instead.
