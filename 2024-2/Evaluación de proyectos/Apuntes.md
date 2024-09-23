# Primera Clase 08-08

Profesor: Eduardo Faivovich
Correo: eduardo.faivovich@mail.udp.cl
Wsp: +56993264986

NP = S1 x 0,25 + S2 x 0,25 + TRABAJO x 0,25 + CONTROLES(5) x 0,25
NF = NP x 0,7 + EXAMEN x 0,3
Eximición → NP >= 5.0 y haber rendido todas las evaluaciones.

C1 → 29/08

## Mercado financiero
Finanzas: 
- Valor del dinero en el tiempo
- Equivalencia entre montos de distintos tiempos se utiliza tasa de interés
- Tasa de interés = Precio del dinero
- Spread: En un ejemplo, es la diferencia entre la tasa de interés del 1% que un banco cobra a los prestatarios y la tasa del 0,5% que paga a los depositantes. Este spread del 0,5% representa la ganancia del banco por intermediar entre quienes necesitan préstamos y quienes depositan dinero.
## Evaluación proyectos

1. IDEA
2. ESTUDIO DEMANDA (cuanto voy a vender y a que precio)
3. ESTUDIO INGENIERIA
4. ESTUDIO PERSONAL (LGBTIQ+)
5. ESTUDIO AMBIENTAL COMUNIDAD (ONG)
6. ESTUDIO LEGAL (S.A , L.T.D.A, S.P.A)
7. INVERSIONES ($)
8. FINANCIAMIENTO (BANCO, CORFO, BONOS, ACCIONES, WARRANTS)
9. FLUJO DE CAJA
10. EVALUACIÓN T.I.R(tasa interna retorno) V.A.N(valor actualizado neto)
11. SENSIBILAD (QUE PASA SI??????)
# Clase 12-08
Banco realiza **captación**, capta dinero de la gente con un 0,6% por mes por ej. y luego el banco presta ese dinero al 1% por mes, esto se llama **colocación**.
La diferencia entre el interes de colocación con el de captación se llama **spread**, con eso el banco tiene utilidad.

## Matemática financiera
- **Interés simple:**  se calcula sobre el mismo capital (se paga todo al final)
	- Un crédito de $5000 a una tasa de interés del 8% anual durante 5 años.
		- Cálculo del interés anual: $5000 * 8% = $400
		- Como el interés es simple, se paga el mismo monto de interés cada año.
		- Interés total al final de 5 años: $400 * 5 = **$2000**
		- Monto total a pagar al final del periodo: $5000 (capital inicial) + $2000 (interés total) = **$7000**
- **Interés compuesto**: se calcula sobre monto anterior con interes.
	- Supongamos un crédito de $5000 al 8% anual durante 5 años, donde los intereses se reinvierten al final de cada año.
        1. **Año 1:**
            - Capital inicial: $5000
            - Interés del primer año: $5000 * 8% = $400
            - Monto al final del año 1: $5000 + $400 = **$5400**
        2. **Año 2:**
            - Capital inicial: $5400
            - Interés del segundo año: $5400 * 8% = $432
            - Monto al final del año 2: $5400 + $432 = **$5832**
        3. **Año 3:**
            - Capital inicial: $5832
            - Interés del tercer año: $5832 * 8% = $466.56
            - Monto al final del año 3: $5832 + $466.56 = **$6298.56**
        4. **Año 4:**
            - Capital inicial: $6298.56
            - Interés del cuarto año: $6298.56 * 8% = $503.88
            - Monto al final del año 4: $6298.56 + $503.88 = **$6802.44**
        5. **Año 5:**
            - Capital inicial: $6802.44
            - Interés del quinto año: $6802.44 * 8% = $544.20
            - Monto al final del año 5: $6802.44 + $544.20 = **$7346.64**
        - Entonces, al final de 5 años, el monto total con interés compuesto es **$7346.64**.

## Fórmulas:
### **Interés Simple**

La fórmula del interés simple es:
I=P×i×n
- **I**: Interés total
- **P**: Capital (monto inicial)
- **i**: Tasa de interés por periodo (en decimal, por ejemplo, 8% = 0.08)
- **n**: Número de periodos
El monto total a pagar al final del periodo es:
F=P+I
- **F**: Monto total a pagar
- **P**: Capital
- **I**: Interés total
### **Interés Compuesto**
La fórmula del interés compuesto es:
F=P×(1+i)^n
- **F**: Monto total al final del periodo
- **P**: Capital
- **i**: Tasa de interés por periodo (en decimal)
- **n**: Número de periodos
Para calcular solo el interés acumulado en un esquema de interés compuesto:
I=M−P
- **I**: Interés total acumulado
- **M**: Monto total al final del periodo
- **P**: Capital
## Tabla desarrollo al crédito
**Fórmula para calcular la cuota (A)**
![[Pasted image 20240812170541.png]]
Donde:
- **P**: Capital (monto del préstamo)
- **A**: Cuota periódica (monto a pagar cada periodo)
- **i**: Tasa de interés por periodo (en decimal)
- **n**: Número de periodos
- **Amortización:** Cuota - interés
Por lo tanto: A=1252,28

| Periodo | Interés (8%) | Cuota   | Amortización | Saldo               |
| ------- | ------------ | ------- | ------------ | ------------------- |
| 1       | 400          | 1252,28 | 852,28       | 5000-852,28=4147,72 |
| 2       | 331,82       | 1252,28 | 920,46       | 3227,26             |
| 3       | 258,18       | 1252,28 | 994,1        | 2233,16             |
| 4       | 178,65       | 1252,28 | 1073,63      | 1159,53             |
| 5       | 92,76        | 1252,28 | 1159,52      | 0,01                |

# Clase 19-08
## Matemática Financiera
- Ejemplo 1: ¿Cuál es el valor a obtener si deposita hoy $1000 a 5 años al 8% anual?
	- F = P x (1+i)^n
	- F = 1000 x (1,08)^5
	- F = 1469,32
- Ejemplo 2: ¿A que tasa de interés se quintuplica 1000 en 5 años?
	- 5000 = 1000 x (1+i)^5
	- 1,3797 = 1+i
	- i = 37,97%
- Ejemplo 3: ¿A cuanto equivale hoy un monto que es $450 hace un año y equivaldrá a $550 el próximo año?
	- 550 = 450(1+i)^2
	- 1+i = 1,1055
	- i = 10,55%
	- Ahora para HOY:
		- F = 450(1,1055) = $497,5 equivale hoy
- Ejemplo 4:  Calcule cuota de un crédito de $5000 a 5 años, tasa anual 8%
	- ![[Pasted image 20240812170541.png]]
	- P = 5000
	- i = 0,08
	- n = 5
	- A = 5000 x 0,08 (1,08)^5 /(1,08)^5 -1
	- A = $1252,28
- Ejemplo 5: Cuántos pagos de $500 debo realizar para pagar un crédito de $5000 al 6% por periodo?
	- ![[Pasted image 20240812170541.png]]
	- P = 5000
	- A = 500
	- i = 0,06
	- n =?
	- 10 = 1,06^n - 1 / (0,06 x 1,06^n)
	- 0,6 x 1,06^n = 1,06^n -1
	- n = 15,72 aprox 16
- Ejemplo 6: Calcule en t=6 despues de 6 años el valor de maquina que cuesta 1000 y debo hacer mantenciones anuales por 500 y además en t=2 y en t=4 debo hacer ajustes por 800 cada uno. Otra pregunta: Aceptaria otra maquina similar que cuesta 4700 en t=0 e incluye todas las mantenciones? **Tasa de interes 10% anual**
	- 1. 1000(1,1)^6 = 1771,56
	- 2. 500 [1,1^6 -1]/0,1 = 3857,8
	- 3. 800(1,1)^4 = 1171,28
	- 4. 800(1,1)^2 = 968
	-  entonces en t=6 el valor de la maquina es 7768,64
	- Entonces si volvemos a t=0, dividiendo por 1,1^6 da 4385,19
	- por lo que no aceptaria otra maquina similar que cuesta 4700 en t=0

# Clase 22-08
- Tasa real efectiva: se calcula a partir de tasa nominal (nombre)
	- Flujo financiero:
		- Anual → tasa de interés anual
		- Semestral → tasa de interés semestral
		- Trimestras → tasa de interés trimestral
	- Forma de cálculo:
		- Método 1: Se divide la tasa nominal por periodos de composición y luego se eleva a periodos requeridos.
		- Método 2: fórmula: Tasa_real_efectiva = (1 + tasa_nominal/periodos_composición)^periodosRequeridos -1
- Ejemplos: (EN EL EXCEL Clase_22-08)
	1. Si la tasa nominal anual es 12% compuesta mensual calcule:
		1. Tasa real efectiva mensual
		2. Tasa real efectiva trimestral
		3. Tasa real efectiva semestral
		4. Tasa real efectiva anual
		Desarrollo:
			Excel...
				Cuando la composicion es mensual los periodos de composicion son 12, cuando es semestral es por 2, trimestral es por 4.
	2. Una persona deposita $500 cada 6 meses por 7 a una tasa nominal anual del 20% compuesta trimestral. ¿cuanto tendrá al final de los 7 años?
		Desarrollo:
			Excel...
	3. Suponga que usted contrata un crédito con el banco Edwards por $65.000.000 con un interés anual del 8% nominal anual  compuesto semestral  por  8 años, cuotas anuales . Luego de pagar la 3° cuota, el banco BCI  se contacta con usted ofreciendo la oportunidad de reprogramar su crédito por el monto restante a 3 años con una tasa del 5% anual . Le consultan: a)Dado lo anterior se pide realizar las tablas de desarrollo de  cada crédito . B) Calcule el total pagado en valor presente , suponiendo tasa de interés del 3% anual. C)  Si banco  Edwards   le aplica una multa de tres  meses  de intereses al 1% por mes , sobre saldo insoluto  por prepago de deuda , que se financia con  crédito total de  banco BCI , calcule el monto del nuevo crédito con banco BCI.
# Clase 26-08
- Continuando ejemplos...(EN EL EXCEL Clase_22-08)
	4. 
		a) Calcule diferencia de jubilación hombre y mujer , siendo que el hombre en Chile se jubila a los 65 años y a la mujer a los 60 años y ambos comienzan a imponer en su vida laboral a los 25 años, siendo la expectativa de vida hombre 85 años y mujer 90 años. Adicionalmente la mujer en Chile tiene un sueldo 20% menor al hombre para el mismo cargo. Suponga el hombre gana un sueldo mensual de $1.670.000 y la mujer un 20% menos. En ambos casos su renta mensual está afecta a descuentos del 13% AFP y 7% Isapre y el diferencial se aplica un impuesto del 10% en cada caso. Suponga rentabilidad de los fondos AFP es del 0,2% por mes.  
		
		b)Si el hombre desea jubilarse con $300.000 mensual adicional y la mujer con $500.000 mensual, adicional ¿cuanto mas deberá aportar a su fondo previsional durante su vida laboral?.
# Clase 23-09
Ejercicio tipo solemne
La solemne tiene 3 ejercicios
1. aprobacion de credito
2. tabla dinamica
3. flujo de caja