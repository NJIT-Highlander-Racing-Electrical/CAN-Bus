# Message ID's for each subsystem								
								
|	CAN ID (dec)	|	CAN ID (hex)	|	Subsystem	|	Message	| Data Type |
|	:-:	|	:-:	|	:-:	|	:-:	| :-:	|
|	1	|	0x01	|	CVT Tachometer	|	Primary RPM	| INT |
|	2	|	0x02	|	CVT Tachometer	|	Secondary RPM	| INT |
|	3	|	0x03	|	CVT Tachometer	|	CVT Primary Ambient Temperature	| INT |
|	4	|	0x04	|	CVT Tachometer	|	CVT Secondary Ambient Temperature		| INT |
|	5	|	0x05	|	CVT Tachometer	|		|
|	6	|	0x06	|	CVT Tachometer	|		|
|	7	|	0x07	|	CVT Tachometer	|		|
|	8	|	0x08	|	CVT Tachometer	|		|
|	9	|	0x09	|	CVT Tachometer	|		|
|	10	|	0x0A	|	CVT Tachometer	|		|
|	11	|	0x0B	|	Wheel Speed Sensors	|	Front Left Wheel RPM	| INT |
|	12	|	0x0C	|	Wheel Speed Sensors	|	Front Right Wheel RPM	| INT |
|	13	|	0x0D	|	Wheel Speed Sensors	|	Rear Left Wheel RPM	| INT |
|	14	|	0x0E	|	Wheel Speed Sensors	|	Rear Right Wheel RPM	| INT |
|	15	|	0x0F	|	Wheel Speed Sensors	| Front Left Wheel State		|INT |
|	16	|	0x10	|	Wheel Speed Sensors	| Front Right Wheel State		|INT |
|	17	|	0x11	|	Wheel Speed Sensors	| Rear Left Wheel State		|INT |
|	18	|	0x12	|	Wheel Speed Sensors	| Rear Right Wheel State		|INT |
|	19	|	0x13	|	Wheel Speed Sensors	|		|
|	20	|	0x14	|	Wheel Speed Sensors	|		|
|	21	|	0x15	|	Steering/Pedal Sensors	|	Gas Pedal Percentage	|INT |
|	22	|	0x16	|	Steering/Pedal Sensors	|	Brake Pedal Percentage	|INT |
|	23	|	0x17	|	Steering/Pedal Sensors	|		|
|	24	|	0x18	|	Steering/Pedal Sensors	|		|
|	25	|	0x19	|	Steering/Pedal Sensors	|		|
|	26	|	0x1A	|	Steering/Pedal Sensors	|		|
|	27	|	0x1B	|	Steering/Pedal Sensors	|		|
|	28	|	0x1C	|	Steering/Pedal Sensors	|		|
|	29	|	0x1D	|	Steering/Pedal Sensors	|		|
|	30	|	0x1E	|	Steering/Pedal Sensors	|		|
|	31	|	0x1F	|	Suspension Displacement	|	Front Left Displacement (inches)	| FLOAT |
|	32	|	0x20	|	Suspension Displacement	|	Front Right Displacement (inches)	|FLOAT |
|	33	|	0x21	|	Suspension Displacement	|	Rear Left Displacement (inches)		|FLOAT |
|	34	|	0x22	|	Suspension Displacement	|	Rear Right Displacement (inches)	|FLOAT |
|	35	|	0x23	|	Suspension Displacement	|		|
|	36	|	0x24	|	Suspension Displacement	|		|
|	37	|	0x25	|	Suspension Displacement	|		|
|	38	|	0x26	|	Suspension Displacement	|		|
|	39	|	0x27	|	Suspension Displacement	|		|
|	40	|	0x28	|	Suspension Displacement	|		|
|	41	|	0x29	|	DAS	|	Acceleration X	|FLOAT |
|	42	|	0x2A	|	DAS	|	Acceleration Y	|FLOAT |
|	43	|	0x2B	|	DAS	|	Acceleration Z	|FLOAT |
|	44	|	0x2C	|	DAS	|	Gyroscope Roll	|FLOAT |
|	45	|	0x2D	|	DAS	|	Gyroscope Pitch	|FLOAT |
|	46	|	0x2E	|	DAS	|	Gyroscope Yaw	|FLOAT |
|	47	|	0x2F	|	DAS	|	GPS Latitude	|FLOAT |
|	48	|	0x30	|	DAS	|	GPS Longitude	|FLOAT |
|	49	|	0x31	|	DAS	|	GPS Time -- Hour	| INT |
|	50	|	0x32	|	DAS	|	GPS Time -- Minute	|INT |
|	51	|	0x33	|	DAS	|	GPS Time -- Second	|INT |
|	52	|	0x34	|	DAS	|	GPS Date -- Month	|INT |
|	53	|	0x35	|	DAS	|	GPS Date -- Day	|INT |
|	54	|	0x36	|	DAS	|	GPS Date -- Year	|INT |
|	55	|	0x37	|	DAS	|	GPS Altitude	|INT |
|	56	|	0x38	|	DAS	|	GPS Heading 	|INT |
|	57	|	0x39	|	DAS	| 	GPS Velocity	 | FLOAT |
|	58	|	0x3A	|	DAS	| SD Data Logging Active	| INT (functions as bool)|
|	59	|	0x3B	|	DAS	|		|
|	60	|	0x3C	|	DAS	|		|
|	61	|	0x3D	|	DAS	|		|
|	62	|	0x3E	|	DAS	|		|
|	63	|	0x3F	|	DAS	|		|
|	64	|	0x40	|	DAS	|		|
|	65	|	0x41	|	DAS	|		|
|	66	|	0x42	|	Dashboard	|		|
|	67	|	0x43	|	Dashboard	|		|
|	68	|	0x44	|	Dashboard	|		|
|	69	|	0x45	|	Dashboard	|		|
|	70	|	0x46	|	Dashboard	|		|
|	71	|	0x47	|	Power	|	Battery Percentage	| INT |
|	72	|	0x48	|	Power	|		|
|	73	|	0x49	|	Power	|		|
|	74	|	0x4A	|	Power	|		|
|	75	|	0x4B	|	Power	|		|
|	76	|	0x4C	|	Fuel Sensor	|
|	77	|	0x4D	|	Fuel Sensor	|		|
|	78	|	0x4E	|	Fuel Sensor	|		|
|	79	|	0x4F	|	Fuel Sensor	|		|
|	80	|	0x50	|	Fuel Sensor	|		|
|	81	|	0x51	|		|		|
|	82	|	0x52	|		|		|
|	83	|	0x53	|		|		|
|	84	|	0x54	|		|		|
|	85	|	0x55	|		|		|
|	86	|	0x56	|		|		|
|	87	|	0x57	|		|		|
|	88	|	0x58	|		|		|
|	89	|	0x59	|		|		|
|	90	|	0x5A	| Status Bit - CVT Tachometer		|	Status	| BYTE
|	91	|	0x5B	|	Status Bit - Base Station	|	Status	|BYTE
|	92	|	0x5C	|	Status Bit - Dashboard	|	Status	|BYTE
|	93	|	0x5D	|	Status Bit - DAS	|	Status	|BYTE
|	94	|	0x5E	|	Status Bit - Wheel Speed	|Status		|BYTE
|	95	|	0x5F	|	Status Bit - Pedals	|	Status	|BYTE
|	96	|	0x60	|		|		|
|	97	|	0x61	|		|		|
|	98	|	0x62	|		|		|
|	99	|	0x63	|		|		|
|	100	|	0x64	|		|		|
