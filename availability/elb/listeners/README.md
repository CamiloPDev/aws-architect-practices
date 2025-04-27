# Listeners para Application Load Balancer (ALB)

## Características
- Un Listener recibe las conexiones entrantes en el ALB.
- Basado en el puerto y protocolo configurados (HTTP o HTTPS).
- Define acciones predeterminadas (`forward`, `redirect`, `fixed-response`).
- Permite definir **reglas** basadas en condiciones (path, host, headers, etc.).

## Estructura Básica
- **Listener**:
  - Se asocia a un Load Balancer.
  - Escucha en un puerto específico.
  - Tiene acciones predeterminadas (por ejemplo, enviar tráfico a un Target Group).
- **Listener Rules**:
  - Permiten enrutar tráfico basado en condiciones específicas.
  - Cada regla tiene una prioridad (número entero, donde 1 es la más alta).
  - Acciones por regla: `forward`, `redirect`, `fixed-response`.

## Ejemplos de Routing

### Basado en Path
- `/users/*` → Se envía al Target Group de usuarios
- `/posts/*` → Se envía al Target Group de posts

### Basado en Host
- `api.example.com` → Target Group de API
- `admin.example.com` → Target Group de administración

### Acciones
- **Forward**: Redirige la solicitud a un Target Group.
- **Redirect**: Redirige al cliente a otra URL.
- **Fixed-response**: Responde con un mensaje fijo sin contactar targets.

## Curiosidades
- El orden de evaluación depende de la prioridad (menor número = más alta prioridad).
- Puedes tener un "Default Action" para manejar cualquier tráfico que no coincida con reglas específicas.
- Con `redirect` puedes forzar tráfico HTTP a HTTPS automáticamente.

## Referencias
- [AWS - Listeners for Your Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html)
- [AWS - Listener Rules](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-update-rules.html)
- [AWS - ALB Routing Conditions](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html#rule-condition-types)
- [CloudFormation - Listener](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-listener.html)
- [CloudFormation - Listener Rules](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-listenerrule.html)