Hasta la clase 27-08 incluyendola

# Repaso de conceptos básicos de Biología Molecular
### 1. Introducción al lenguaje en Biología Molecular
**Lenguaje actual**:  
En la computación tradicional, el lenguaje común se basa en números binarios (0 y 1), que representan voltajes en sistemas electrónicos.
**Lenguaje necesario para este curso**:  
El curso se centrará en integrar un nuevo paradigma de modelamiento, diseño y simulación, utilizando cadenas de ADN en lugar de números binarios.

---
### 2. ¿Qué es el ADN?
- El ADN es un compuesto químico que forma la base de la caracterización de cualquier organismo vivo.
- En lugar de bits binarios, el ADN utiliza 4 bases: adenina (A), citosina (C), timina (T) y guanina (G).
- El ADN define:
    - Las propiedades observables de un organismo (fenotipo).
    - Los procesos operativos del organismo (como la comunicación celular o la síntesis de proteínas).
---
### 3. Terminología
1. **ADN**: Molécula que almacena las características y funciones de los seres vivos.
2. **ARN**: Molécula derivada del ADN que sirve como una copia móvil para la síntesis de proteínas.
3. **Codón**: Tripleta de bases del ARN que codifican un aminoácido.
4. **Aminoácido**: Unidad química que forma las proteínas (hay 20 tipos diferentes).
5. **Proteína**: Secuencia de aminoácidos que realiza funciones esenciales en los organismos.
6. **Polimerasa (ADN/ARN)**: Enzima que produce bases a partir de nutrientes.
7. **Ribosoma**: Orgánulo encargado de sintetizar proteínas a partir del ARN mensajero (mRNA).
---
### 4. ADN en la Computación Biomolecular
- Las cadenas de ADN pueden ser simples o dobles y se componen de combinaciones de cuatro nucleótidos.
- La secuencia del ADN proporciona patrones para la síntesis de proteínas.
---
### 5. Combinatoria en ADN
- Mientras que los sistemas binarios (bits) tienen 2^n combinaciones posibles, las cadenas de ADN tienen 4^n combinaciones debido a la presencia de 4 bases diferentes.
---
### 6. Principio de Complementariedad de Watson-Crick
- Las cadenas de ADN complementarias interactúan entre sí según las afinidades entre nucleótidos, lo que es clave para tecnologías como la computación con ADN.
---
### 7. Dogma Central de la Biología
- El ADN es equivalente al "código fuente" de la vida. Para ser utilizado, pasa por dos transformaciones:
    1. **Transcripción**: ADN se convierte en ARN.
    2. **Traducción**: El ARN se convierte en proteínas.
---
### 8. Motores de la Vida
- Los elementos discutidos son fundamentales para la computación/programación biomolecular.
- En la próxima sesión se abordarán organismos y su papel en la biología programable.
# Organismos, organismos modelo, y su rol
### 1. Introducción: Abstracción
- En la clase anterior se revisaron elementos fundamentales de la vida, sin considerar la "escala" o nivel de abstracción.
- En esta sesión se sube un nivel en la escala de abstracción, introduciendo la célula como un elemento de procesamiento biológico.
---
### 2. La Célula
- Es la unidad mínima de vida (aunque otros actores como los fagos pueden cuestionarse).
- Está compuesta de una membrana, núcleo y citoplasma, y sus funciones están relacionadas con el ADN como lenguaje universal de los seres vivos.
---
### 3. Composición de la Célula
- Las células se ven como "contenedores" que incluyen partes esenciales para llevar a cabo procesos vitales.
- Estos procesos dependen del tipo de célula y de la información que poseen.
---
### 4. Analogía: La Célula como Unidad de Procesamiento
- Siguiendo el Dogma Central de la Biología, la síntesis de proteínas es clave: ADN → ARN → Proteína.
- Las proteínas son responsables de las funciones celulares y activan diversas actividades dentro de la célula.
---
### 5. Ejemplos de Funciones Celulares
1. **Repressilator**: Circuito sintético fundacional.
2. **Ruta metabólica de la glucosa**: Un ejemplo más complejo.
3. **Propulsión flagelar de bacterias**: Desplazamiento de bacterias mediante flagelos.
---
### 6. Mecanismos detrás de las Funciones Celulares
- Las funciones descritas anteriormente dependen de la producción de proteínas específicas o cascadas de proteínas que inducen las funciones celulares.
- Se analizará en detalle cómo se diseña el Repressilator en clases posteriores.
---
### 7. Tipos de Células
1. **Eucariotas**:
    - Tienen membranas y orgánulos especializados.
    - El material genético se encuentra en un núcleo.
    - Son típicas de animales y organismos pluricelulares.
    - Organismo modelo: **S. Cerevisiae**.
2. **Procariotas**:
    - Estructura más simple, sin membrana nuclear.
    - Material genético en el citoplasma.
    - Incluyen bacterias y arqueas, que pueden funcionar en consorcios.
    - Organismo modelo: **E. Coli**.
---
### 8. Funciones Celulares Importantes
1. **Expresión genética**: Aplicación del Dogma Central de la Biología, clave para la biología programable.
2. **Crecimiento y división**: Las células absorben nutrientes y se reproducen.
3. **Señalización**: Comunicación entre células o con su entorno.
4. **Evolución**: Adaptación y cambio de las células a lo largo del tiempo para su supervivencia.
---
### 9. Conclusión: Próximos Pasos
- La célula **E. Coli** será el foco de estudio debido a su simplicidad y amplio conocimiento.
- En la próxima sesión se abordará la **expresión genética** y su relación con el paradigma computacional, junto con la introducción de otros actores clave en la biología programable.
# Expresión genética: procesos y actores asociados
### 1. Introducción
- En clases anteriores se observó el funcionamiento de la célula en sistemas biológicos.
- En esta sesión, se analizarán las acciones del ADN, ARN y proteínas en la biología programable con un mayor grado de abstracción.
---
### 2. Dogma Central de la Biología
- El Dogma Central conecta al ADN, ARN y proteínas, donde las proteínas son responsables de las funciones celulares.
- Este dogma es fundamental para entender y programar circuitos genéticos en biología programable.
---
### 3. Programación basada en el Dogma Central
- El objetivo es vincular conceptos biológicos con la lógica computacional/electrónica.
- Se introducen los componentes esenciales para la construcción de circuitos genéticos.
---
### 4. Glosario de términos clave
1. **Promotor**: Región del ADN donde se une la ARN polimerasa para iniciar la transcripción.
2. **Ribosome Binding Site (RBS)**: Área en el ARN donde los ribosomas se unen para iniciar la traducción.
3. **Coding Sequence (CDS)**: Secuencia de ADN que sirve de plantilla para su transcripción a ARN.
4. **Terminador**: Secuencia de ADN que marca el fin de la transcripción.
---
### 5. Interacciones genéticas
1. **Represión**: Interacción que impide el inicio de la transcripción en un promotor.
2. **Activación**: Promueve la transcripción y posterior traducción de una secuencia de ADN.
    - Estas interacciones ocurren entre proteínas (factores de transcripción) y promotores.
---
### 6. Estructuras genéticas
1. **Operón**: Conjunto de genes cuya transcripción y traducción están regulados por un único promotor.
2. **Plásmido**: Fragmento circular de ADN que agrupa operones y aísla funcionalidades específicas. Suelen estar presentes en varias copias en una célula.
---
### 7. Construcción de circuitos genéticos
- El proceso se realiza "de abajo hacia arriba" (bottom-up):
    - Diseño de operones.
    - Colocación de los operones en un plásmido.
    - Inserción del plásmido en la célula.
- Este proceso es análogo a la secuencia de implementar, compilar y ejecutar en una máquina computacional.
---
### 8. Analogía biológica-computacional
- Los sistemas biológicos son analógicos en términos de la expresión de proteínas.
- Sin embargo, se pueden aproximar a una representación digital (0s y 1s) para entender la biología desde una perspectiva computacional.
---
### 9. Ejemplos de circuitos genéticos
- **Circuito 1** y **Circuito 2**: Ejemplos prácticos de circuitos sintéticos en biología programable (los detalles no están especificados en el documento).
---
### 10. Conclusión y próxima clase
- Se han introducido herramientas para el diseño y estructura de circuitos sintéticos.
- En la próxima clase se agregarán más herramientas y procesos importantes, reforzando la interpretación electrónica de los conceptos biológicos aprendidos.
# Otras herramientas y consideraciones
### 1. Introducción
- Se han establecido los fundamentos de la biología programable en células y la estructura para construir sistemas biológicos.
- En esta sesión se presentarán herramientas adicionales y se discutirá la relación entre la biología programable y la electrónica.
---
### 2. Herramientas complementarias
- Aunque ya se tienen las herramientas básicas para construir circuitos genéticos, aún no se ha diseñado ningún circuito.
- Se introducirá el uso de herramientas adicionales que complementan las ya vistas.
---
### 3. Sistema CRISPR/Cas9
- **CRISPR (Clustered Regularly Interspaced Short Palindromic Repeats)** es un sistema de edición genética que deriva del sistema inmune de bacterias y arqueas, usado desde 2012.
- Los componentes principales son:
    1. **Proteína Cas9**: Reconoce y corta secuencias específicas de ADN.
    2. **gRNA (ARN guía)**: Sirve de guía para que Cas9 localice el sitio exacto en la cadena de ADN que debe cortar.
#### Usos del CRISPR/Cas9 en biología programable:
- **Inserción**: Añadir una porción de ADN a una secuencia existente.
- **Eliminación**: Remover una porción de ADN de una secuencia.
- **Represión**: Usar dCas9 para bloquear la expresión genética.
---
### 4. Variantes del sistema CRISPR
- Se están explorando variantes como el uso de proteínas Cas12 y Acrs (inhibidores del CRISPR provenientes de los fagos).
---
### 5. Crecimiento y división celular
- **Crecimiento celular**: Las células consumen nutrientes, lo que les permite crecer, dividirse y proliferar.
- La velocidad de crecimiento y división varía según el tipo de célula y la carga metabólica. Por ejemplo, las **E. Coli** tienen tiempos de división entre 20 y 40 minutos.
---
### 6. Asociación de circuitos genéticos
- Se hace una revisión de los circuitos genéticos vistos en clases anteriores.
- Se busca agregar más operaciones lógicas para tener un mayor control sobre los circuitos biológicos.
---
### 7. Próxima clase
- Ahora los estudiantes están capacitados para leer y diseñar circuitos básicos.
- En las próximas sesiones se estudiarán circuitos más complejos y redes de células con comunicación intercelular.
# Diseño de circuitos
### 1. Introducción: Diseño y aspectos a considerar
- Se han definido partes básicas y herramientas para diseñar e implementar circuitos genéticos.
- Estas herramientas permiten no solo diseñar circuitos sintéticos, sino también leer cualquier circuito genético.
- Aunque el tema pertenece mayoritariamente a la unidad de Biología Sintética, hoy se discutirán los lineamientos básicos de diseño de circuitos.
---
### 2. Estructura básica de un circuito
- Los circuitos transcripcionales generalmente incluyen:
    1. Promotor
    2. Operador
    3. RBS (Ribosome Binding Site)
    4. Genes
    5. Terminador
- Los factores del entorno pueden influir en la operación de un circuito.
---
### 3. Notación y herramientas de diseño
- Se menciona el lenguaje gráfico **SBOL**, que se discutirá más adelante en el curso.
- SBOL es una ontología que facilita el diseño y la representación de circuitos genéticos.
---
### 4. Ubicación de los circuitos
- Los circuitos genéticos se programan con ADN y deben ser ubicados en:
    1. **Genoma** (equivalente a un sistema operativo en términos computacionales).
    2. **Plásmidos** (contenedores de procesos adicionales).
- **Plásmidos** son preferibles para alojar circuitos sintéticos debido a su:
    - **Control**: Codifican rasgos beneficiosos (resistencia a toxinas, defensa, etc.).
    - **Maleabilidad evolutiva**: Son móviles e independientes, más fáciles de modificar que el genoma.
    - **Facilidad de integración**: Se pueden insertar circuitos en plásmidos mediante la transformación de bacterias.
---
### 5. Consideraciones de diseño
- **Carga metabólica**: Un circuito genético puede afectar negativamente el desarrollo del organismo o ser eliminado por evolución.
- Existen **sistemas o partes complejas predefinidas** (iGem, Biobricks, SynBioHub) que pueden integrarse directamente a los circuitos, evitando el diseño desde cero.
---
### 6. Circuitos complejos
Para diseñar circuitos más complejos, existen varias estrategias:
1. **Diseño directo**: Añadir el circuito al organismo, aunque es arriesgado debido a problemas metabólicos y evolutivos.
2. **Vinculación a un proceso vital**: Asociar el circuito a procesos esenciales del organismo (ej., metabolismo del ATP).
3. **Alojamiento en un chassis mínimo**: Usar organismos con la mínima organización genética necesaria para soportar el circuito.
4. **Comunicación celular**: Dividir tareas complejas entre organismos (consorcios), repartiendo la carga computacional.
---
### 7. Próxima clase
- Se abordará la **comunicación intercelular** y cómo aprovecharla para coordinar poblaciones de células en la realización de tareas complejas.
