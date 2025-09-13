# Reto Básico: Despliegue de una Aplicación Web en Kubernetes

## Descripción

En este reto aprenderás a desplegar una aplicación web sencilla en un clúster de Kubernetes utilizando un Deployment y un Service. El objetivo es familiarizarte con los conceptos básicos de pods, deployments y servicios.

## Objetivos de Aprendizaje

- Comprender cómo crear y aplicar manifiestos básicos de Kubernetes.
- Aprender a exponer una aplicación mediante un Service.
- Verificar el estado de los recursos desplegados.

## Requisitos Previos

- Tener acceso a un clúster de Kubernetes (puedes usar minikube, kind, etc.).
- Tener instalado `kubectl`.

## Enunciado

1. Crea un Deployment llamado `web-app` que despliegue una imagen de NGINX (`nginx:latest`) con 2 réplicas.
2. Expón el Deployment mediante un Service de tipo `NodePort` llamado `web-app`.
3. Asegúrate de que la aplicación sea accesible desde tu máquina local.

## Recursos

- Puedes usar la documentación oficial de Kubernetes: https://kubernetes.io/es/docs/

## Criterios de Éxito

- El Deployment `web-app` debe tener 2 pods en estado Running.
- El Service `web-app` debe exponer el puerto 8081 de los pods y ser accesible desde fuera del clúster (usando el puerto asignado por NodePort).
- Debes poder acceder a la página de bienvenida de NGINX desde tu navegador o por medio del comando curl.

## Cómo Probar

1. Aplica los manifiestos con `kubectl apply -f <archivo>.yaml`.
2. Verifica los pods con `kubectl get pods`.
3. Verifica el servicio con `kubectl get svc`.
4. Accede a `http://localhost:<NodePort>` en tu navegador.

## Sugerencias

- Puedes obtener el puerto asignado por NodePort con `kubectl get svc web-app`.

---

**¡Buena suerte! Recuerda compartir tu solución en la carpeta `/soluciones/`.**