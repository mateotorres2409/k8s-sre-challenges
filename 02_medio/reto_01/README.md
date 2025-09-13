# Reto de Diagnóstico: Despliegue con Incidente Simulado

## Descripción

En este reto deberás desplegar una aplicación con una falla intencional en un clúster de Kubernetes. El objetivo es que la persona participante diagnostique y solucione el problema para restaurar el servicio.

## Objetivos de Aprendizaje

- Diagnóstico de problemas en Kubernetes.
- Uso de herramientas (`kubectl`, logs, describe, etc.) para investigación.
- Aplicación de soluciones y buenas prácticas.

## Requisitos Previos

- Acceso a un clúster de Kubernetes.
- `kubectl` instalado.
- Crea namespace `production`
- Aplica los recursos `recursos/manifest.yaml` en el namespace `production`

## Enunciado

1. El equipo reporta que el endpoint /health no responde y la aplicación no es accesible desde el Service.
2. Tu tarea es:
    - Diagnosticar la causa raíz del problema.
    - Documentar los pasos y comandos utilizados.
    - Proponer y aplicar una solución para restaurar el servicio.
    - Explicar cómo evitar este tipo de problemas en el futuro.

## Criterios de Éxito
- Desplegar correctamente el manifiesto.
- Identificar correctamente la causa raíz.
- Documentas los pasos y comandos usados en el diagnóstico.
- Propones y aplicas una solución efectiva.
- Explicas medidas preventivas para el futuro.

## Cómo Probar
1. Ingresa al contenedor desplegado en el pod del deployment con `busybox-test`
2. Realizar un comando curl al servicio `api-prod-service` por el puerto `8090` a la URL `/health`

---

**¡Buena suerte! Este reto simula un incidente real de SRE en Kubernetes.**