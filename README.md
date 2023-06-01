# Design-and-simulate-8-bit-parity-generator-using-verilog
# Aim:
TO design and simulate 8 bit parity genetor using verilog

# HARDWARE REQUIRED :
– PC, Cyclone II , USB flasher
# SOFTWARE REQUIRED:
Quartus prime

# THEORY:
The parity generating technique is one of the most widely used error detection techniques for the
data transmission. In digital systems, when binary data is transmitted and processed, data may be
subjected to noise so that such noise can alter 0s (of data bits) to 1s and 1s to 0s.
Hence, a Parity Bit is added to the word containing data in order to make number of 1s either even
or odd. The message containing the data bits along with parity bit is transmitted from transmitter
to the receiver.
# Parity Generator and Checker
A Parity Generator is a combinational logic circuit that generates the parity bit in the transmitter.
On the other hand, a circuit that checks the parity in the receiver is called Parity Checker.

# LOGIC DIAGRAM
![image](https://github.com/RKavikeerthana/Simulation-project--Digital-Electronics/assets/120431120/32087813-b94a-4ca8-b166-6a845f800539)
# program:
```py
# developed by:R.Kavi Keerthana
# register number:212222100022

library ieee;
use ieee.std_logic_1164.all;
entity parity_chk is
      port( data:in bit_vector(7 downto 0);
                  p: in bit;
                  e: out bit);
end parity_chk;
architecture parity_arch of parity_chk is
signal temp : bit_vector(6 downto 0);
  begin
    temp(0)<=data(0) xor data(1);
    temp(1)<=temp(0) xor data(2);
    temp(2)<=temp(1) xor data(3);
    temp(3)<=temp(2) xor data(4);
    temp(4)<=temp(3) xor data(5);
    temp(5)<=temp(4) xor data(6);
    temp(6) <= temp(5) xor data(7);
    e <= p xor temp(6);
end parity_arch;
```
# TRUTH TABLE:
![image](https://github.com/RKavikeerthana/Simulation-project--Digital-Electronics/assets/120431120/9e989347-abcc-4b5b-9f3c-1df5fd67de2e)
# RTL DIAGRAM:
![image](https://github.com/RKavikeerthana/Simulation-project--Digital-Electronics/assets/120431120/15af2127-06e0-4f2a-8c67-85f2d921ad7e)
# TIMING DIAGRAM:
![image](https://github.com/RKavikeerthana/Simulation-project--Digital-Electronics/assets/120431120/2b28a35a-b7c7-486f-bca9-4e514207d2e5)




# Result:
Thus the required design and simulate 8 bit parity using verilog has executed
