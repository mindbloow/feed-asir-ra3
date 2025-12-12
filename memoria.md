# Memoria de la Actividad – Generación de Canales RSS/Atom (RA3)

## Grupo X: *Noticias Actualidad*

**Integrantes del grupo:**
- **Enrique** – Rol: Desarrollador del feed RSS  
- **Pablo** – Rol: Desarrollador del feed Atom  
- **Javi** – Rol: Coordinación y Pruebas con Agregador  

---

## 1. Descripción del Proyecto

El proyecto consiste en la creación de dos canales de sindicación de contenido: uno en **RSS 2.0** y otro en **Atom 1.0**. El grupo seleccionó **tres noticias reales de actualidad** para alimentar ambos feeds:

1. **EL PAÍS amplía su liderazgo en la prensa generalista.**
2. **Sánchez defiende la sanidad pública frente a privatizaciones.**
3. **Luis Tosar critica el negacionismo franquista en redes sociales.**

Cada miembro del equipo asumió un rol: Enrique desarrolló el archivo RSS, Pablo creó el Atom y Javi comprobó la coherencia entre ambos, además de realizar las pruebas en un agregador de noticias.

---

## 2. Desarrollo del Trabajo

---

### 2.1 Rol RSS – Enrique Ros

**Tareas realizadas:**

Para crear el archivo `feed_rss.xml`, utilicé la estructura de RSS 2.0 con el elemento raíz `<rss>` y el elemento `<channel>`. Añadí los campos obligatorios y recomendados:
- `<title>`  
- `<link>`  
- `<description>`  
- `<language>`  
- `<lastBuildDate>`  
- `<pubDate>`  

Después incorporé las tres noticias dentro de elementos `<item>` con los campos:
- `<title>`
- `<link>`
- `<description>`
- `<pubDate>` (formato RFC 822)
- `<guid>`

```xml
<item>
  <title>EL PAÍS amplía su liderazgo en la prensa generalista</title>
  <link>https://elpais.com/comunicacion/2025-12-12/el-pais-amplia-liderazgo</link>
  <description>EL PAÍS incrementa su número de lectores un 14,8 % en 2025, consolidándose como el diario líder en España.</description>
  <pubDate>Fri, 12 Dec 2025 08:00:00 +0000</pubDate>
  <guid>https://elpais.com/comunicacion/2025-12-12/el-pais-amplia-liderazgo</guid>
</item>
```

**Validación del RSS:**

El archivo se validó con W3C Feed Validator, comprobando sintaxis XML, estructura RSS y fechas. El feed es totalmente válido.

**Reflexión individual:**

Crear el RSS fue sencillo gracias a su estructura clara. El aspecto más delicado fue el formato de fechas RFC 822, ya que los validadores son estrictos.

---

### 2.2 Rol Atom – Pablo

**Tareas realizadas:**

Para crear el archivo `feed_atom.xml` utilicé la estructura estándar de Atom 1.0 con el elemento principal `<feed>` del namespace Atom. Cada noticia se añadió como `<entry>` con sus campos obligatorios:
- `<title>`
- `<link>`
- `<id>`
- `<updated>` (ISO 8601)
- `<summary>`

```xml
<entry>
  <title>Sánchez defiende la sanidad pública frente a privatizaciones</title>
  <link href="https://elpais.com/espana/2025-12-06/sanchez-sanidad-publica" />
  <id>https://elpais.com/espana/2025-12-06/sanchez-sanidad-publica</id>
  <updated>2025-12-06T12:00:00Z</updated>
  <summary>El presidente del Gobierno destaca la importancia de la sanidad pública frente a propuestas de privatización.</summary>
</entry>
```

**Validación del Atom:**

El archivo se validó correctamente en un validador compatible. No hubo errores; Atom es más estricto que RSS, pero su estructura es clara.

**Reflexión individual:**

El formato Atom me pareció más moderno y organizado que RSS. Las fechas ISO 8601 son más intuitivas. También valoro que Atom sea más flexible con la información interna.

---

### 2.3 Rol Coordinador/Agregador – Javi

**Tareas realizadas:**

Me encargué de coordinar que ambos feeds usaran las mismas noticias y que los enlaces y fechas fueran coherentes. Publiqué los archivos en **GitHub Pages** para obtener una URL accesible y realicé las pruebas con el agregador **Feedly**.

**Pruebas en agregador:**

- Feed RSS reconocido correctamente, mostrando los tres titulares y sus descripciones.  
- Feed Atom también reconocido sin errores.  
- Ambos feeds mostraron las fechas, títulos y enlaces de forma correcta.  
- No se observaron diferencias relevantes en la presentación dentro de Feedly.

**Reflexión individual:**

Los agregadores facilitan el consumo de noticias desde múltiples fuentes. Comprobar los feeds en un entorno real ayudó a ver que RSS y Atom se comportan de manera casi idéntica desde el punto de vista del usuario.

---

## 3. Conclusión del Grupo

El proyecto nos permitió aprender a generar contenido estructurado para RSS y Atom, entendiendo sus diferencias y similitudes. Valoramos el uso de agregadores como herramienta para centralizar información y la importancia de que los feeds estén bien formados para evitar errores de lectura.

---

## 4. Evidencias

- **validacion_rss.png** – Captura del feed RSS validado correctamente.
- **validacion_atom.png** – Captura del feed Atom validado correctamente.
- **agregador_rss.png** – Visualización del feed RSS en el agregador.
- **agregador_atom.png** – Visualización del feed Atom en el agregador.

---

## 5. Entrega

- Fichero .md de documentación completado
- Ficheros XML RSS y Atom
- Carpeta con imágenes de evidencias
- Todo entregado en un archivo ZIP

