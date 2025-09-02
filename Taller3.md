# 🚀 Taller de React Native — Comunicación Padre ↔ Hijo (Lista de estudiantes)

https://reactnative.dev/

Este taller tiene como objetivo practicar la **comunicación entre componentes** creando un **componente hijo** que lista estudiantes y un **componente padre** que contiene la data y coordina las acciones. Se trabajará el flujo **padre → hijo** (props) y **hijo → padre** (callbacks) para **seleccionar/deseleccionar** estudiantes y mantener una lista de **“correos por enviar”**.

---

## 📚 Taller Parte 1: Componentes (definición de Padre e Hijo)

En esta parte creamos los componentes base y definimos sus props/callbacks sin lógica compleja.

---

### 1. ListaEstudiantes (Hijo)
- **Razón**: Mostrar una lista reutilizable que recibe datos y comunica interacciones al padre.
- **Se usa cuando**: La pantalla padre necesita renderizar varios ítems y reaccionar a sus eventos.
- **Puntos**:
  - Crear `ListaEstudiantes({ data, seleccionados, onToggleSelect })`.
  - `data`: arreglo de objetos `{ id, nombre, correo }`.
  - `seleccionados`: arreglo de `id` actualmente seleccionados (controlado por el padre).
  - `onToggleSelect(id)`: callback que el hijo dispara al tocar un estudiante.
  - Renderizar cada estudiante mostrando **nombre** y **correo**.
  - **Resaltar visualmente** (sin estilos avanzados) si el `id` está en `seleccionados` (p. ej., añadir un texto “(seleccionado)”).

---

### 2. PantallaPadre (Padre)
- **Razón**: Fuente de la verdad; mantiene el estado y pasa props/callbacks al hijo.
- **Se usa cuando**: Debes coordinar data, selección y acciones globales (p. ej., enviar correo).
- **Puntos**:
  - Definir `const [estudiantes, setEstudiantes] = useState([...])` con `{ id, nombre, correo }`.
  - Definir `const [seleccionados, setSeleccionados] = useState([])` (ids).
  - Pasar al hijo: `data={estudiantes}`, `seleccionados={seleccionados}`, `onToggleSelect={handleToggle}`.
  - Incluir un botón en el **padre** llamado **“Enviar correo”** (sin enviar realmente), que por ahora **no** implementa lógica de red.

---

### 📋 Ejemplo de data de estudiantes

```js
const estudiantesEjemplo = [
  { id: "1", nombre: "Ana García", correo: "ana.garcia@correo.com" },
  { id: "2", nombre: "Luis Zuluaga", correo: "luis.zuluaga@correo.com" },
  { id: "3", nombre: "María Pérez", correo: "maria.perez@correo.com" },
  { id: "4", nombre: "Carlos Gómez", correo: "carlos.gomez@correo.com" },
  { id: "5", nombre: "Sofía Ramírez", correo: "sofia.ramirez@correo.com" },
];
