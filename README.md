🚀 Taller introductorio de React Native — Componentes
Objetivo: Practicar componentes básicos sin estado (no usar useState), empezar por los que no requieren acciones y cerrar con botones que disparan Alert. Además, ejercitar funciones que retornan componentes.

📚 Parte 1: Componentes sin acciones
1. View
Razón: Es el contenedor base; organiza estructura y layout.
Se usa cuando: Necesitas agrupar elementos, crear filas/columnas y espaciar con padding/margin.
Puntos:

Crea un View raíz con padding y fondo claro; separa encabezado y contenido con márgenes consistentes.

Practica flexDirection (columna/fila) y alineación básica para ordenar bloques.

2. Text
Razón: Todo texto visible (títulos, subtítulos, párrafos) vive dentro de Text.
Se usa cuando: Defines jerarquía tipográfica y rótulos.
Puntos:

Agrega un título (tamaño mayor, negrita) y un subtítulo (tamaño medio) con espaciado vertical.

Añade un párrafo corto y verifica legibilidad (contraste, tamaño, interlineado).

3. Image
Razón: Muestra contenido visual; requiere tamaño definido para un render correcto.
Se usa cuando: Necesitas portada, avatar o miniatura.
Puntos:

Muestra una imagen remota con width/height explícitos y resizeMode adecuado.

Incluye accessibilityLabel descriptivo para mejorar accesibilidad.

4. Lista — FlatList
Razón: Renderiza listas de forma eficiente y consolida el patrón de funciones que retornan componentes.
Se usa cuando: Hay varios ítems (≥ 5) o la lista puede crecer.
Puntos:

Define data con al menos 5 elementos ({ id, title }) y crea renderItem como función clásica que retorne View + Text.

Implementa ItemSeparatorComponent (una View delgada) y ListHeaderComponent con un Text de sección.

🏹 Intermedio: Arrow function
Razón: Sintaxis concisa para callbacks en eventos (sin manejar estado).
Puntos:

Usar const fn = () => { /* ... */ } para acciones simples como Alert.

Aplicar en botones luego de comprender la sintaxis.

🔘 Parte 2: Botones con Alert — dos variantes
5. Botón con función flecha inline
Razón: Definir la acción directamente donde ocurre el evento (onPress).
Puntos:

Agrega un botón con función flecha inline que dispare un Alert.

Verifica que el mensaje se muestre al tocar.

6. Botón con función flecha definida previamente
Razón: Reutilizar la misma acción en varios lugares y mantener el código limpio.
Puntos:

Declara la función flecha antes del render y referencia esa función en onPress.

Comprueba que el comportamiento sea equivalente al inline.

🧠 Ejercicios de comprensión para sustentar
Caso A: Portada de catálogo
Situación: Portada con título, subtítulo, una imagen destacada y una lista de 6 ítems con separadores.
Puntos:

Elige y justifica los componentes para cada parte (usa solo View, Text, Image, FlatList).

Implementa la estructura en Snack sin estado.

Caso B: Perfil simple
Situación: Avatar, nombre, bio y un botón “Contacto”.
Puntos:

Define y justifica los componentes y la jerarquía tipográfica.

Implementa el botón “Contacto” con Alert (elige variante inline o definida).

Caso C: Lista de titulares
Situación: Encabezado “Hoy” y 5 titulares cortos con separadores sutiles.
Puntos:

Decide si usas FlatList o no y justifica tu elección.

Implementa ListHeaderComponent y un separador reutilizable.
