
# 1.Tranzystory polowe

## Rodzaje tranzystorów polowych (1)
- **FET** (Field Effect Transistor) - Tranzystor **polowy** lub **unipolarny**
- **JFET** (Junction FET) - tranzystor polowy **złączowy**, występuje złącze półprzewodnikowe, zawsze z półprzewodników monokrystalicznych
- **PNFET** - polowy złączowy ze złączem **p-n** (najczęściej **krzem**)
- **MESFET** - polowy złączowy ze złączem **m-s** (metal-semiconductor/metal-półprzewodnik, najczęściej - **arsenek galu GaAs**)

## Typ kanału
**Kanał** - podstawowa jednostka strukturalna tranzystora polowego, przemieszczają się w nim nośniki.
Dla tranzystora istotne są tylko nośniki **większościowe**. Może być wykonany z półprzewodnika typu **n** (przepływa strumień **elektronów**), lub typu **p** (przepływa strumień **dziur**)

**Uwaga** - **MESFET** wymaga typu **n**


## Rodzaje tranzystorów polowych (2)
- **IGFET** (Insulated Gate FET) - tranzystor polowy z izolowaną bramką
	między bramką a półprzewodnikiem jest warstwa izolacyjna (najczęściej dwutlenek krzemu $SiO_2$)
- **MISFET** (Metal-Insulator)
	![[Pasted image 20240117192827.png]]

- **MOSFET** - (Metal-Oxide-Semiconductor) - tranzystor polowy metal-tlenek-półprzewodnik, jednak w warstwie izolacyjnej występuje **dwu**tlenek krzemu, a nie tlenek.
- Tranzystor z kanałem **wbudowanym** - **normalnie załączony** (normally **ON**)
- Tranzystor z kanałem **indukowanym** - **normalnie wyłączony** (normally **OFF**)

**Kanał** można wytworzyć na dwa sposoby:
- **kanał wbudowany** - umieścić w strukturze **warstwę półprzewodnika** n lub p, które pełnią funkcję kanału, na **przeciwległych końcach** którego wyprowadza się elektrody źródła i drenu
- **kanał indukowany** - wytworzyć w strukturze **dwie oddzielne wyspy, tworzące źródło i dren**, a obszar kanału zostanie zaindukowany po przyłożeniu napięcia do elektrody bramki

Wartość prądu w kanale zależy od **liczby nośników większościowych**.
- **Wzbogacanie** - zwiększenie liczby nośników większościowych (przez elektrodę bramki)
- **Zubożanie** - zmniejszenie liczby nośników większościowych (przez elektrodę bramki)

- **EMOS** - Tranzystor z kanałem **wzbogacanym** (Enhanced MOS)
- **DMOS** - Tranzystor z kanałem **zubożanym** (Depleted MOS)

**Uwaga: nie stosuje się w praktyce zubożania kanału indukowanego**
-  **TFT** – Thin Film Transistor – tranzystor cienkowarstwowy.

## JFET (tranzystor polowy złączowy)
![[Pasted image 20240117193929.png]]

**![[Pasted image 20240117193947.png]]**

## JFET - Warunki polaryzacji

Aby tranzystor polowy mógł normalnie pracować, muszą być spełnione następujące **dwa warunki polaryzacji**:
- **Złącze bramka-kanał** musi być spolaryzowane w kierunku **zaporowym** (obszar kanału reprezentuje elektroda źródła)
- Elektrody źródła i drenu muszą być spolaryzowane tak, aby transport nośników odbywał się **od źródła do drenu**

![[Pasted image 20240117194224.png]]

## Zasada działania JFET

Strumień nośników większościowych tworzy **prąd**, zwany **prądem drenu $I_D$** , który zależy od obydwu napięć przyłożonych z zewnątrz do tranzystora: $U_{DS}$ oraz $U_{GS}$ (gate-source, drain-source) (bramka-źródło, dren-źródło)

- charakterystyki przejściowe
$$ I_D = f(U_{GS}) | _{U_{DS} = const} $$
![[Pasted image 20240117194629.png]]

- charakterystyki wyjściowe
$$ I_D = f(U_{DS}) | _{U_{GS} = const} $$
![[Pasted image 20240117194646.png]]

![[Pasted image 20240117195236.png]]








# 2.Tranzystor bipolarny jako czwórnik aktywny

## Równania hybrydowe
$$
U_1 = h_{11} \cdot I_1 + h_{12} \cdot U_2

$$
$$
I_2 = h_{21} \cdot I_1 + h_{22} \cdot U_2
$$
Równania hybrydowe są *naturalnym opisem* tranzystora bipolarnego.
zamienne niezależne:
- prąd wejściowy = $I_1$
- napięcie wyjściowe = $U_2$
Postać macierzowa:
$$
\begin{bmatrix} U_1 \\ I_2 \end{bmatrix} = H \cdot \begin{bmatrix} I_1 \\ U_2 \end{bmatrix} \Rightarrow \begin{bmatrix} U_1 \\ I_2 \end{bmatrix} = \begin{bmatrix} h_{11} & h_{12} \\ h_{21} & h_{22} \end{bmatrix}\begin{bmatrix} I_1 \\ U_2 \end{bmatrix}
$$
![[Pasted image 20240117191632.png]]
![[Pasted image 20240117191647.png]]
![[Pasted image 20240117191720.png]]
![[Pasted image 20240117191841.png]]

