# Proyecto de Modelado UML – Traza2

Este proyecto continúa con la misma lógica que el **proyecto Traza1**, pero en lugar de modelar artículos e insumos de un sistema de comidas rápidas, aquí se aborda la **estructura empresarial y geográfica** de las sucursales de una empresa.  

La idea es aplicar los mismos principios de **encapsulación, colecciones HashSet, relaciones UML y operaciones CRUD**, pero en un dominio distinto.

---

##  Clases del Modelo

### 1. `Pais`
- Atributos: `nombre`
- Relación: Un país contiene varias provincias.

### 2. `Provincia`
- Atributos: `nombre`
- Relación: pertenece a un `Pais` y contiene varias `Localidades`.

### 3. `Localidad`
- Atributos: `nombre`
- Relación: pertenece a una `Provincia` y contiene varios `Domicilios`.

### 4. `Domicilio`
- Atributos: `calle`, `numero`, `cp`
- Relación: pertenece a una `Localidad`.

### 5. `Sucursal`
- Atributos: `nombre`, `horaApertura`, `horaCierre`, `esCasaMatriz`
- Relación: cada sucursal tiene **un único domicilio**.

### 6. `Empresa`
- Atributos: `nombre`, `razonSocial`, `cuit`, `logo`
- Relación: una empresa tiene una o varias sucursales.

---

## Relación con el Proyecto **Traza1**

- En **Traza1** trabajamos con el **núcleo del negocio**: los artículos que una empresa de comidas rápidas vende (insumos, manufacturados, categorías, unidades de medida, imágenes).
- En **Traza2** se modela la **estructura organizacional y geográfica**: cómo se organizan las empresas, sus sucursales y domicilios.

Ambos proyectos se complementan:  
- **Traza1** representa **qué vende la empresa**.  
- **Traza2** representa **dónde y cómo opera la empresa**.  

Esto permite que en un futuro ambos modelos se puedan integrar en un único sistema de gestión.

---

## Lógica Implementada en `Main`

El programa sigue la siguiente secuencia:

1. Crear el país **Argentina**.
2. Crear provincias: **Buenos Aires** y **Córdoba**, asociadas a Argentina.
3. Crear localidades para cada provincia:
   - Buenos Aires → `CABA`, `La Plata`
   - Córdoba → `Córdoba Capital`, `Villa Carlos Paz`
4. Crear domicilios en cada localidad.
5. Crear sucursales y asociarlas con los domicilios:
   - `Sucursal1` → CABA
   - `Sucursal2` → La Plata
   - `Sucursal3` → Córdoba Capital
   - `Sucursal4` → Villa Carlos Paz
6. Crear empresas y asociarlas con sucursales:
   - `Empresa1` → sucursales 1 y 2
   - `Empresa2` → sucursales 3 y 4

---

## Funcionalidades CRUD

El sistema permite:

- **Mostrar todas las empresas.**
- **Buscar empresa por ID.**
- **Buscar empresa por nombre.**
- **Actualizar datos de una empresa (ej: CUIT) buscando por ID.**
- **Eliminar empresa por ID.**

---

## Conclusión

Este ejercicio fortalece los mismos conceptos de POO practicados en **Traza1**, pero aplicados a un dominio distinto (estructura empresarial y geográfica).  

De esta forma:
- **Traza1** modela el **negocio (productos)**.  
- **Traza2** modela la **organización (empresas y sucursales)**.  

Ambos proyectos juntos forman la base de un sistema integral para gestionar tanto **qué se vende** como **dónde se vende**.
