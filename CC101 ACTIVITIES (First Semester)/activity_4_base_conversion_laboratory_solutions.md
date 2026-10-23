# Activity 4 – Base Conversion Laboratory Solutions

---

### 1. Convert to Decimal

$$
\begin{aligned}
&= 1(2^7) + 0(2^6) + 1(2^5) + 0(2^4) + 1(2^3) + 0(2^2) + 1(2^1) + 0(2^0) \\
&= 128 + 0 + 32 + 0 + 8 + 0 + 2 + 0 \\
&= \boxed{170_{10}}
\end{aligned}
$$

---

### 2. Convert to Decimal

$$
\begin{aligned}
&= 3(8^3) + 4(8^2) + 5(8^1) + 6(8^0) \\
&= 1536 + 256 + 40 + 6 \\
&= \boxed{1838_{10}}
\end{aligned}
$$

---

### 3. Convert to Decimal

$$
\begin{aligned}
&= 15(16^2) + 7(16^1) + 12(16^0) \\
&= 3840 + 112 + 12 \\
&= \boxed{3964_{10}}
\end{aligned}
$$

---

### 4. Convert to Binary

$$
\begin{aligned}
219 \div 2 &= 109 \quad \text{R } 1 \\
109 \div 2 &= 54 \quad \text{R } 1 \\
54 \div 2 &= 27 \quad \text{R } 0 \\
27 \div 2 &= 13 \quad \text{R } 1 \\
13 \div 2 &= 6 \quad \text{R } 1 \\
6 \div 2 &= 3 \quad \text{R } 0 \\
3 \div 2 &= 1 \quad \text{R } 1 \\
1 \div 2 &= 0 \quad \text{R } 1
\end{aligned}
$$

Read the remainders from bottom to top:

$$
\boxed{219_{10} = 11011011_2}
$$

---

### 5. Convert to Octal

$$
\begin{aligned}
1179 \div 8 &= 147 \quad \text{R } 3 \\
147 \div 8 &= 18 \quad \text{R } 3 \\
18 \div 8 &= 2 \quad \text{R } 2 \\
2 \div 8 &= 0 \quad \text{R } 2
\end{aligned}
$$

$$
\boxed{1179_{10} = 2233_8}
$$

---

### 6. Convert to Hexadecimal

$$
\begin{aligned}
2755 \div 16 &= 172 \quad \text{R } 3 \\
172 \div 16 &= 10 \quad \text{R } 12 \text{ (C)} \\
10 \div 16 &= 0 \quad \text{R } 10 \text{ (A)}
\end{aligned}
$$

$$
\boxed{2755_{10} = \text{AC3}_{16}}
$$

---

### 7. Convert to Hexadecimal

Group into sets of four bits:

$$
0101 \mid 1101 \mid 0011
$$

* $0101_2 = 5_{16}$
* $1101_2 = \text{D}_{16}$
* $0011_2 = 3_{16}$

$$
\boxed{10111010011_2 = 5\text{D}3_{16}}
$$

---

### 8. Convert to Octal

Group into sets of three bits:

$$
001 \mid 001 \mid 101 \mid 111
$$

* $001_2 = 1_8$
* $001_2 = 1_8$
* $101_2 = 5_8$
* $111_2 = 7_8$

$$
\boxed{1001101111_2 = 1157_8}
$$

---

### 9. Convert to Binary

Convert each hexadecimal digit to a 4-bit binary sequence:

* $2_{16} = 0010_2$
* $\text{E}_{16} = 1110_2$
* $8_{16} = 1000_2$

$$
0010 \mid 1110 \mid 1000
$$

$$
\boxed{2\text{E}8_{16} = 1011101000_2}
$$

---

### 10. Convert to Hexadecimal

First, convert octal to binary:
* $5_8 = 101_2$
* $2_8 = 010_2$
* $2_8 = 010_2$

$$
522_8 = 101010010_2
$$

Group into sets of four bits from right to left:

$$
0001 \mid 0101 \mid 0010
$$

* $0001_2 = 1_{16}$
* $0101_2 = 5_{16}$
* $0010_2 = 2_{16}$

$$
\boxed{522_8 = 152_{16}}
$$

---

### 11. Convert IPv4 Address to Binary

**Given:** `172.20.207.174`

* $172_{10} = 10101100_2$
* $20_{10} = 00010100_2$
* $207_{10} = 11001111_2$
* $174_{10} = 10101110_2$

**Answer:**
`10101100.00010100.11001111.10101110`

---

### 12. RGB Color Conversion

#### A. Hexadecimal to Decimal

* **Red:** $\text{BE}_{16} = 11(16) + 14 = \boxed{190}$
* **Green:** $68_{16} = 6(16) + 8 = \boxed{104}$
* **Blue:** $\text{D}5_{16} = 13(16) + 5 = \boxed{213}$

#### B. Decimal to Hexadecimal

* **Red:** $81_{10} = 5(16) + 1 = \boxed{51_{16}}$
* **Green:** $76_{10} = 4(16) + 12 = \boxed{4\text{C}_{16}}$
* **Blue:** $80_{10} = 5(16) + 0 = \boxed{50_{16}}$

---

### 13. Linux File Permissions

**Given command:**
```bash
chmod 744 report.txt
```

* $7 = 111_2 = \text{rwx}$
* $4 = 100_2 = \text{r--}$
* $4 = 100_2 = \text{r--}$

**Answer:**
$$
\boxed{\text{rwxr--r--}}
$$

---

### 14. Ten-Bit Storage

* **Number of different values:** $2^{10} = \boxed{1024}$
* **Largest decimal value:** $2^{10} - 1 = \boxed{1023}$
* **Largest binary value:** $\boxed{1111111111_2}$
* **Largest hexadecimal value:** $\boxed{3\text{FF}_{16}}$

---

### 15. Convert to Binary, Octal, and Hexadecimal

#### A. Binary

$$
\begin{aligned}
677 \div 2 &= 338 \quad \text{R } 1 \\
338 \div 2 &= 169 \quad \text{R } 0 \\
169 \div 2 &= 84 \quad \text{R } 1 \\
84 \div 2 &= 42 \quad \text{R } 0 \\
42 \div 2 &= 21 \quad \text{R } 0 \\
21 \div 2 &= 10 \quad \text{R } 1 \\
10 \div 2 &= 5 \quad \text{R } 0 \\
5 \div 2 &= 2 \quad \text{R } 1 \\
2 \div 2 &= 1 \quad \text{R } 0 \\
1 \div 2 &= 0 \quad \text{R } 1
\end{aligned}
$$

$$
\boxed{677_{10} = 1010100101_2}
$$

#### B. Octal

$$
\begin{aligned}
677 \div 8 &= 84 \quad \text{R } 5 \\
84 \div 8 &= 10 \quad \text{R } 4 \\
10 \div 8 &= 1 \quad \text{R } 2 \\
1 \div 8 &= 0 \quad \text{R } 1
\end{aligned}
$$

$$
\boxed{677_{10} = 1245_8}
$$

#### C. Hexadecimal

$$
\begin{aligned}
677 \div 16 &= 42 \quad \text{R } 5 \\
42 \div 16 &= 2 \quad \text{R } 10 \text{ (A)} \\
2 \div 16 &= 0 \quad \text{R } 2
\end{aligned}
$$

$$
\boxed{677_{10} = 2\text{A}5_{16}}
$$

---

### Error Analysis: Convert to Binary

$$
\begin{aligned}
46 \div 2 &= 23 \quad \text{R } 0 \\
23 \div 2 &= 11 \quad \text{R } 1 \\
11 \div 2 &= 5 \quad \text{R } 1 \\
5 \div 2 &= 2 \quad \text{R } 1 \\
2 \div 2 &= 1 \quad \text{R } 0 \\
1 \div 2 &= 0 \quad \text{R } 1
\end{aligned}
$$

Read the remainders from bottom to top:

$$
\boxed{46_{10} = 101110_2}
$$