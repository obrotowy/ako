# Wyprowadzenie wzorów
## Mnożenie
$a = M_a * 2^{W_a} \\
b = M_b * 2^{W_b} \\
c = a \cdot b = (M_a \cdot 2^{W_a}) \cdot (M_b \cdot 2^{W_b}) = (M_a \cdot M_b) 2^{W_a + W_b}$

## Dzielenie
$a = M_a * 2^{W_a} \\
b = M_b * 2^{W_b} \\
c = \frac{a}{b} = \frac{M_a * 2^{W_a}}{M_b * 2^{W_b}} = \frac{M_a}{M_b}\cdot 2^{W_a - W_b}$

# Przykłady
## 1.
Dla podanych liczb a i b wyznacz $\frac{a}{b}$:\
**a = 4F805252h \
b = 3D805252h**

## 2.
Dla podanych liczb a i b wyznac $a \cdot\ b$: \
**a = 4140000h\
b = 44B0000h**

# Rozwiązania
## Rozwiązanie przykład 1
Zauważamy, że tylko 9 najstarszych bitów obu liczb się różnią -> Mantysy są takie same -> $M_a = M_b$ \
a = 0 10011111 000...
b = 0 01111011 000...

$W_a = (10011111)_2 - 127_{10} = 32$    // Warto zauważyć, że najstarszy bit ma wartość 128, wystarczy więc tylko zsumować pozostałe bity i dodać 1

$W_b = (01111011)_2 - 127_{10} = -4$ // Tu warto zauważyć, że 01111111 = 127, a w naszym wykladniku brakuje tylko 2 bitu o wartości 4

$\frac{a}{b} = \frac{M_a}{M_b} \cdot 2^{W_a - W_b} = 1 \cdot 2^{32-(-4)} = 2^{36} = (010100011000...)_2 = 51800000h$


## Rozwiąznie przykład 2
a = 0 10000010 10... \
b = 0 10001001 011...

$a \cdot b = (1.10)_2 \cdot 2^3 \cdot (1.011)_2 \cdot 2^{10} = (1.10 \cdot 1.011)_2 \cdot 2^{13} = (1.5 \cdot 1.375)_{10} \cdot 2^{13} = (2.0625)_{10} \cdot 2^{13} = (10.0001)_2\cdot2^{13} = (1.00001)_2 \cdot 2^{14}$

1.5 * 1.375 polecam zrobić poprzez mnożenie pisemne, można też uskuteczniac mnożenie pisemne binarnie

$(1.10001)_2 \cdot 2^{14}$ = 0 10001101 00001... = **46840000h**