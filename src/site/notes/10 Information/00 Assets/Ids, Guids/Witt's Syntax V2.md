---
{"dg-publish":true,"permalink":"/10-information/00-assets/ids-guids/witt-s-syntax-v2/","created":"2024-09-20T19:32:38.519+07:00","updated":"2024-09-20T20:36:42.710+07:00"}
---

5 bit encoding

Set 1

|     | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | a                    | b     | c   | d   | e   | f      |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------------------- | ----- | --- | --- | --- | ------ |
| 0   | A   | B   | C   | D   | E   | F   | G   | H   | I   | J   | K                    | L     | M   | N   | O   | P      |
| 1   | Q   | R   | S   | T   | U   | V   | W   | X   | Y   | Z   | <small>*NUL*</small> | \_(-) | @   | #   | &   | *Set2* |
Set 2

|     | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | a   | b   | c   | d   | e    | f      |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | ------ |
| 0   | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | /   | (   | )   | ?   | NULL | *Set1* |

Set 1 Binary

| Binary | Letter   |
| ------ | -------- |
| 00000  | A        |
| 00001  | B        |
| 00010  | C        |
| 00011  | E        |
| 00100  | F        |
| 00101  | G        |
| 00110  | H        |
| 00111  | I        |
| 01000  | J        |
| 01001  | K        |
| 01010  | M        |
| 01011  | L        |
| 01100  | N        |
| 01101  | O        |
| 01110  | P        |
| 01111  | Q        |
| 10000  | R        |
| 10001  | S        |
| 10010  | T        |
| 10011  | U        |
| 10100  | V        |
| 10101  | W        |
| 10111  | X        |
| 11000  | Y        |
| 11001  | Z        |
| 11010  | NULL     |
| 11011  | \_(or -) |
| 11100  | @        |
| 11101  | #        |
| 11110  | &        |
| 11111  | *Set2*   |
Set 2 Binary

| Binary | Letter |
| ------ | ------ |
| 0000   | 0      |
| 0001   | 1      |
| 0010   | 2      |
| 0011   | 3      |
| 0100   | 4      |
| 0101   | 5      |
| 0110   | 6      |
| 0111   | 7      |
| 1000   | 8      |
| 1001   | 9      |
| 1010   | /      |
| 1011   | (      |
| 1100   | )      |
| 1101   | ?      |
| 1110   | NULL   |
| 1111   | *Set1* |
##### Format 0001
Space Used: 32 Bits(4 reserved for identifier) | PXXX-XXXX
Budget: 28 Bits
Common Formats: (T for text, N for number)
* TTTNN = 5+5+5+**5**+4+4 = 28 bits
* Vanilla Vehicles Remastered 2 = VVR2 = 10100 10100 10000 11111 0010
##### Format 0010
Space Used: 20 Bits(4 reserved for identifier) | P???-XXXX
Budget: 16
Common Formats:
* TT = 5+5 = 10 bits
* TN = 5+5+4 = 14 bits
* TTT = 5+5+5 = 15 bits
* Paul's Tactical Apparel = PTA = 01110 10010 00000
* More Farming Mod = MFM = 01010 00100 01010
##### Format 0011
Space Used: 16 Bits(4 reserved for identifier) | P???-?XXX
Budget: 12 bits
Common formats:
* TT = 5+5 = 10 bits
* Vehicle Expansion = VE = 10100 00011