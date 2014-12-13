#Bayraklar - Flags

6502 ve türevlerinde Statü Yazmacı'nın (Status Register = SR) 7 biti birer bayrağa işaret eder. 5'inci bit boştur.

7|6|5|4|3|2|1|0
-|-|-|-|-|-|-|-
N|V|-|B|D|I|Z|C

Z,C,N ve V bayrakları karşılaştırma komutlarıyla birlikte kullanılırlar. 

###Zero Flag (Z)

Akümülator, indis yazmaçlarınıdan (X ve Y) her hangi birini değiştiren komutlardan sonra eğer yazmacın değeri $00'sa Zero flag set olur. `LDA`,`LDX`,`LDY`,`INX`,`INY`,`ADC`,`SBC` komutları Z'yi etkiler. `STA`, `STX`, `STY` komutları Z'yi değiştirmez.

Zero flag'ın ikinci işlemi ise karşılaştırmadır. Karışılatşırma komutlarından sonra eğer karşılaştırılan değerler eşitşe Z set olur.

BNE (Branch while Not Equal) ve BEQ (Branch while EQual) koşullu dallanma komutları Z'ye bağlı olarak çalışırlar.

*  Z=1 ise BEQ çalışır
*  Z=0 ise BNE çalışır

Örneğin, aşağıdaki kod X=0 oluncaya kadar 8 kere çalışır.

 	         LDX #$07
	   loop: INC $d021
	         DEX
	         BNE loop
	         
###Carry Flag (C)

Aritmetik işlemlerden sonra *elde var / kalan* bilgisini taşır. `ADC`, `SBC`, `ROL`, `ROL`, `ASL` ve `LSR`komutlarından etkilenir.

Carry flag aynı zamanda karşılaştırma komutlarından sonra sonra büyük eşit bilgisini taşır. Karşılaştırılan yazmaçın değer karşılaştırılan değerden büyük veya eşitse set olur.

BCS (Branch Carry Set) ve BCC (Branch Carry Clear) koşullu dallanma komutlarıyla beraber kullanılır.

C'nin durumu SEC (Set Carry) ve CLC (Clear Carry) komutlarıyla değiştirilebilir.

###Negative Flag (N)

Z gibi N'de yazmaçları değiştiren komutlardan etkilenir. Yazılan değerin işaret biti 1 ise N yazmacı da set olur. Sayı işaretsiz (usigned) olduğunda yüksek bit'in değerini kopyalamış olur. 

N karşılaştırma komutlarından da etkilenir.

BMI (Branch Minus) ve BPL (Branch PLus) koşullu döngü komutları N'yi kullanırlar.


###oVerflow Flag (V)

V, C'nin ikiye tümleyen sistemdeki karşılığıdır. İşaretli (signed) sayılar için aritmetik işlemlerde sonucun 128'den büyük veya -128'den küçük olduğu bilgisini taşır.

`CLV` (Clear OVerflow) V'yi sıfırlar.

`PLP` ve `BIT` komutlarından da etkilenir. 




Özet Tablo: Z,C,N,V bayrakları

Bayrak|Değer Anlamı|Karşılaştırma Anlamı|Koşullu dalanma
---|---|---|---
Z | sıfır | eşit | BEQ - BNE
C | elde | büyükeşit | BCS - BCC
N | negatif | high bit | BMI - BPL
V | taşma | | BVS - BVC

