# **Clase Programación Móvil**  
📅 **Fecha:** 25/02/2025  

## **1. Actividades**  
- 📌 Revisión de tableros en Trello.  
- 📌 Resolución de dudas sobre los tableros.  

---

## **2. Conceptos Claves**  

### **2.1. Entendimiento de Negocio en un Proyecto**  
**📌 Semana 4 - Revisión de Historias de Usuario**  

### **Resumen de la Semana**  
- Se revisaron las **Historias de Usuario (HU)** y su estructura base.  
- Se trabajó en un **ejercicio práctico**: creación de un mockup de una HU.  
- Se introdujo la herramienta **Figma** para el diseño de mockups.  

### **Estructura Base de una Historia de Usuario**  
1. **Descripción:** Papel del usuario y sus necesidades.  
2. **Criterios de Aceptación:** Funcionalidades y validaciones para aceptar la historia.  
3. **Criterios de Finalización:** Condiciones necesarias para dar por terminada la HU.  

#### **Ejemplo:**  

**Descripción:**  
> Como administrador del sistema, quiero registrar, actualizar, eliminar y consultar categorías de productos, para gestionar eficientemente la organización de los productos dentro del sistema.  

**Criterios de Aceptación:**  
- Registro, edición, eliminación y consulta de categorías.  
- Validaciones como campos obligatorios y restricciones.  

**Criterios de Finalización:**  
- Funcionalidad desarrollada y probada.  
- Código revisado.  
- Demostración al Product Owner.  
- Documentación actualizada.  

### **Ejercicio Práctico**  
- 🔹 Creación de un mockup para la HU del **Carrito de Compras**.  
- 🔹 Diseño libre, revisado en clase.  
- 🔹 Introducción a **Figma**.  
- 🔗 **Enlace del Mockup:** [Ver en Figma](https://www.figma.com/design/NIEpjfQmtZMCts9b4FzQAp/Untitled?node-id=0-1&t=nn1rIwqPMCYFKEzU-1)  

### **Planes para la Próxima Semana**  
- 📌 Continuar trabajando con **Figma** en los mockups.  
- 📌 Vincular los mockups a las historias de usuario en **Trello**.  

---

## **3. Modelado y Diseño del Proyecto**  

### **3.1. Elementos Mínimos del Proyecto**  
- **Base de datos.**  
- **Estructura de situaciones** (entidades y relaciones).  

#### **Ejemplo de Entidad Cliente:**  
```json
{
    "cliente": {
        "nombre": "Juan",
        "apellido": "Pérez",
        "fecha_nacimiento": "1990-05-15",
        "correo": "juanperez@email.com"
    }
}
```

### **3.2. Buenas Prácticas**  
- ✔ Análisis profundo del sistema.  
- ✔ Diseño modular y estructurado.  
- ✔ Comportamiento adecuado de cada módulo.  

#### **Ejemplo de Módulos:**  
- 📦 **Inventario**  
- 🧾 **Facturación (POO)**  
- ⚙ **Parametrización**  
- 🛒 **Ventas**  
- 🔐 **Seguridad**  

---

## **4. Modelado de Datos**  

📌 **Requisitos del Modelo de Datos:**  
- ✅ Debe ser **incremental**.  
- ✅ Incluir un **diagrama de base de datos**.  
- ✅ Incluir un **diagrama de secuencias**.  

---

## **5. Arquitectura del Proyecto**  

📌 **Conceptos Claves:**  
- Ejemplo de **arquitectura limitada**: **Nequi**.  
- Los datos básicos pueden ser reutilizados para distintos roles (ej. empleado, auditor).  
- Se permite la **tercerización de procesos**.  

---

## **6. Parametrización del Sistema**  

📌 **Inserciones controladas en la base de datos**.  
📌 **Ejemplos de Parámetros:**  
- 🌍 **Idioma**  
- ⏰ **Jornadas y horarios**  
- 📅 **Agenda y reservas**  
- ⏳ **Segmentación de tiempo**  

---

## **7. Historias de Usuario (HU) y Buenas Prácticas en Scrum**  

📌 **Ejemplo de Entidad Categoría:**  
```json
{
    "Categoria": {
        "id": "auto_increment",
        "codigo": "único",
        "nombre": "único",
        "descripcion": "opcional",
        "estado": "default 1"
    }
}
```

---

## **8. Diseño y Entrega de Tareas**  

📌 **Tareas Desglosadas en Componentes:**  
- 🎨 **Mockup**  
- 🔙 **Backend**  
- 🖥 **Frontend**  
- 🗄 **Base de datos**  
- ⚙ **DevOps**  
- 📄 **Documentación**  

---

## **9. Estimación y Lista de Entrega**  

📌 **Historia de Usuario:**  

### **Descripción:**  
> Como administrador del sistema, quiero registrar, actualizar, eliminar y consultar categorías de productos, para gestionar eficientemente la organización de los productos dentro del sistema.  

### **✅ Criterios de Aceptación:**  

🔹 **Registro de Categorías:**  
- Creación de una categoría con:  
  - `id` (auto-generado).  
  - `codigo` (alfanumérico único).  
  - `nombre` (obligatorio).  
  - `descripcion` (opcional).  
  - `estado` (activo/inactivo).  

🔹 **Edición de Categorías:**  
- Permitir modificar `nombre`, `descripcion` y `estado`.  
- ❌ No modificar `id` ni `codigo` tras la creación.  

🔹 **Eliminación de Categorías:**  
- ❌ Solo eliminar si **no está asociada** a productos.  

🔹 **Consulta de Categorías:**  
- Listar todas las categorías.  
- Permitir filtro por `codigo` y `nombre`.  

### **✅ Criterios de Finalización:**  
✅ Funcionalidad implementada y probada.  
✅ Código revisado y aprobado en **Pull Request**.  
✅ Demostración al **Product Owner**.  
✅ Documentación y pruebas actualizadas.  

---
