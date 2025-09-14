# Escenario: Microservicio de UUIDs con Falla

## Descripción

Imagina que un desarrollador despliega un microservicio encargado de generar UUIDs, el cual es fundamental para la integración con un servicio crítico de la empresa. Todo parece estar bien: los pods del microservicio aparecen en estado **Running** y no muestran errores evidentes en Kubernetes.

Sin embargo, el equipo de desarrollo reporta que el endpoint `/uuid` no responde y la integración con el servicio crítico está fallando. Tras varios intentos de solución sin éxito, el incidente es escalado al equipo de SRE.

## Tu reto como SRE

1. **Diagnosticar la causa raíz:** Aunque los pods están en estado Running, el servicio no funciona correctamente. Debes investigar por qué el endpoint `/uuid` no responde y por qué la aplicación no es accesible desde el Service.
2. **Documentar los pasos y comandos utilizados:** Registra cada comando y observación relevante durante tu diagnóstico.
3. **Proponer y aplicar una solución:** Una vez identificada la causa, realiza los cambios necesarios para restaurar el servicio.
4. **Explicar cómo evitar este tipo de problemas en el futuro:** Sugiere buenas prácticas y mecanismos de monitoreo o alertas para detectar este tipo de fallas antes de que impacten al negocio.


## Requisitos Previos

- Acceso a un clúster de Kubernetes.
    - Cluster local (KIND - Minikube - k3d)
    - `kubectl` instalado.
    - https://labs.play-with-k8s.com
```sh
# Crear nueva instancia
    # node1
    # node2
# node1 - indicaciones de consola
1. Initializes cluster master node:
2. Initialize cluster networking:
# node1
#3. 
kubeadm token create --print-join-command
# node2
4. Registrar el output del paso 3
# node1
# 5.
kubectl label node node2 node-role.kubernetes.io/worker=worker
kubectl get nodes 
```
- Preparar entorno
```sh
kubectl create ns production
kubectl apply -f https://raw.githubusercontent.com/mateotorres2409/k8s-sre-challenges/refs/heads/main/02_medio/reto_01/recursos/manifest.yaml -n production
```

## Cómo Probar
1. Inovacar el servicio **api-uuid-service** por el puerto **8090** a la url **/uuid** expuesto por el microservicio **api-uuid**

---

**¡Buena suerte!**