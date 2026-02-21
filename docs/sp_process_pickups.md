📋 Resumen del Proceso ETL (sp_process_pickups)
Objetivo Principal
Sincronizar los puntos de retiro (pickup points) desde la API de VTEX hacia las tablas de la base de datos PostgreSQL.

Flujo del Proceso
Extracción (Python)

Obtiene 569 registros desde la API de VTEX

Guarda el JSON crudo en raw_api (ID 81)

Transformación y Carga (Procedimiento Almacenado)

Paso 1 - Preparación

Toma el último registro de raw_api

Crea tabla temporal tmp_pickups con los 569 items del JSON

Paso 2 - Sincronización de pickup (Tabla Padre)

INSERTA registros nuevos que no existen

ACTUALIZA registros existentes con datos nuevos

Gestiona bajas: Marca como deleted = true los que ya no están en API

Reactivación: Marca como deleted = false los que vuelven a aparecer

Paso 3 - Sincronización de Tablas Hijas

pickup_business_hours: Horarios de atención

pickup_tags: Etiquetas/tags de cada pickup

Logging

Registra inicio, fin, estado y métricas en etl_log

Resultado Final
Base de datos actualizada reflejando EXACTAMENTE lo que devuelve la API VTEX, manteniendo histórico de bajas (soft delete) mediante la columna deleted.
