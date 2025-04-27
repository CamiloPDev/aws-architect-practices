# AWS Application Load Balancer (ALB)

## Características
- Capa 7 del modelo OSI (HTTP/HTTPS)
- Soporte para múltiples Target Groups
- Soporte para múltiples Targets en la misma máquina (por ejemplo: contenedores)
- Compatible con HTTP/2 y WebSocket
- Redirección automática de HTTP a HTTPS

## Enrutamiento

### Por URL Path
- Ejemplos:
  - `example.com/users`
  - `example.com/posts`

### Por Host
- Ejemplos:
  - `one.example.com`
  - `other.example.com`

### Por Query String (Parámetros)
- Ejemplo:
  - `example.com/users?id=123&order=false`

## Curiosidades
- El ALB es ideal para arquitecturas basadas en microservicios utilizando contenedores.
- Permite usar **Port Mapping** en Amazon ECS, facilitando la gestión dinámica de puertos para servicios desplegados.

## Referencias
- [AWS - What is an Application Load Balancer?](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
- [AWS - Application Load Balancer Components](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-components.html)
- [AWS - Listener Rules](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-update-rules.html)
- [AWS - Target Groups for Your Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)
- [AWS - Port Mapping in ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-load-balancing.html#service-load-balancing-application)
- [CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-loadbalancer.html)