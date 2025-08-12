# 🚀 Taller introductorio de React Native — Componentes

https://reactnative.dev/

Este taller tiene como objetivo practicar los **componentes básicos sin estado** (sin `useState`), empezando por los que **no requieren acciones**, y cerrar con **botones** que disparan `Alert`. Además, se ejercitan **funciones que retornan componentes**.

---

## 📚 Taller Parte 1: Componentes sin acciones

En esta parte practicamos los componentes base para estructurar interfaces sin lógica de estado.

---

### 1. View
- **Razón**: Contenedor base; organiza estructura y layout.
- **Se usa cuando**: Agrupar elementos, crear filas/columnas, espaciar con `padding`/`margin`.
- **Puntos**:
  - Crear un `View` raíz con `padding` y fondo claro; separar **encabezado** y **contenido** con márgenes consistentes.
  - Practicar `flexDirection` (columna/fila) y alineación para ordenar bloques.

---

### 2. Text
- **Razón**: Todo texto visible (títulos, subtítulos, párrafos) vive en `Text`.
- **Se usa cuando**: Definir jerarquía tipográfica y rótulos.
- **Puntos**:
  - Agregar **título** (tamaño mayor, negrita) y **subtítulo** (tamaño medio) con espaciado vertical.
  - Añadir un párrafo corto y verificar legibilidad (contraste, tamaño, interlineado).

---

### 3. Image
- **Razón**: Muestra contenido visual; requiere **tamaño definido** para render correcto.
- **Se usa cuando**: Portada, avatar o miniatura.
- **Puntos**:
  - Usar imagen **remota** con `width`/`height` explícitos y `resizeMode` apropiado.
  - Incluir `accessibilityLabel` descriptivo para accesibilidad.

---

### 4. Lista — FlatList
- **Razón**: Renderiza listas de forma **eficiente** y consolida el patrón de funciones que **retornan componentes**.
- **Se usa cuando**: Hay varios ítems (≥ 5) o la lista puede crecer.
- **Puntos**:
  - Definir `data` con al menos 5 elementos (`{ id, title }`) y crear `renderItem` **como función clásica** que retorne `View + Text`.
  - Implementar `ItemSeparatorComponent` (una `View` delgada) y `ListHeaderComponent` con un `Text` de sección.

---

## 🏹 Intermedio: Arrow function

- **Razón**: Sintaxis concisa para callbacks en eventos (sin manejar estado).
- **Puntos**:
  - Usar `const fn = () => { /* ... */ }` para acciones simples como `Alert`.
  - Aplicar en botones después de comprender la sintaxis.

---

## 🔘 Taller Parte 2: Botones con `Alert` — dos variantes

---

### 5. Botón con función flecha inline
- **Razón**: Definir la acción directamente donde ocurre el evento (`onPress`).
- **Puntos**:
  - Agregar un botón con función flecha **inline** que dispare un `Alert`.
  - Verificar que el mensaje se muestre al tocar.

---

### 6. Botón con función flecha definida previamente
- **Razón**: Reutilizar la misma acción en varios lugares y mantener el código limpio.
- **Puntos**:
  - Declarar la función flecha antes del render y referenciar esa función en `onPress`.
  - Comprobar que el comportamiento sea equivalente al inline.

---

## 🧠 Ejercicios de comprensión para sustentar

---

### Caso A: Portada de catálogo
- **Situación**: Portada con título, subtítulo, una imagen destacada y una lista de 6 ítems con separadores.
- **Puntos**:
  - Elegir y **justificar** los componentes para cada parte (usar solo `View`, `Text`, `Image`, `FlatList`).
  - Implementar la estructura en Snack sin estado.

---

### Caso B: Perfil simple
- **Situación**: Avatar, nombre, bio y un botón “Contacto”.
- **Puntos**:
  - Definir y **justificar** los componentes y la jerarquía tipográfica.
  - Implementar el botón “Contacto” con `Alert` (elegir variante inline o definida).

---

### Caso C: Lista de titulares
- **Situación**: Encabezado “Hoy” y 5 titulares cortos con separadores sutiles.
- **Puntos**:
  - Decidir si usas `FlatList` o no y **justificar** la elección.
  - Implementar `ListHeaderComponent` y un separador reutilizable.

---
