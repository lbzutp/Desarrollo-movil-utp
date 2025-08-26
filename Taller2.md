# ⚡️ Taller de React Native — Props y useState

https://reactnative.dev/

Este taller tiene como objetivo practicar el uso de **props** (datos que recibe un componente) y **estado local con `useState`**. Empezamos con componentes **puros** que solo leen props, y luego añadimos **interacciones** que modifican el estado. Al final se incluyen **ejercicios opcionales sobre listas** con sustento.

---

## 📚 Taller Parte 1: Componentes con props

En esta parte practicamos componentes que **reciben datos** y **renderizan** sin estado interno.

---

### 1. TitleBlock (props básicos)
- **Razón**: Aislar tipografía para reuso.
- **Se usa cuando**: Necesitas mostrar `title` y `subtitle`.
- **Puntos**:
  - Crear `TitleBlock({ title, subtitle })` que renderice dos `Text`.
  - Usar **desestructuración** en la firma del componente.
  - Añadir un prop opcional `align` (`'left' | 'center'`) y condicionar la alineación.

---

### 2. Card (props + children)
- **Razón**: Composición flexible; el padre decide qué va dentro.
- **Se usa cuando**: Quieres un contenedor con contenido variable.
- **Puntos**:
  - Crear `Card({ children })` que retorne un `View`.
  - Usar la `Card` para envolver `TitleBlock` u otros elementos.
  - Añadir prop `highlighted` (boolean) y mostrar un texto adicional si está activo.

---

### 3. PrimaryButton (props de evento)
- **Razón**: Separar la **UI** de la **lógica**.
- **Se usa cuando**: Un mismo botón dispara acciones distintas en contextos distintos.
- **Puntos**:
  - Crear `PrimaryButton({ label, onPress })` y usarlo en pantalla.
  - Comprobar que pasa funciones **distintas** al mismo componente.

---

### 4. Render condicional con imageUrl
- **Razón**: Un componente robusto no asume siempre la misma data.
- **Se usa cuando**: Un prop puede venir vacío.
- **Puntos**:
  - En una `Card`, mostrar `Image` **solo si** llega `imageUrl`.
  - Añadir `accessibilityLabel` descriptivo.

---

## 🏹 Intermedio: Buenas prácticas con props

- **Razón**: Mantener los componentes claros y fáciles de reutilizar.
- **Puntos**:
  - **Desestructurar** props en la definición del componente.
  - Establecer **valores por defecto** vía parámetros.
  - Usar props para variantes en lugar de múltiples componentes duplicados.

---

## 🔘 Taller Parte 2: Interacciones con useState

Ahora los componentes **guardan estado** y reaccionan a eventos.

---

### 5. Counter
- **Razón**: Ejemplo mínimo de estado numérico.
- **Se usa cuando**: Necesitas incrementar/decrementar valores.
- **Puntos**:
  - `const [count, setCount] = useState(0)`.
  - Renderizar el valor y un botón `+1`.
  - Añadir un botón `Reset`.

---

### 6. PreferenceToggle
- **Razón**: Estado booleano y UI condicional.
- **Se usa cuando**: Activas/desactivas una opción.
- **Puntos**:
  - `const [enabled, setEnabled] = useState(false)`.
  - Mostrar un `Text` que diga “Activo/Inactivo”.
  - Alternar el estado con un botón o `Pressable`.

---

### 7. ControlledInput
- **Razón**: Formularios y sincronía entre UI ↔ estado.
- **Se usa cuando**: Necesitas leer/modificar texto del usuario.
- **Puntos**:
  - `const [name, setName] = useState('')`.
  - Usar `TextInput` con `value={name}` y `onChangeText={setName}`.
  - Mostrar saludo dinámico: “Hola, {name || 'visitante'}”.

---

### 8. ProfileCard (props + useState)
- **Razón**: Integrar piezas previas en un caso realista.
- **Se usa cuando**: Un contenedor incluye interacciones internas.
- **Puntos**:
  - Usar `Card` + `TitleBlock` + `PrimaryButton`.
  - Estado local `liked` (boolean) que cambie el texto del botón entre “Like”/“Unlike”.

---

## 🧠 Ejercicios de comprensión para sustentar

---

### Caso A: Like en una Card
- **Situación**: Imagen (opcional), título y botón “Like”.
- **Puntos**:
  - ¿Qué datos viajan como **props** y cuál es el **estado**?
  - ¿Por qué el estado (`liked`) vive en la `Card` y no en el botón?

---

### Caso B: Saludo personalizado
- **Situación**: `TextInput` + `Text` que responde al escribir.
- **Puntos**:
  - Explica por qué el `TextInput` debe ser **controlado**.
  - ¿Dónde validas el mínimo de caracteres y por qué?

---

### Caso C: Preferencias rápidas
- **Situación**: Varios toggles (ej. sonido, vibración, tema).
- **Puntos**:
  - ¿Usas **un estado por toggle** o **un objeto de estado**? Justifica.
  - Si creas un `ToggleRow({ label, value, onChange })`, ¿qué gana tu arquitectura?

---

## 📜 Opcionales sobre listas (con useState)

Estos puntos son **opcionales** y deben ir acompañados de una breve **justificación**.

---

### O1. Lista de tareas mínima
- **Situación**: Lista de strings con opción de agregar y eliminar.
- **Puntos**:
  - `const [tasks, setTasks] = useState([{id:'1', title:'Aprender props'}])`.
  - Agregar tarea con un `TextInput` y botón “Agregar”.
  - Eliminar tarea con un botón “X”.
  - **Sustenta**: ¿`FlatList` vs `.map()`? ¿Por qué `keyExtractor`?

---

### O2. Filtro por texto
- **Situación**: Campo de búsqueda para filtrar resultados.
- **Puntos**:
  - Campo “Buscar” que filtra `tasks` por `title`.
  - Mantener el arreglo original, filtrar en el render.
  - **Sustenta**: ¿Dónde conviene guardar el término de búsqueda?

---

### O3. Contadores independientes en una lista
- **Situación**: Cada ítem tiene su propio contador.
- **Puntos**:
  - Cada ítem tiene su propio `count`.
  - Actualizar con `map` de forma inmutable.
  - **Sustenta**: ¿Por qué evitar mutaciones directas?
