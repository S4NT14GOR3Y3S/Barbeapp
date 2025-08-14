# Barbeapp
BarbeApp  Aplicación móvil desarrollada con Ionic + Angular para el agendamiento de citas en una barbería. Permite a los clientes seleccionar servicios, elegir fecha y hora, y confirmar su cita de manera rápida y sencilla desde cualquier dispositivo móvil.
# BarbeApp

BarbeApp es una aplicación móvil desarrollada con **Ionic + Angular** para el agendamiento de citas en una barbería.  
Permite a los usuarios seleccionar servicios, elegir fecha y hora, y confirmar su cita de manera rápida y sencilla.

## 📱 Características
- Visualización de servicios disponibles.
- Selección de fecha y hora para la cita.
- Navegación por pestañas (Tabs) para acceder a diferentes secciones.
- Interfaz adaptada para dispositivos móviles.

## 🛠 Tecnologías utilizadas
- **Ionic Framework** (Componentes móviles y UI)
- **Angular** (Framework frontend)
- **TypeScript**
- **HTML5 / SCSS**
- **Capacitor** (para funcionalidades nativas en móvil)

## 📂 Estructura del proyecto
src/
├── app/
│ ├── tab1/ # Página de inicio
│ ├── tab2/ # Otra sección (ej. promociones)
│ ├── tab3/ # Perfil o citas agendadas
│ ├── tab4/ # Lista de servicios
│ ├── tabs/ # Contenedor principal con las pestañas
│ └── app-routing.module.ts # Configuración de rutas principales
└── assets/ # Imágenes y recursos

## 🚀 Instalación y ejecución
1. Clonar el repositorio:
   ```bash
   git clone <url-del-repo>
   cd barbeapp
Instalar dependencias:

npm install
Ejecutar en modo desarrollo:

ionic serve
Compilar para producción:

ionic build
📋 Notas
Se recomienda tener instalado Ionic CLI:
npm install -g @ionic/cli
👨‍💻 Autor
Tu nombre aquí

php
Copiar
Editar

---

## **Ejemplo de documentación en el código**
En `tab4.page.ts` (Lista de servicios):
```ts
import { Component } from '@angular/core';
import {
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonList,
  IonItem
} from '@ionic/angular/standalone';
import { NgFor } from '@angular/common';

@Component({
  selector: 'app-tab4',
  templateUrl: './tab4.page.html',
  styleUrls: ['./tab4.page.scss'],
  standalone: true,
  imports: [IonHeader, IonToolbar, IonTitle, IonContent, IonList, IonItem, NgFor]
})
export class Tab4Page {
  /**
   * Lista de servicios disponibles en la barbería.
   * Cada elemento contiene un nombre y un precio.
   */
  servicios = [
    { nombre: 'Corte de cabello', precio: '$10' },
    { nombre: 'Afeitado clásico', precio: '$8' },
    { nombre: 'Corte + Barba', precio: '$15' }
  ];
}
En app-routing.module.ts:

ts
Copiar
Editar
/**
 * Configuración de rutas principales de la aplicación.
 * La ruta vacía redirige a la vista de pestañas (Tabs).
 */
const routes: Routes = [
  {
    path: '',
    redirectTo: 'tabs',
    pathMatch: 'full'
  },
  {
    path: 'tabs',
    loadChildren: () => import('./tabs/tabs.module').then(m => m.TabsPageModule)
  }
];
