# Target Groups for Application Load Balancer (ALB)

## Características
- Asociados a un Load Balancer de capa 7 (Application Load Balancer)
- Permiten enrutar tráfico hacia instancias, contenedores o direcciones IP
- Soportan múltiples protocolos (HTTP y HTTPS)
- Configuración personalizada de Health Checks
- Permiten definir el tipo de Target: `instance`, `ip` o `lambda`

## Configuraciones principales

### Protocolo y Puerto
- Definen cómo se comunica el Load Balancer con los targets.
- Ejemplos:
  - `HTTP` en puerto `80`
  - `HTTPS` en puerto `443`

### Health Checks
- Validan la disponibilidad de los targets mediante chequeos periódicos.
- Puedes configurar:
  - Protocolo (`HTTP` o `HTTPS`)
  - Ruta de comprobación (`/`, `/health`, etc.)
  - Códigos HTTP esperados (`200`, `302`, etc.)

### Matcher
- Especifica qué códigos de respuesta HTTP se consideran exitosos.

### Target Types
- `instance`: Targets son instancias EC2.
- `ip`: Targets son direcciones IP específicas.
- `lambda`: Targets son funciones Lambda (no usado en ALB tradicionalmente).

## Curiosidades
- Un solo ALB puede enrutar tráfico a múltiples Target Groups basados en reglas.
- Puedes asociar múltiples instancias o contenedores a un mismo Target Group.
- El uso de Health Checks ayuda a eliminar automáticamente targets no saludables.

## Referencias
- [AWS - What is a Target Group?](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)
- [AWS - Health Checks for Your Target Groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)
- [AWS - Target Type Differences](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-types.html)
- [CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-targetgroup.html)