# Troubleshooting

A list of issues I have ran into, with fixes, if applicable


## Received message data not correct

I had an issue where the message data was not updating on the receiving end even though the changing end was sending new values. This turned out to be a result of Serial prints in the receiving program. The sender was sending data about every 1 ms, but the serial prints themselves in each loop were taking 2 or more ms. Increasing the baud rate and making messages more concise fixed this.

## CAN packets jumping to wrong case

This follows similarly to the issue above with serial prints. The long serial prints and low baud rate resulted in RTR messages that we sent out returning to us. 

## Received Message data bouncing between value and zero 

Not sure on a fix for this yet

## Subsystem that receives RTR transmits its response many times

Not sure on a fix for this yet

## Message data on logic analyzer does not match what was sent

We use CAN.print which has the same functionality as Serial.print. If you send it a "1", it will interpret that as an ASCII 1, and send the hex code for that instead.
