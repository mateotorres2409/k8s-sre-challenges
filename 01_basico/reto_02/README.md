# Reto Básico: Uso de ConfigMap para Variables de Entorno en un Deployment

## Descripción

En este reto aprenderás a utilizar un ConfigMap para definir variables de entorno y pasarlas a un Deployment en Kubernetes. El objetivo es separar la configuración del contenedor y gestionar variables de manera centralizada y escalable.

## Objetivos de Aprendizaje

- Crear y aplicar un ConfigMap.
- Referenciar variables de entorno desde un ConfigMap en un Deployment.
- Verificar que los pods del Deployment reciben y muestran correctamente las variables.

## Requisitos Previos

- Acceso a un clúster de Kubernetes.
- `kubectl` instalado.

## Enunciado

1. Crea un ConfigMap llamado `env-config` con las siguientes claves y valores:
   - `APP_ENV=development`
   - `APP_VERSION=1.0`
2. Crea un Deployment llamado `env-demo` que use la imagen `busybox` y tenga 2 réplicas.
3. Haz que los pods del Deployment tomen las variables de entorno desde el ConfigMap `env-config`.
4. Los pods deben ejecutar el comando:  
   `sh -c 'echo "Ambiente: $APP_ENV, Versión: $APP_VERSION" && sleep 3600'`
5. Aplica ambos manifiestos y verifica que las variables se imprimen correctamente en los logs de los pods.

## Criterios de Éxito

- El ConfigMap `env-config` debe existir en el clúster.
- El Deployment `env-demo` debe tener 2 pods en estado Running.
- Al revisar los logs de los pods, debe aparecer el mensaje:  
  `Ambiente: development, Versión: 1.0`

## Cómo Probar

1. Aplica el ConfigMap:  
   `kubectl apply -f <configmap>.yaml`
2. Aplica el Deployment:  
   `kubectl apply -f <deployment>.yaml`
3. Verifica el estado de los pods con `kubectl get pods`.
4. Revisa los logs de cada pod con `kubectl logs <nombre-del-pod>`.

## Sugerencias

- Puedes modificar los valores en el ConfigMap y reiniciar los pods para ver los cambios reflejados en los logs.

---

**¡Buena suerte! Recuerda compartir tu solución en la carpeta `/soluciones/`.**