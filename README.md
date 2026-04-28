# 2526CL12_Bomba_Montaje_Fisico_v1

Caracterización de Bomba para sistema de riego y Montaje fisico v1.

Indice evolutivo del las clases del taller + libros y webs de referencia:

[GitHub - Jcspoza/2526_PyR_Index: Curso Programación y Robotica 2025 2026 - CMM BML](https://github.com/Jcspoza/2526_PyR_Index)

---

## Proyecto completo-> en inicio de pruebas : sensor humedad suelo + bomba agua (motor)

Esta lección forma parte del los aprendizajes necesarios para caracterizar la bomba en cuanta a voltaje - amperaje y altura máxima a al que puede subir agua.

Adicionalmente se empezara a dibujar un esquema del montaje físico en una primera aproximación

## Clase12 - Indice

- 0- Resumen inicial
  
  - Tópicos que se van a aprender
  
  - Lista de materiales
  
  - Links a Tutoriales e informacion
  
  - Librerías usadas
  
  - Tabla resumen de programas

- 1- Caracterización de bomba incluida en kit SF
  
  - Prueba inicial básica
  - Pruebas de voltaje - intensidad
  - Pruebas de altura máxima a la que se eleva el agua
  - CONCLUSIONES  de caracterización

- 2-Comparación con un riego automático solar básico
  
  - --> Se nos ha olvidado un sensor de que el recipiente tiene agua

- 3-Montaje Físico - draft v1 : Bomba + Recipiente 
  
  - 3.1 Conectores a usar : jack  de audio M y H ?
  
  - 3.2 Recipiente a usar : Idea bote de detergente de 5L con tapa + serrar para meter bomba
  
  - 3.3 ¿Cómo medir nivel de agua sin añadir muchos cables?
  
  - 3.4 Montaje cables v1

---

## Resumen inicial

### Tópicos que se van a aprender / repasar

| Tópico                                 | Detalle | Links |
| -------------------------------------- | ------- | ----- |
| Parámetros de una bomba de agua básica |         |       |
| T                                      |         |       |

### Lista de Materiales

| Material                                                                                                                          | Descripcion                                                                                                                                                      | Kit SF | Montaje |
| --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------- |
| [Protoboard 700](https://docs.sunfounder.com/projects/kepler-kit/en/latest/component/component_breadboard.html)                   | Placa para prototipos ver apartado [Uso de la protoboard](https://github.com/Jcspoza/2526CL1_R_CircElect0#uso-de-la-protoboard). Mejor usar la protoboard de 700 | SI     | Todos   |
| [Cables dupond M-M](https://docs.sunfounder.com/projects/kepler-kit/en/latest/component/component_wire.html)                      | Sirven para hacer conexiones en protoboard                                                                                                                       | SI     | Todos   |
| Pico _, 2, W, 2W                                                                                                                  | Vale cualquiera de los 4 modelos de Pico                                                                                                                         | SI     | Todos   |
| [Bomba tipo acuario corriente continua](https://docs.sunfounder.com/projects/pico-2w-kit/en/latest/component/component_pump.html) | Es básicamente un motor de 5 volt                                                                                                                                | SI     |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |
|                                                                                                                                   |                                                                                                                                                                  |        |         |

### Links a informacion

| Tema | Link |
| ---- | ---- |
|      |      |
|      |      |

### Librerías usadas - No se usan librerias

### Tabla resumen de programas

Todos los programas en microPython

| Programa | Montaje | HW si Robotica y Notas | Objetivo de Aprendizaje |
| -------- | ------- | ---------------------- | ----------------------- |
|          |         |                        |                         |
|          |         |                        |                         |
|          |         |                        |                         |
|          |         |                        |                         |
|          |         |                        |                         |
|          |         |                        |                         |
|          |         |                        |                         |

---

## 1- Caracterización de bomba incluida en kit SF

### Introducción

La bomba de acuario incluida en el kit tiene las siguientes características

**Características**

- **Rango de voltaje** : CC 3 ~ 4,5 V

- **Corriente de funcionamiento** : 120 ~ 180 mA

- **Potencia** : 0,36 ~ 0,91 W

- **Altura máxima de elevación del agua** : 0,35 ~ 0,55 m

- **Caudal máximo** : 80 ~ 100 L/h

- **Vida laboral continua** : 100 horas

- **Grado de protección contra el agua** : IP68

- **Modo de funcionamiento** : CC, accionamiento magnético

- **Material** : Plástico de ingeniería

- **Diámetro exterior de la salida** : 7,8 mm

- **Diámetro interior de la salida** : 6,5 mm

- Es una bomba sumergible y debe usarse como tal. Tiende a calentarse demasiado, por lo que existe riesgo de sobrecalentamiento si se enciende sin estar sumergida.

- Invertir la polaridad no la convertirá en una bomba de entrada; seguirá bombeando agua hacia afuera.

- Incluye un cable macho de 25 cm, lo que permite una fácil inserción en una placa de prototipos.

Comentarios : 

1. Deberia poder funcionar a 5volt y asi aprovechar la potencia al máximo -> caracterizar

2. Hay que medir el amperaje de funcionamiento porque eso puede determinar el montaje electrónico a realizar --> caracterizar

3. Indica la salida en litros / hora , pero no la altura máxima a la que puede elevar el agua --> Caracterizar

4. No podemso dejar la bomba funcionando sin agua => nuevo requisito

#### Pruebas iniciales con bomba aliexpres

Por adelantar y probar yo primero, he usado una bomba que puede ser ligeramente distinta comprada en aliexpres.

[Bomba 3 a 5 volt - vertical](https://es.aliexpress.com/item/1005007416493842.html?spm=a2g0o.order_list.order_list_main.163.3dbf194dJ7FKho&gatewayAdapt=glo2esp) Con caracteriticas muy similares

**Especificación:**  
Origen: China continental  
Estructura: Bomba Sumergible  
Potencia: Eléctrica  
Combustible: Eléctrico  
Uso: Agua  
Estándar o No estándar: Estándar  
Número de modelo: Bomba de agua sumergible  
Voltaje: 3-4.5V  
Corriente: 0,12-0,18 A.  
Potencia: 0,36-0,91W  
Cabeza: 0,35-0,55 M  
Flujo: 80-100 (L/H)  
Tensión inicial: 1  
Grado de impermeabilidad: IP68

### Pruebas de voltaje - intensidad

En los dos siguientes videos se puede ver el funcionamiento ( sin tubo) a 3.3 volt y a 5.0 volt, usando una fuente de voltaje variable con limite de corriente

[Bomba de acuario para sistema de riego con PICO W - 3 3v - YouTube](https://youtu.be/X_0jZWPfRAw)

[Bomba de acuario para sistema de riego con PICO W - 5.0 volt - YouTube](https://youtu.be/DHgVienK9Sk)

o este otro video corto a 5 volt

https://github.com/user-attachments/assets/a39b6d37-9748-4f1c-8fe4-40d5a9bb93c6

#### Caracterización de voltaje - amperios - bomba Aliexpres

| Voltaje  | Amperios | Funcionamiento |
| -------- | -------- | -------------- |
| 3.3 volt | 263 mA   |                |
| 5.0 volt | 428 mA   |                |

### Pruebas de altura máxima a la que se eleva el agua

Video de configuración del montaje

[Bomba de acuario para sistema de riego con PICO W- Montaje para ver altura maxima - YouTube](https://youtube.com/shorts/1d3WkyyNLxg?feature=share)

Foto de altura máxima a al que el agua ya no circula = 118 cm

| ![](./montaje_altura_det2.jpg) | ![](./altura_limite2.jpg) |
| ------------------------------ | ------------------------- |

### CONCLUSIONES de caracterización

1- A 5voltios el consumo es de 428 mA muy por debajo de la corriente máxima que aguanta un transistor BJC NPN S8050 ==> **no hay que usar el integrado del kit mejor el Transistor S8050**

2- Las **macetas a regar han de estar a menos de 100 cms de altura respecto a la bomba**

---

## 2-Comparación con un riego automático solar básico

[Temporizador de riego con mini tuberías y potencia solar](https://vm.tiktok.com/ZNRbtEhAG/)

- --> Se nos ha olvidado un sensor de que el recipiente tiene agua

---

## 3-Montaje Físico - draft v1 : Bomba + Recipiente

### 3.1 Conectores a usar : jack de audio M y H ?

Tanto el motor con 2 cables como la sonda sensor de suelo con 3 cables, han de tener un conector tipo un enchufe macho a hembra para facilitar el montaje. He probado a usar conectores de audio tipo jack de 3.5 de 2 polos y 3 polos, que son baratos en la tienda de barquillo 15 : 0,70 eur por conector. (el mas barato) 

**VA OK**

### 3.2 Recipiente a usar :

**Idea bote de detergente de 5L con tapa + serrar para meter bomba** ver foto

Criterios:

* Recipiente de **plástico** -> robusto + evitar filtraciones + facil de cortar y adaptar +,no conductor

* **base ancha**

* que **se pueda cerrar** con un tapón o similar para evitar que el agua estanca da se llene de mosquitos 

--> un bidón de agua mineral de los de 5 a 8 litros estaría OK

--> Yo he usado un bote de detergente liquido de 5L

### 3.3 ¿Cómo medir nivel de agua sin añadir muchos cables?

He probado con un sensor de humedad de suelo del tipo antiguo en 2 piezas 

( añadir foto y referencia)

* Funciona a 3,3 volt

* Tiene una señal digital que se activa si las 2 puntas estan sumergidas en agua

* Consume unos 3 mA ==> se puede alimentar por GPIO al mismo tiempo que el sensor de humedad de suelo y con el mismo GPIO

**Todo esto quiere decir que solo necesitamos un cable ADICIONAL para la señal digital de SIN AGUA**

### 3.4 Montaje cables v1

Vamos a necesitar 6 cables

| Lado PICO    | Lado deposito + maceta                         |
| ------------ | ---------------------------------------------- |
| GND          | GND sensor Hum Suelo + GND sensor hay Agua     |
| GPIO21       | VCC sensor Hum suelo y VCC sensor hay agua     |
| ADC0         | Señal sensor Hum suelo                         |
| GPIO22       | DO digital output sensor hay Agua - Low activo |
| +5 volt      | Motor 1-bomba agua                             |
| Colector NPN | Motor 2 -bomba agua                            |
