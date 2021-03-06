### 1. chip

#### 1.1 chip info

chip name : Raspberry Pi 4B

iic pin: SCL/SDA GPIO3/GPIO2

### 2. install

#### 2.1 install info

```shell
make
```

### 3. pcf8574

#### 3.1 command Instruction

​          pcf8574 is a basic command which can test all pcf8574 driver function:

​          -i        show pcf8574 chip and driver information.

​          -h       show pcf8574 help.

​          -p       show pcf8574 pin connections of the current board.

​          -t  (readwrite <times> -a  (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) )

​          -t readwrite <times> -a  (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)        run pcf8574 read write test.times means test times.

​          -c basic (-i -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)|-o (0 | 1) -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7))

​          -c basic -i -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)      run pcf8574 read function.

​          -c basic -o (0 | 1) -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)        run pcf8574 write function.

#### 3.2 command example

```shell
./pcf8574 -i

pcf8574: chip is NXP PCF8574.
pcf8574: manufacturer is NXP.
pcf8574: interface is IIC.
pcf8574: driver version is 1.0.
pcf8574: min supply voltage is 2.5V.
pcf8574: max supply voltage is 6.0V.
pcf8574: max current is 200.00mA.
pcf8574: max temperature is 85.0C.
pcf8574: min temperature is -40.0C.
```

```shell
./pcf8574 -p

pcf8574: SCL connected to GPIO3(BCM).
pcf8574: SDA connected to GPIO2(BCM).
```

```shell
./pcf8574 -t readwrite 3 -a 0

pcf8574: chip is NXP PCF8574.
pcf8574: manufacturer is NXP.
pcf8574: interface is IIC.
pcf8574: driver version is 2.0.
pcf8574: min supply voltage is 2.5V.
pcf8574: max supply voltage is 6.0V.
pcf8574: max current is 200.00mA.
pcf8574: max temperature is 85.0C.
pcf8574: min temperature is -40.0C.
pcf8574: start read write test.
pcf8574: read PIN 0 is 1.
pcf8574: read PIN 1 is 0.
pcf8574: read PIN 2 is 1.
pcf8574: read PIN 3 is 1.
pcf8574: write PIN 4 low.
pcf8574: write PIN 5 high.
pcf8574: write PIN 6 low.
pcf8574: write PIN 7 high.
pcf8574: read PIN 0 is 1.
pcf8574: read PIN 1 is 0.
pcf8574: read PIN 2 is 1.
pcf8574: read PIN 3 is 1.
pcf8574: write PIN 4 low.
pcf8574: write PIN 5 high.
pcf8574: write PIN 6 low.
pcf8574: write PIN 7 high.
pcf8574: read PIN 0 is 1.
pcf8574: read PIN 1 is 0.
pcf8574: read PIN 2 is 1.
pcf8574: read PIN 3 is 1.
pcf8574: write PIN 4 low.
pcf8574: write PIN 5 high.
pcf8574: write PIN 6 low.
pcf8574: write PIN 7 high.
pcf8574: finish read write test.
```

```shell
./pcf8574 -c basic -i -a 0 -p 1 

pcf8574: read 1 pin is 0.
```

```shell
./pcf8574 -c basic -o 0 -a 0 -p 7  

pcf8574: write 7 pin level 0.
```

```shell
./pcf8574 -h

pcf8574 -i
	show pcf8574 chip and driver information.
pcf8574 -h
	show pcf8574 help.
pcf8574 -p
	show pcf8574 pin connections of the current board.
pcf8574 -t readwrite <times> -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)
	run pcf8574 read write test.times means test times.
pcf8574 -c basic -i -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)
	run pcf8574 read function.
pcf8574 -c basic -o (0 | 1) -a (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7) -p (0 | 1 | 2 | 3 | 4 | 5 | 6 | 7)
	run pcf8574 write function.
```

