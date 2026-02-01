FernanPop - Memoria de Cambios (Tema 3 vs Tema 4)
1.Introducción
Este documento detalla la evolución de la aplicación FernanPop desde los requisitos del
Tema 3 hasta la implementación final del Tema 4. Se ha pasado de un código monolítico a
una arquitectura modular orientada a funciones, integrando servicios de red y seguridad.
2.Tabla Comparativa de Mejoras
Característica
Tema 3 Tema
4
Estructura
Main único y denso Modularizado en funciones
ID
Producto
Manual / Fijo Aleatorio (1-100k) y Único
Seguridad
Login básico Validación por Token (GMail)
Errores
Riesgo de cierre (Excep.) Control total con try-catch
Comunicación
Ninguna GMail SMTP y Telegram Bot API
3.Implementación de Funciones
(Modularidad)
El Main ha sido simplificado. Se han creado métodos estáticos como realizarLogin(),
realizarRegistro(), publicarNuevoArticulo() y gestionarCierreDeVenta(). Esto mejora la
legibilidad y facilita el mantenimiento del código.
4.Generación de IDs y Unicidad
La clase Producto genera ahora un ID aleatorio. Se ha implementado una función de
búsqueda recursiva que garantiza que ningún producto nuevo tenga el mismo ID que uno ya
existente en la aplicación
5.Seguridad y Notificaciones Externas
Se ha integrado la clase Comunicaciones.java. Ahora el sistema envía un Token aleatorio
por correo para validar cuentas nuevas. Además, cada transacción (subida o venta) genera
un correo al usuario y un mensaje de Telegram al administrador.
