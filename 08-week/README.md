# Explicación del Código de la Aplicación Lista de Tareas

#### Esta aplicación de lista de tareas permite a los usuarios agregar, eliminar y visualizar tareas con diferentes niveles de prioridad. Se ha desarrollado utilizando **Vue.js** y **Ionic**, lo que permite crear una interfaz de usuario interactiva y receptiva.

## Estructura del Código

### 1. Template
La parte del template está diseñada con Ionic y Vue. Incluye los siguientes elementos:

#### **a. Encabezado**
Muestra el título de la aplicación.
```html
<ion-header>
  <ion-toolbar>
    <ion-title>Lista de Tareas</ion-title>
  </ion-toolbar>
</ion-header>
```
- `<ion-header>`: Contenedor principal para la cabecera de la página.
- `<ion-toolbar>`: Componente que proporciona una barra de herramientas.
- `<ion-title>`: Muestra el título "Lista de Tareas".

#### **b. Entrada para Nueva Tarea**
Permite al usuario ingresar la descripción de una nueva tarea.
```html
<ion-item>
  <ion-label position="floating">Nueva Tarea</ion-label>
  <ion-input placeholder="Descripción de la tarea" v-model="newTask.description"></ion-input>
</ion-item>
```

#### **c. Selector de Prioridad**
Un menú desplegable para seleccionar la prioridad de la tarea (alta, media, baja).
```html
<ion-item>
  <ion-label>Prioridad</ion-label>
  <ion-select v-model="newTask.priority" placeholder="Selecciona">
    <ion-select-option value="alta">Alta</ion-select-option>
    <ion-select-option value="media">Media</ion-select-option>
    <ion-select-option value="baja">Baja</ion-select-option>
  </ion-select>
</ion-item>
```

#### **d. Checkbox para Mostrar Completadas**
Permite al usuario decidir si desea ver las tareas completadas o no.
```html
<ion-item>
  <ion-label>Mostrar Completadas</ion-label>
  <ion-checkbox v-model="showCompleted"></ion-checkbox>
</ion-item>
```

#### **e. Botón para Agregar Tarea**
```html
<ion-button expand="block" @click="addTask">Agregar Tarea</ion-button>
```

#### **f. Lista de Tareas**
Muestra las tareas filtradas según su estado de completado.
```html
<ion-list>
  <ion-item v-for="(task, index) in filteredTasks" :key="index">
    <ion-label>
      <h2>{{ task.description }}</h2>
      <p>Prioridad: {{ task.priority }}</p>
    </ion-label>
    <ion-checkbox slot="start" v-model="task.completed"></ion-checkbox>
    <ion-button slot="end" color="danger" @click="deleteTask(index)">Eliminar</ion-button>
  </ion-item>
</ion-list>
```

### 2. Script
La lógica de la aplicación se maneja en la sección del script.

#### **a. Importaciones**
```javascript
import { ref, computed } from 'vue';
import {
  IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonItem, IonLabel, IonInput,
  IonButton, IonList, IonCheckbox, IonSelect, IonSelectOption, IonToast
} from '@ionic/vue';
```

#### **b. Definición de Componente**
```javascript
export default {
  components: {
    IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonItem, IonLabel, IonInput,
    IonButton, IonList, IonCheckbox, IonSelect, IonSelectOption, IonToast
  },
  setup() {
    // Lógica aquí...
  }
};
```

#### **c. Variables Reactivas**
```javascript
const tasks = ref([
  { description: 'Comprar leche', priority: 'baja', completed: false },
  { description: 'Lavar la ropa', priority: 'media', completed: true },
  { description: 'Ir al gimnasio', priority: 'alta', completed: false }
]);
const newTask = ref({ description: '', priority: 'baja', completed: false });
const showToast = ref(false);
const showDeleteToast = ref(false);
const showCompleted = ref(false);
```

#### **d. Propiedad Computada**
```javascript
const filteredTasks = computed(() => {
  return tasks.value.filter(task => showCompleted || !task.completed);
});
```

#### **e. Funciones**
```javascript
function addTask() {
  if (newTask.value.description.trim()) {
    tasks.value.push({ ...newTask.value });
    newTask.value = { description: '', priority: 'baja', completed: false };
    showToast.value = true;
  }
}

function deleteTask(index) {
  tasks.value.splice(index, 1);
  showDeleteToast.value = true;
}
```

### 3. Estilos
```css
<style scoped>
ion-item {
  margin-bottom: 10px;
}
ion-checkbox {
  margin-right: 15px;
}
</style>
```

## **Conclusión**
La aplicación de lista de tareas permite a los usuarios gestionar sus tareas de manera eficiente. Se pueden agregar y eliminar tareas, seleccionar prioridades y filtrar tareas completadas. Se puede mejorar añadiendo persistencia de datos o características adicionales como edición de tareas.

