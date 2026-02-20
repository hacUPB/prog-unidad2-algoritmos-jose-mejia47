# EJERCICIO

## 1. ¿Por qué es necesario que las computadoras representen los datos en binario?

Las computadoras utilizan el sistema binario porque internamente funcionan con componentes electrónicos (transistores) que solo pueden tener dos estados físicos estables: encendido o apagado. Estos dos estados se representan como 1 y 0.

El sistema binario es ideal porque:
- Es más confiable para los circuitos electrónicos.
- Reduce errores al interpretar señales eléctricas.
- Permite representar cualquier tipo de dato (números, texto, imágenes, audio) combinando únicamente 0 y 1.

En resumen, las computadoras usan binario porque su hardware está diseñado para trabajar con dos niveles de energía, lo que hace que el sistema sea más estable y eficiente.

---

## 2. Conversión del número binario 10011011

### a) Conversión a decimal

Número binario: 10011011₂

Se multiplica cada bit por su potencia correspondiente de 2:

1×2⁷ + 0×2⁶ + 0×2⁵ + 1×2⁴ + 1×2³ + 0×2² + 1×2¹ + 1×2⁰

= 128 + 0 + 0 + 16 + 8 + 0 + 2 + 1  
= 155

Resultado en decimal:
10011011₂ = 155₁₀

---

### b) Conversión a hexadecimal

Se agrupa en bloques de 4 bits:

1001 1011

1001 = 9  
1011 = B  

Resultado en hexadecimal:
10011011₂ = 9B₁₆

---

## 3. ¿Cómo se representa una imagen en formato PNG en el disco?

Una imagen PNG (Portable Network Graphics) se almacena como una secuencia de bytes organizados en una estructura específica.

Características principales:

- Está compuesta por bloques llamados chunks.
- Cada chunk contiene información específica (cabecera, datos de imagen, etc).
- Usa compresión sin pérdida.

Estructura básica de un archivo PNG:

1. Firma del archivo (8 bytes iniciales que identifican que es PNG).
2. Chunk IHDR (información básica: ancho, alto, profundidad de color).
3. Chunk IDAT (datos de la imagen comprimidos).
4. Chunk IEND (marca el final del archivo).

Cada píxel se representa numéricamente (por ejemplo, en RGB: rojo, verde y azul, cada uno normalmente usando 1 byte).

En el disco, todo esto está almacenado en binario como una secuencia organizada de bytes.

---

## 4. ¿Qué sucede si intentas almacenar un número mayor al que puede representar un byte (por ejemplo, 300)? ¿Cómo lo maneja Python?

Un byte puede representar valores entre 0 y 255 (8 bits).

Si intentamos almacenar el número 300 en un solo byte:

300 > 255

En sistemas que usan tamaño fijo de byte:
- Ocurre un desbordamiento (overflow).
- El valor se ajusta usando módulo 256.
- 300 mod 256 = 44

Entonces realmente se almacenaría el valor 44.

En Python:

Python no limita los enteros a 1 byte. Los enteros en Python pueden crecer dinámicamente en tamaño según sea necesario. Por ejemplo:

300

es perfectamente válido y no produce error.

Sin embargo, si intentamos forzar el uso de un byte, por ejemplo:

bytes([300])

Python generará un error:

ValueError: bytes must be in range(0, 256)

Esto ocurre porque el tipo bytes sí está limitado al rango de un byte.

En conclusión:
- En hardware de tamaño fijo hay overflow.
- En Python, los enteros crecen dinámicamente.
- Solo ocurre error si se fuerza el almacenamiento en un solo byte.