Ejercicios Propuestos
📦 Inventario: Reglas de Reabastecimiento por Prioridad
Objetivo: Automatizar la priorización de productos para reabastecimiento interno según criticidad operativa. Criterios de Aceptación:
Campo “prioridad de reabastecimiento” en product.template (ejemplo: baja, media, alta).
Campo “stock objetivo” en product.template .
Acción automática que identifique productos con
qty_available por debajo del stock objetivo y genere una
actividad ( mail.activity ) para el responsable del almacén.
Vista de lista o tablero en inventario que muestre los
productos pendientes de reabastecimiento, agrupados por
prioridad.
Prueba que valide la creación de actividades para productos
por debajo del stock objetivo y que no se creen duplicados
innecesarios para el mismo producto.
🛒 Punto de Venta: Reglas de Descuento por Horario Objetivo: Aplicar descuentos automáticos en el punto de venta
según franjas horarias configurables. Criterios de Aceptación:
Nuevo modelo de configuración para definir reglas con
campos como: name , hour_from , hour_to , discount_percentage .
Aplicación automática del descuento en una orden de
pos.order cuando la venta se registre dentro del horario
definido.
Validación para evitar que se apliquen múltiples descuentos
incompatibles sobre la misma orden.
Vista de configuración accesible desde el menú de punto de
venta.
Prueba que valide órdenes con y sin descuento, incluyendo
casos límite (ej. orden fuera del rango horario o reglas
solapadas).

 Contabilidad: Retenciones Automáticas por
Perfil Fiscal
Objetivo: Aplicar retenciones automáticas en facturas según el
perfil fiscal del cliente. Criterios de Aceptación:
Campo “perfil fiscal” en res.partner (ejemplo: estándar,
agente de retención, exento).
Configuración de retenciones mediante una tabla de reglas.
Aplicación automática de la retención en la factura
( account.move ) al confirmar o validar el documento.
Vista de configuración accesible desde el menú de
contabilidad.
Prueba que valide facturas con y sin retención, incluyendo
casos límite (ej. cliente sin perfil fiscal definido o sin
regla asociada).
Inventario: Clasificación Operativa de
Productos
Objetivo: Permitir clasificar productos con etiquetas
operativas para optimizar picking, almacenamiento y despacho.
Criterios de Aceptación:
Nuevo modelo stock.operation.tag con campos: name , color ,
description , operation_type .
Relación many2many entre product.template y
stock.operation.tag .
Vista kanban en inventario que muestre productos agrupados
por etiquetas operativas o tipo de operación.
Acción rápida en la vista de producto para asignar o
remover etiquetas sin abrir el formulario completo.
Prueba que valide la creación de etiquetas, su asignación a
productos y su visualización en la vista kanban.

Contabilidad: Alertas de Facturas con Riesgo
de Cobro
Objetivo: Crear un tablero simple para identificar facturas
con alto riesgo de atraso en el cobro. Criterios de
Aceptación:
Nuevo modelo account.collection.alert.rule con campos: name ,
days_overdue , amount_min , risk_level .
Evaluación automática de facturas vencidas según los días
de atraso y el monto pendiente.
Vista tablero con agrupación por nivel de riesgo (bajo,
medio, alto).
Configuración accesible desde el menú de contabilidad para
definir reglas de riesgo.
Prueba que valide la clasificación de facturas en el nivel
de riesgo correcto y la visualización en el tablero.
