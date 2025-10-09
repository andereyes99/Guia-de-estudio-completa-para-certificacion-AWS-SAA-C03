**Guía Completa AWS SAA-C03 2025**

Francisco Escobar | Certified Solutions Architect - Associate

💡 Buena suerte en tu examen de certificación# Guía Completa AWS SAA-C03 2025

**Certified Solutions Architect - Associate**

**Francisco Escobar**


**https://www.linkedin.com/in/franciscojeg/**


**https://dev.to/franciscojeg78**

---

## 📊 1. ANÁLISIS

### Amazon Athena

**Analítica interactiva sobre datos en S3 usando SQL sin administrar servidores**

#### Características clave:
- Serverless, sin infraestructura que administrar
- Pago por consulta (por TB escaneado)
- Soporta CSV, JSON, Parquet, ORC, Avro
- Integración con AWS Glue Data Catalog
- Consultas SQL estándar (Presto engine)

**Casos de uso:** Análisis ad-hoc, consultas sobre logs, análisis de datos sin ETL, reporting

> 💡 **Exam tip:** Ideal cuando necesitas consultar S3 directamente sin cargar datos a una base de datos. Usa formatos columnares (Parquet) para reducir costos.

---

### AWS Data Exchange

**Marketplace para suscribirse y compartir conjuntos de datos**

#### Características clave:
- Acceso a datos de terceros (proveedores externos)
- Actualización automática de datasets
- Facturación integrada en AWS
- Datos listos para análisis

**Casos de uso:** Obtener datos externos (financieros, demografía, clima) para enriquecer análisis

---

### AWS Data Pipeline

**Servicio de orquestación para movimiento y transformación de datos**

#### Características clave:
- Programación de trabajos periódicos
- Manejo de dependencias entre tareas
- Soporta on-premises y AWS
- Reintentos automáticos en caso de fallo
- Procesamiento basado en EC2 o EMR

**Casos de uso:** ETL entre sistemas, backups programados, movimiento de datos

> 💡 **Exam tip:** Para pipelines tradicionales; considera Glue para enfoque serverless más moderno.

---

### Amazon EMR (Elastic MapReduce)

**Framework administrado de big data (Hadoop, Spark, Presto, HBase)**

#### Características clave:
- Clústeres escalables en EC2
- Auto-scaling de nodos
- Integración con S3, DynamoDB
- Spot instances para reducir costos hasta 90%
- Notebooks integrados (EMR Notebooks)

**Casos de uso:** Procesamiento masivo de datos, machine learning a escala, análisis de logs, ETL pesado

> 💡 **Exam tip:** Mejor para procesamiento batch intensivo vs Glue. Usa Spot instances para ahorro en cargas fault-tolerant.

---

### AWS Glue

**Servicio ETL serverless completamente administrado**

#### Características clave:
- **Glue Data Catalog:** Metadatos centralizados para todos los datos
- **Crawlers:** Descubrimiento automático de esquemas
- Jobs de ETL en Python/Scala (PySpark)
- **Glue DataBrew:** Preparación visual de datos sin código
- **Glue Studio:** Interfaz visual para crear ETL
- Serverless, pago por uso (DPU - Data Processing Units)

**Casos de uso:** ETL sin servidores, catalogación automática, data lake preparation

> ✅ **Exam tip:** Primera opción para ETL serverless. El Data Catalog es usado por Athena, EMR, Redshift Spectrum.

---

### Amazon Kinesis

**Plataforma para ingesta y procesamiento de datos en tiempo real**

#### Componentes:
- **Kinesis Data Streams:** Streams personalizados, retención 1-365 días, control total, sharding manual
- **Kinesis Data Firehose:** Carga automática a S3/Redshift/OpenSearch/Splunk, near real-time (60s buffer), serverless
- **Kinesis Data Analytics:** Análisis SQL en tiempo real sobre streams
- **Kinesis Video Streams:** Streaming de video para análisis con ML

**Casos de uso:** IoT data ingestion, log aggregation, real-time analytics, clickstream analysis

> 💡 **Exam tip:** Data Streams para control total y procesamiento custom, Firehose para simplicidad y entrega automática a destinos.

---

### AWS Lake Formation

**Servicio para construir, asegurar y gestionar data lakes**

#### Características clave:
- Configuración centralizada de data lakes en S3
- Permisos granulares a nivel de columna (column-level security)
- Integración con Glue Data Catalog
- Blueprints para ingesta automatizada de datos
- Governance centralizado

**Casos de uso:** Gestión empresarial de data lakes con seguridad robusta, compliance

---

### Amazon MSK (Managed Streaming for Apache Kafka)

**Apache Kafka completamente administrado**

#### Características clave:
- Clusters Kafka sin gestión de infraestructura
- Alta disponibilidad multi-AZ automática
- Integración con KMS (encriptación), IAM
- Compatible con aplicaciones Kafka existentes (API nativa)
- MSK Connect para integrar con data sources/sinks

**Casos de uso:** Streaming de eventos, arquitecturas event-driven, reemplazo de Kafka on-prem

> 💡 **Exam tip:** Cuando específicamente necesites Kafka (ecosistema existente) vs Kinesis (AWS-native, más simple).

---

### Amazon OpenSearch Service

**Servicio administrado de búsqueda y análisis (anteriormente Elasticsearch)**

#### Características clave:
- Búsqueda de texto completo
- Análisis de logs y métricas
- Visualización con OpenSearch Dashboards (antes Kibana)
- Auto-scaling de nodos
- Multi-AZ con réplicas
- Integración con Kinesis Firehose, CloudWatch Logs

**Casos de uso:** Búsquedas en aplicaciones, análisis de logs, SIEM, monitoreo de aplicaciones

---

### Amazon QuickSight

**Servicio de Business Intelligence y visualización**

#### Características clave:
- Serverless, pago por usuario/sesión
- Dashboards interactivos y responsivos
- **ML Insights:** Detección automática de anomalías, forecasting
- Integración con múltiples fuentes (S3, RDS, Redshift, Athena, SaaS)
- SPICE engine (in-memory) para performance
- Embedding en aplicaciones

**Casos de uso:** Reportes empresariales, visualizaciones para stakeholders, self-service BI

---

### Amazon Redshift

**Data warehouse columnar para análisis masivos (OLAP)**

#### Características clave:
- Almacenamiento columnar comprimido (10x compresión)
- MPP (Massively Parallel Processing)
- **Redshift Spectrum:** Query S3 sin cargar datos
- Concurrency Scaling (auto-scaling para queries)
- Snapshots automáticos y manuales
- Materialized views
- Multi-AZ opcional
- Enhanced VPC routing

**Casos de uso:** Análisis OLAP, reporting empresarial complejo, data warehousing, BI

> ✅ **Exam tip:** Para queries analíticas complejas sobre grandes volúmenes. vs RDS (OLTP transaccional).

---

## 🔗 2. INTEGRACIÓN DE APLICACIONES

### Amazon AppFlow

**Integración segura entre aplicaciones SaaS y AWS**

#### Características clave:
- Transferencia bidireccional de datos
- Soporta Salesforce, SAP, Slack, ServiceNow, Zendesk, etc.
- Transformación y filtrado de datos
- Encriptación automática en tránsito y reposo
- Triggers automáticos o programados

**Casos de uso:** Sincronizar datos de CRM a S3/Redshift, integrar SaaS con data lake

---

### AWS AppSync

**Servicio para crear APIs GraphQL serverless**

#### Características clave:
- GraphQL API completamente administrada
- Real-time subscriptions (WebSocket automático)
- Offline sync para apps móviles
- Múltiples fuentes de datos (DynamoDB, Lambda, RDS, HTTP)
- Resolvers automáticos
- Integración con Cognito para autenticación

**Casos de uso:** APIs para apps móviles/web con sincronización, real-time apps, apps offline-first

---

### Amazon EventBridge

**Bus de eventos serverless para arquitecturas event-driven**

#### Características clave:
- Enrutamiento basado en reglas (event patterns)
- 100+ integraciones con servicios AWS y SaaS partners
- Event replay (reproducir eventos históricos)
- Schema registry (descubrimiento de esquemas)
- Archive y replay de eventos
- Cross-account event routing

**Casos de uso:** Desacoplar microservicios, automatizaciones, arquitecturas event-driven

> 💡 **Exam tip:** Evolución de CloudWatch Events. Mejor para event routing complejo vs SNS/SQS.

---

### Amazon MQ

**Message broker administrado (ActiveMQ, RabbitMQ)**

#### Características clave:
- Compatibilidad con protocolos estándar (JMS, AMQP, MQTT, STOMP, WebSocket)
- Multi-AZ con failover automático
- NO serverless (basado en instancias)
- Soporta ActiveMQ y RabbitMQ

**Casos de uso:** Migrar aplicaciones que usan message brokers tradicionales

> ⚠️ **Exam tip:** Usa SQS/SNS para nuevas apps (serverless, escalable). MQ solo para compatibilidad con apps existentes.

---

### Amazon SNS (Simple Notification Service)

**Servicio pub/sub de mensajería y notificaciones push**

#### Características clave:
- Múltiples suscriptores por tópico (fan-out pattern)
- Protocolos: HTTP/HTTPS, email, SMS, SQS, Lambda, Kinesis Firehose, mobile push
- **FIFO topics:** Orden garantizado, exactly-once delivery
- Message filtering (suscriptores reciben solo mensajes relevantes)
- Message attributes
- Dead Letter Queue (DLQ)

**Casos de uso:** Notificaciones push, fan-out a múltiples sistemas, alertas, workflows distribuidos

> ✅ **Exam tip:** Pattern común: SNS + SQS para fan-out (un publisher, múltiples consumers con sus propias colas).

---

### Amazon SQS (Simple Queue Service)

**Servicio de colas de mensajes completamente administrado**

#### Tipos:
- **Standard Queue:** Orden best-effort, entrega al menos una vez, throughput ilimitado, low latency
- **FIFO Queue:** Orden estricto garantizado, exactly-once processing, 300 msg/s (3000 con batching)

#### Características clave:
- Desacoplamiento de componentes
- Dead Letter Queues (DLQ) para mensajes fallidos
- Visibility timeout (mensaje invisible mientras se procesa)
- Long polling (reduce costo, espera hasta recibir mensaje)
- Retención hasta 14 días
- Message delay (0-15 minutos)
- Tamaño mensaje hasta 256KB (extended con S3)

**Casos de uso:** Desacoplamiento asíncrono, buffer entre componentes, job queues

> ✅ **Exam tip:** Primera opción para desacoplamiento asíncrono. FIFO cuando necesitas orden estricto.

---

### AWS Step Functions

**Orquestación serverless de flujos de trabajo**

#### Características clave:
- Definición visual de workflows (state machines)
- State machine en JSON (Amazon States Language)
- Integración directa con 200+ servicios AWS
- **Standard:** Larga duración (hasta 1 año), exactly-once execution
- **Express:** Alta velocidad (<5 min), at-least-once, más barato
- Manejo de errores, reintentos, timeouts
- Parallel processing, branching, wait states

**Casos de uso:** Orquestar microservicios, pipelines ETL complejos, workflows de negocio

---

## 💰 3. ADMINISTRACIÓN DE COSTOS

### AWS Budgets

**Define presupuestos y recibe alertas de gasto**

#### Características clave:
- Presupuestos de costo, uso, reservas (RI), Savings Plans
- Alertas por email/SNS cuando se exceden umbrales
- Acciones automáticas (detener instancias, aplicar SCPs)
- Filtros por servicio, región, tag, cuenta

> 💡 **Exam tip:** Monitoreo proactivo de costos con alertas automáticas

---

### Informe de Costo y Uso de AWS (CUR)

**Reportes detallados de costos en CSV**

#### Características clave:
- Datos granulares por hora/día
- Exportación automática a S3
- Integración con Athena para análisis SQL
- QuickSight para visualización

**Casos de uso:** Análisis profundo de costos, chargebacks internos, auditoría financiera

---

### AWS Cost Explorer

**Herramienta visual para analizar costos y uso**

#### Características clave:
- Gráficos interactivos de costos históricos
- Forecasting (predicción hasta 12 meses)
- Recomendaciones de ahorro (RI, Savings Plans)
- Filtros por servicio, región, tag, cuenta
- Reportes custom

> 💡 **Exam tip:** Para visualización rápida de tendencias de costo

---

### Savings Plans

**Modelo de descuentos por compromiso de uso (1 o 3 años)**

#### Tipos:
- **Compute Savings Plans:** Hasta 66% descuento, máxima flexibilidad (EC2, Fargate, Lambda), cualquier región/AZ/OS
- **EC2 Instance Savings Plans:** Hasta 72% descuento, menos flexible (familia de instancia y región específica)

> ✅ **Exam tip:** Más flexible que Reserved Instances. Primera opción para descuentos en workloads predecibles.

---

## 💻 4. INFORMÁTICA / COMPUTE

### AWS Batch

**Ejecuta trabajos batch sin administrar infraestructura**

#### Características clave:
- Provisioning automático de recursos compute
- Optimización de costos (Spot instances)
- Planificación de jobs con dependencias
- Integración con ECS/Fargate
- Array jobs, multi-node parallel jobs

**Casos de uso:** Procesamiento batch, rendering de video, análisis científicos, ETL pesado

---

### Amazon EC2 (Elastic Compute Cloud)

**Máquinas virtuales en la nube**

#### Familias de instancias:
- **General Purpose (T, M):** Balance compute/memoria/network
- **Compute Optimized (C):** Procesamiento intensivo
- **Memory Optimized (R, X, z):** Bases de datos en memoria
- **Storage Optimized (I, D, H):** I/O intensivo
- **Accelerated Computing (P, G, F):** GPU, ML, gráficos

#### Modelos de compra:
- **On-Demand:** Pago por segundo, sin compromiso
- **Reserved (RI):** 1-3 años, hasta 75% descuento
- **Spot:** Hasta 90% descuento, interrumpible con 2min notice
- **Dedicated Hosts:** Hardware físico dedicado, BYOL
- **Dedicated Instances:** Hardware aislado, misma cuenta

#### Características clave:
- **User Data:** Scripts de inicio (bootstrap)
- **Placement Groups:** Cluster (baja latencia), Spread (HA), Partition (distributed apps)
- Enhanced Networking (SR-IOV)
- Hibernate (preserva RAM en EBS)
- Elastic IPs

> ✅ **Exam tip:** Conoce cuándo usar cada tipo y modelo. Spot para fault-tolerant, RI/Savings Plans para workloads predecibles.

---

### Amazon EC2 Auto Scaling

**Escalado automático de instancias EC2**

#### Tipos de políticas:
- **Target Tracking:** Mantener métrica objetivo (ej: CPU 50%)
- **Step Scaling:** Escalar por pasos según alarmas
- **Simple Scaling:** Una acción por alarma
- **Scheduled Scaling:** Horarios predecibles
- **Predictive Scaling:** ML para predecir carga

#### Características clave:
- Health checks (EC2, ELB)
- Launch templates/configurations
- Lifecycle hooks (acciones custom durante launch/terminate)
- Warmup time (instancia lista)
- Cooldown period

> 💡 **Exam tip:** Integra con ELB para alta disponibilidad automática

---

### AWS Elastic Beanstalk

**PaaS para desplegar aplicaciones web sin gestionar infraestructura**

#### Características clave:
- Soporta: Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker
- Gestión automática de capacity, load balancing, auto-scaling
- Health monitoring integrado
- Deployment strategies: All at once, Rolling, Rolling with batch, Immutable, Blue/Green
- Acceso completo a recursos subyacentes (EC2, RDS, etc.)
- .ebextensions para configuración avanzada

**Casos de uso:** Despliegue rápido de apps web, developers sin experiencia DevOps

> ✅ **Exam tip:** Desarrollador controla código, AWS controla infraestructura. Gratis (pagas solo recursos subyacentes).

---

### AWS Outposts

**Infraestructura AWS en tu datacenter on-premises**

#### Características clave:
- Hardware AWS instalado en tu ubicación
- Mismas APIs y servicios AWS localmente
- Conectividad a región AWS (service link)
- Latencia ultrabaja para apps on-prem
- Servicios: EC2, EBS, S3, ECS, RDS, EMR

**Casos de uso:** Híbrido, baja latencia crítica, residencia de datos, modernizar on-prem

---

### AWS Wavelength

**Compute y storage en el edge de redes 5G**

#### Características clave:
- Latencia ultra-baja (<10ms) para dispositivos 5G
- Wavelength Zones en redes de carriers
- Integración con VPC (subnet en Wavelength Zone)
- Servicios: EC2, EBS, VPC

**Casos de uso:** Gaming móvil, streaming 4K/8K, AR/VR, ML inference en edge, IoT

---

## 🐳 5. CONTENEDORES

### Amazon ECS (Elastic Container Service)

**Orquestador de contenedores Docker administrado por AWS**

#### Tipos de lanzamiento:
- **EC2 Launch Type:** Tú gestionas clúster de instancias EC2
- **Fargate Launch Type:** Serverless, sin gestión de instancias

#### Características clave:
- **Task Definitions:** Blueprint de contenedores (imagen, CPU, memoria, puertos)
- **Services:** Mantienen número deseado de tasks, integran con ELB
- Integración profunda con AWS (ELB, IAM, CloudWatch, ECR, Secrets Manager)
- Auto Scaling de tasks
- Service Discovery (Cloud Map)
- Task placement strategies

**Casos de uso:** Microservicios, aplicaciones containerizadas, batch processing

> ✅ **Exam tip:** Más simple que EKS, AWS-native. Fargate para serverless, EC2 para control y ahorro con Spot.

---

### Amazon EKS (Elastic Kubernetes Service)

**Kubernetes administrado por AWS**

#### Características clave:
- Control plane administrado (HA multi-AZ automático)
- Compatible con CNCF Kubernetes (upstream)
- Integración con AWS (IAM, VPC, ELB, EBS, EFS)
- Managed Node Groups, Self-managed nodes, Fargate
- Add-ons: CoreDNS, kube-proxy, VPC CNI

**Casos de uso:** Cuando necesitas Kubernetes estándar, multi-cloud, ecosistema K8s

---

### Amazon ECR (Elastic Container Registry)

**Registro privado de imágenes de contenedores**

#### Características clave:
- Integración con IAM (control de acceso granular)
- Encriptación en reposo (KMS)
- Escaneo de vulnerabilidades (integrado o enhanced)
- Replicación cross-region y cross-account
- Lifecycle policies (limpiar imágenes antiguas)
- OCI compliant

**Casos de uso:** Almacenar imágenes Docker privadas, CI/CD pipelines

> 💡 **Exam tip:** Similar a Docker Hub pero privado, seguro e integrado con AWS

---

## 🗄️ 6. BASE DE DATOS

### Amazon Aurora

**Base de datos relacional compatible con MySQL/PostgreSQL**

#### Características clave:
- **Performance:** 5x MySQL, 3x PostgreSQL
- Storage auto-scaling hasta 128TB (increments de 10GB)
- Hasta 15 read replicas (low lag <10ms)
- Multi-AZ automático (6 copias en 3 AZ)
- **Backtrack:** Viaje en el tiempo (point-in-time sin restore)
- **Global Database:** Replicación cross-region <1s, DR rápido
- Cloning rápido (copy-on-write)
- Custom endpoints
- Parallel query

**Casos de uso:** Apps críticas que requieren alta performance y disponibilidad

> ✅ **Exam tip:** Mejor RDS para performance crítica. Más caro pero superior en todo.

---

### Amazon Aurora Serverless

**Aurora con auto-scaling automático de capacidad**

#### Características clave:
- Pago por segundo de uso (ACUs - Aurora Capacity Units)
- Auto-scaling basado en carga
- Pausa automática cuando no se usa (ahorro)
- Ideal para cargas intermitentes o impredecibles

#### Versiones:
- **v1:** Legacy, pausa/resume más lento
- **v2:** Actual, escala en fracciones de segundo, shared endpoints

**Casos de uso:** Dev/test, aplicaciones con uso variable, nuevas apps sin carga conocida

---

### Amazon DynamoDB

**Base de datos NoSQL serverless de baja latencia**

#### Características clave:
- Latencia milisegundos de un dígito (single-digit ms)
- Auto-scaling ilimitado
- Estructura: Tablas → Items → Atributos
- **Primary Key:** Partition Key o Partition Key + Sort Key
- **Secondary Indexes:** GSI (Global) y LSI (Local)
- **DynamoDB Streams:** Cambios en tiempo real (24h retention)
- **Global Tables:** Multi-región activo-activo, replicación ms
- **TTL:** Expiración automática de items
- Point-in-time recovery (PITR) hasta 35 días
- On-demand o Provisioned capacity modes
- DAX (DynamoDB Accelerator) para caché microsegundos
- Transactions (ACID)

**Casos de uso:** Apps móviles/web, gaming leaderboards, IoT, shopping carts, session storage

> ✅ **Exam tip:** Primera opción para NoSQL serverless. Streams para event-driven architectures.

---

### Amazon ElastiCache

**Cache en memoria administrado (Redis/Memcached)**

#### Tipos:
**Redis:**
- Persistencia (RDB snapshots, AOF)
- Replicación multi-AZ con failover automático
- Pub/Sub
- Sorted sets, lists, hashes (estructuras complejas)
- Transactions
- Backup/restore

**Memcached:**
- Simple, multi-threaded
- Sin persistencia ni replicación
- Horizontal scaling (sharding)

#### Características clave:
- Microsegundos de latencia
- Reduce carga de bases de datos
- Sesiones de usuario
- Leaderboards (Redis sorted sets)

**Casos de uso:** Cache de queries DB, session store, real-time analytics, pub/sub

> 💡 **Exam tip:** Redis para HA y persistencia, Memcached para simplicidad y multi-core.

---

### Amazon RDS (Relational Database Service)

**Bases de datos relacionales administradas**

**Motores:** MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora

#### Características clave:
- Backups automáticos (7-35 días retention)
- Snapshots manuales (indefinidos)
- **Multi-AZ:** Sync replica en otra AZ, failover automático (HA)
- **Read Replicas:** Hasta 5, async replication, escalado de lectura
- Storage auto-scaling
- Maintenance windows
- Encriptación en reposo (KMS) y tránsito (SSL/TLS)
- Parameter groups, option groups
- Enhanced monitoring

**Casos de uso:** Aplicaciones OLTP, CMS, ERP, ecommerce

> ✅ **Exam tip:** Multi-AZ para HA (mismo endpoint), Read Replicas para performance. No puedes SSH a instancias RDS.

---

### Amazon Neptune

**Base de datos de grafos administrada**

#### Características clave:
- Soporta Property Graph (Apache TinkerPop Gremlin) y RDF (SPARQL)
- Optimizado para relaciones complejas (grafos)
- Multi-AZ con hasta 15 read replicas
- Storage auto-scaling hasta 64TB
- Continuous backup a S3

**Casos de uso:** Redes sociales, motores de recomendación, detección de fraude, knowledge graphs

---

### Amazon QLDB (Quantum Ledger Database)

**Ledger database inmutable y verificable**

#### Características clave:
- Historia completa e inmutable de cambios
- Criptográficamente verificable (SHA-256, journal cryptográfico)
- Serverless
- Journal inmutable (append-only)
- PartiQL query language (SQL-like)
- Sin descentralización (centralizado por AWS)

**Casos de uso:** Auditoría, sistemas financieros, supply chain, cumplimiento regulatorio, historial médico

> ✅ **Exam tip:** Cuando necesitas trazabilidad completa e inmutable. Blockchain sin descentralización.

---

## 🛠️ 7. HERRAMIENTAS PARA DESARROLLADORES

### AWS X-Ray

**Servicio de tracing distribuido para análisis de performance**

#### Características clave:
- Trazado end-to-end de requests
- Service map visual de arquitectura
- Identifica cuellos de botella y errores
- Análisis de latencia por componente
- Integración: Lambda, ECS, Beanstalk, API Gateway, EC2
- X-Ray daemon y SDKs

**Casos de uso:** Debug de aplicaciones distribuidas, optimización de microservicios

> 💡 **Exam tip:** Para troubleshooting de arquitecturas complejas y microservicios

---

## 📱 8. FRONTEND WEB Y MÓVIL

### AWS Amplify

**Framework para desarrollo full-stack de apps móviles/web**

**Características:** Hosting con CI/CD, backend serverless automático, autenticación, storage, APIs, frontend libraries (React, Angular, Vue)

**Casos de uso:** Desarrollo rápido de apps modernas serverless

---

### Amazon API Gateway

**Servicio para crear, publicar y gestionar APIs**

#### Tipos:
- **REST API:** RESTful completo, caching, transformación, más features
- **HTTP API:** Más simple, barato, menor latencia
- **WebSocket API:** Comunicación bidireccional real-time

#### Características clave:
- Integración: Lambda, HTTP endpoints, AWS services
- Autenticación: IAM, Cognito, Lambda authorizers, API keys
- Rate limiting, throttling (protección)
- Request/response transformation
- Caching de respuestas
- Stage management (dev, staging, prod)
- CORS support

> ✅ **Exam tip:** Gateway entre clientes externos y backend serverless

---

### AWS Device Farm

**Testing de apps móviles en dispositivos reales**

**Características:** Testing automatizado, dispositivos físicos iOS/Android, remote access, informes con screenshots

---

### Amazon Pinpoint

**Servicio de engagement y campañas multicanal**

**Características:** Email, SMS, push, voz, segmentación de usuarios, análisis de campañas, A/B testing

---

## 🤖 9. MACHINE LEARNING

| Servicio | Función |
|----------|---------|
| **Comprehend** | NLP: sentimientos, entidades, idioma, tópicos, PII |
| **Forecast** | Predicciones time-series con ML |
| **Fraud Detector** | Detección de fraude en pagos, cuentas |
| **Kendra** | Búsqueda empresarial inteligente (semántica) |
| **Lex** | Chatbots conversacionales (tech de Alexa) |
| **Polly** | Texto a voz (60+ idiomas, voces neurales) |
| **Rekognition** | Análisis imágenes/video: faces, objetos, texto, contenido |
| **SageMaker** | Plataforma completa ML: build, train, deploy |
| **Textract** | OCR: extrae texto, tablas, formularios |
| **Transcribe** | Voz a texto (real-time, batch) |
| **Translate** | Traducción automática (75+ idiomas) |

---

## ⚙️ 10. ADMINISTRACIÓN Y GOBERNANZA

### AWS CloudFormation

**Infraestructura como código (IaC)**

#### Características clave:
- Templates JSON/YAML (declarativos)
- **Stacks:** Grupos de recursos como unidad
- **Change sets:** Preview de cambios antes de aplicar
- **Drift detection:** Detecta cambios manuales
- **StackSets:** Deploy en múltiples cuentas/regiones
- Nested stacks, cross-stack references

> ✅ **Exam tip:** Automatización e infraestructura reproducible. Gratis (pagas recursos).

---

### AWS CloudTrail

**Auditoría de acciones API en AWS**

#### Características clave:
- Registro de todas las llamadas API (quién, qué, cuándo, dónde)
- Logs en S3 (encriptados)
- Integración con CloudWatch Logs
- Organization trails (toda la org)
- Event history 90 días gratis
- CloudTrail Insights (detección de anomalías)

> ✅ **Exam tip:** Para compliance, auditoría, "quién hizo qué". Siempre habilitado.

---

### Amazon CloudWatch

**Monitoreo y observabilidad**

#### Componentes:
- **Metrics:** Métricas de servicios AWS y custom
- **Logs:** Centralización, query con Insights
- **Alarms:** Alertas basadas en métricas
- **Events/EventBridge:** Automatización
- **Dashboards:** Visualización
- **Container Insights, Lambda Insights:** Métricas detalladas

> 💡 **Exam tip:** Centro de monitoreo. Métricas cada 5min (gratis) o 1min (custom)

---

### AWS Config

**Auditoría y evaluación de configuraciones**

**Características:** Inventario recursos, historial cambios, Config Rules (compliance), remediation automática

> 💡 **Exam tip:** Para compliance y configuración correcta continua

---

### AWS Organizations

**Gestión centralizada de múltiples cuentas AWS**

#### Características:
- Organizational Units (OUs) jerárquicos
- **Service Control Policies (SCPs):** Permisos máximos
- Facturación consolidada (descuentos por volumen)
- Compartir recursos (RAM)

> ✅ **Exam tip:** Para empresas multi-cuenta. SCPs limitan (no otorgan) permisos.

---

### AWS Systems Manager

**Suite de herramientas para gestión operacional**

#### Componentes clave:
- **Session Manager:** Acceso seguro sin SSH/RDP
- **Parameter Store:** Config y secretos (gratis hasta 10K)
- **Patch Manager:** Gestión de parches
- **Run Command:** Ejecutar en múltiples instancias
- **State Manager:** Configuración deseada
- **Automation:** Runbooks

> ✅ **Exam tip:** Session Manager elimina necesidad de bastions

---

### AWS Trusted Advisor

**Recomendaciones para optimización**

**Categorías:** Cost optimization, Performance, Security, Fault tolerance, Service limits

**Niveles:** Basic (7 checks), Business/Enterprise (todos los checks)

---

## 🎬 11. SERVICIOS MULTIMEDIA

### Amazon Elastic Transcoder

**Transcodificación de archivos multimedia**

**Características:** Conversión formatos video/audio, presets, pipelines, thumbnails

---

### Amazon Kinesis Video Streams

**Ingesta y almacenamiento de streams de video**

**Características:** Retención configurable, reproducción, integración con Rekognition Video

---

## 🚚 12. MIGRACIÓN Y TRANSFERENCIA

### AWS Application Migration Service (MGN)

**Migración lift-and-shift automatizada**

**Características:** Replicación continua, cutover rápido, testing sin impacto

> 💡 **Exam tip:** "Rehost" strategy, migración rápida de servidores físicos/virtuales

---

### AWS Database Migration Service (DMS)

**Migra bases de datos con mínimo downtime**

#### Características:
- Migraciones homogéneas y heterogéneas
- Replicación continua (CDC)
- Schema Conversion Tool (SCT) para conversiones

> ✅ **Exam tip:** Origen puede seguir activo durante migración

---

### AWS DataSync

**Transferencia automatizada on-prem ↔ AWS**

**Características:** 10x más rápido, preserva permisos, verificación integridad, destinos S3/EFS/FSx

> 💡 **Exam tip:** Para movimiento recurrente de grandes volúmenes

---

### Familia AWS Snow

**Dispositivos físicos para transferir datos masivos**

#### Dispositivos:
- **Snowcone:** 8-14 TB, portable
- **Snowball Edge:** Storage Optimized (80 TB), Compute Optimized (42 TB + GPU)
- **Snowmobile:** 100 PB (contenedor)

**Características:** Encriptación E2E (KMS), edge computing (EC2, Lambda)

> ⚠️ **Exam tip:** >10TB usa Snow, >10PB usa Snowmobile

---

### AWS Transfer Family

**Transferencia usando protocolos estándar**

**Protocolos:** SFTP, FTPS, FTP, AS2

**Backend:** S3 o EFS

> 💡 **Exam tip:** Para partners/clientes que usan FTP tradicional

---

## 🌐 13. REDES Y ENTREGA DE CONTENIDO

### Amazon CloudFront

**CDN global para entrega de contenido**

#### Características clave:
- 450+ edge locations globales
- Orígenes: S3, ALB, EC2, custom HTTP
- Cache TTL configurable
- Signed URLs/Cookies (contenido privado)
- Field-level encryption
- Lambda@Edge (compute en edge)
- Origin failover (HA)
- Geo-restriction

> ✅ **Exam tip:** Reduce latencia para usuarios globales, protege origen

---

### AWS Direct Connect

**Conexión dedicada on-prem ↔ AWS**

#### Características:
- Bandwidths: 1, 10, 100 Gbps
- VIFs: Private (VPC), Public (S3, DynamoDB), Transit (TGW)
- NO cifrado por defecto (usar VPN over DX)
- Menor latencia y costos vs Internet

> 💡 **Exam tip:** Para conexión consistente y alta bandwidth. Setup toma semanas.

---

### Elastic Load Balancing (ELB)

**Distribución automática de tráfico**

#### Tipos:
- **ALB:** Layer 7 (HTTP/HTTPS), routing por path/host/headers, targets: EC2/IP/Lambda
- **NLB:** Layer 4 (TCP/UDP), ultra-performance, IP estática, preserva source IP
- **GWLB:** Layer 3 (IP), para appliances (firewalls, IDS/IPS)

**Características comunes:** Multi-AZ, health checks, SSL termination, sticky sessions

> ✅ **Exam tip:** ALB para HTTP, NLB para TCP/performance extrema, GWLB para appliances

---

### AWS Global Accelerator

**Mejora disponibilidad y performance usando red AWS**

**Características:** 2 IPs Anycast estáticas, routing óptimo, failover <30s, endpoints: ALB/NLB/EC2/EIP

> 💡 **Exam tip:** CloudFront cachea contenido, Global Accelerator no (proxy). Para IPs estáticas globales.

---

### Amazon Route 53

**DNS altamente disponible**

#### Routing Policies:
- **Simple:** Un solo recurso
- **Weighted:** Distribución porcentual
- **Latency:** Menor latencia para usuario
- **Failover:** Activo-pasivo con health check
- **Geolocation:** Por ubicación del usuario
- **Geoproximity:** Por proximidad con bias
- **Multi-value:** Multiple IPs con health checks

> ✅ **Exam tip:** Conoce cuándo usar cada routing policy

---

### AWS Transit Gateway

**Hub central para conectar VPCs y redes**

**Características:** Arquitectura hub-and-spoke, conecta miles de VPCs, VPN/DX/peering, multicast

> 💡 **Exam tip:** Simplifica topologías multi-VPC vs malla de peerings

---

### Amazon VPC

**Red virtual aislada en AWS**

#### Componentes:
- **Subnets:** Públicas (IGW) o privadas
- **IGW:** Internet Gateway
- **NAT Gateway:** Internet saliente para privadas
- **Route Tables:** Enrutamiento
- **NACLs:** Firewall stateless (subnet)
- **Security Groups:** Firewall stateful (instancia)
- **VPC Peering:** Conectar VPCs (no transitivo)
- **VPC Endpoints:** Acceso privado a servicios
- **VPC Flow Logs:** Captura tráfico IP

> ✅ **Exam tip:** Arquitectura fundamental. NACLs stateless (explicit deny/allow), SG stateful (solo allow).

---

## 🔐 14. SEGURIDAD, IDENTIDAD Y CONFORMIDAD

### Amazon Cognito

**Gestión de identidad de usuarios para apps**

#### Componentes:
- **User Pools:** Directorio de usuarios, autenticación (sign-up/sign-in)
- **Identity Pools:** Credenciales temporales AWS para usuarios

**Características:** Social/enterprise login, MFA, federated identities

> 💡 **Exam tip:** User Pools = authentication, Identity Pools = authorization AWS

---

### Amazon GuardDuty

**Detección de amenazas inteligente**

**Características:** ML para anomalías, analiza CloudTrail/VPC Flow/DNS logs, threat intelligence, findings con severity

> 💡 **Exam tip:** Habilitar sin agentes, bajo impacto, detección continua

---

### AWS IAM (Identity and Access Management)

**Control de acceso a recursos AWS**

#### Componentes:
- **Users:** Identidades permanentes
- **Groups:** Colecciones de usuarios
- **Roles:** Identidades asumibles (EC2, Lambda, cross-account)
- **Policies:** JSON de permisos (Effect, Action, Resource, Condition)

**Best practices:** Least privilege, MFA, rotate credentials, usar roles

> ✅ **Exam tip:** Core de seguridad. Policies evalúan: Explicit Deny > Explicit Allow > Implicit Deny

---

### Amazon Inspector

**Escaneo automatizado de vulnerabilidades**

**Características:** Escanea EC2, ECR images, Lambda, CVE database, network reachability

---

### AWS KMS (Key Management Service)

**Gestión de claves de cifrado**

#### Características:
- Customer Managed Keys (CMK), AWS Managed Keys
- Rotación automática anual
- Envelope encryption
- Integración profunda con servicios AWS
- Multi-region keys

> ✅ **Exam tip:** Default para cifrado en AWS. vs CloudHSM (dedicado, FIPS 140-2 L3)

---

### Amazon Macie

**Detección de datos sensibles con ML**

**Características:** Escanea S3 en busca de PII, ML para patrones, alertas de exposición

---

### AWS Secrets Manager

**Gestión de secretos con rotación automática**

**Características:** Almacena credenciales/API keys, rotación automática (RDS, Redshift, DocumentDB), cifrado KMS, versionado

> 💡 **Exam tip:** vs Parameter Store (Secrets Manager = rotación, más caro; Parameter Store = gratis básico)

---

## ⚡ 15. SIN SERVIDOR (SERVERLESS)

### AWS Lambda

**Ejecución de código serverless event-driven**

#### Características clave:
- Pago por invocación (primeros 1M gratis) y duración (ms)
- Timeout máximo: 15 minutos
- Memoria: 128MB - 10GB (CPU proporcional)
- Runtimes: Python, Node.js, Java, Go, .NET, Ruby, custom
- Triggers: 200+ event sources (S3, DynamoDB, SQS, API Gateway, etc.)
- Concurrency: 1000 default (aumentable)
- Cold starts (primera invocación más lenta)
- Lambda Layers (código compartido entre funciones)
- Environment variables
- VPC integration
- Versioning y aliases
- Lambda@Edge (CloudFront)

**Casos de uso:** APIs serverless, procesamiento de eventos, automatización, ETL ligero, backends móviles

> ✅ **Exam tip:** Core de arquitecturas serverless. <15min, event-driven, auto-scaling infinito

---

### AWS Fargate

**Compute serverless para contenedores**

**Características:** Sin gestión de EC2, funciona con ECS/EKS, pago por vCPU/memoria usada

> 💡 **Exam tip:** vs EC2 (Fargate = serverless, más caro; EC2 = control, Spot para ahorro)

---

## 💾 16. ALMACENAMIENTO

### Amazon EBS (Elastic Block Store)

**Volúmenes de bloques para EC2**

#### Tipos:
- **gp3/gp2:** SSD general purpose (boot, dev/test) - 3000-16000 IOPS
- **io2/io1:** SSD provisioned IOPS (databases críticas) - hasta 64000 IOPS, Multi-Attach
- **st1:** HDD throughput optimized (big data, data warehouse)
- **sc1:** HDD cold (archivos de acceso infrecuente, más barato)

**Características:** Adjuntado a 1 AZ, Snapshots incrementales en S3, encriptación KMS, Multi-Attach (io1/io2)

> 💡 **Exam tip:** Snapshots son incrementales. Cross-AZ via snapshot copy.

---

### Amazon EFS (Elastic File System)

**Sistema de archivos NFS administrado**

#### Características:
- Compartido entre múltiples instancias/AZs (multi-AZ automático)
- Escalado automático (petabytes)
- Storage classes: Standard, Infrequent Access (IA)
- Lifecycle management (auto-move a IA)
- Performance modes: General Purpose, Max I/O
- Throughput modes: Bursting, Provisioned, Elastic

**Casos de uso:** Content management, web serving, data sharing, home directories

> ✅ **Exam tip:** Multi-AZ, Linux only (NFS), escalado automático

---

### Amazon FSx

**Sistemas de archivos completamente administrados**

#### Tipos:
- **FSx for Windows:** SMB, integración AD, Windows apps, DFS
- **FSx for Lustre:** HPC, ML, procesamiento ultra-rápido, integración S3
- **FSx for NetApp ONTAP:** NetApp features, multi-protocol (NFS, SMB, iSCSI)
- **FSx for OpenZFS:** ZFS, migración from on-prem ZFS

> 💡 **Exam tip:** Windows apps → FSx Windows; HPC/ML → FSx Lustre

---

### Amazon S3 (Simple Storage Service)

**Almacenamiento de objetos escalable**

#### Storage Classes:
- **S3 Standard:** Uso general, 99.99% disponibilidad, 11 9s durabilidad
- **S3 Intelligent-Tiering:** Automático entre access tiers
- **S3 Standard-IA:** Acceso infrecuente, 99.9% disponibilidad
- **S3 One Zone-IA:** Una AZ, 99.5% disponibilidad, más barato
- **S3 Glacier Instant Retrieval:** Archival, retrieval ms
- **S3 Glacier Flexible Retrieval:** Archival, retrieval min-horas
- **S3 Glacier Deep Archive:** Archival más barato, retrieval horas

#### Características clave:
- Versionado, Lifecycle policies, Replicación (CRR, SRR)
- Encriptación: SSE-S3, SSE-KMS, SSE-C, client-side
- MFA Delete, Object Lock (WORM), Pre-signed URLs
- S3 Select, Event notifications, Static website hosting
- Transfer Acceleration (CloudFront edge)

> ✅ **Exam tip:** Durabilidad 11 9s (99.999999999%). Conoce cuándo usar cada storage class.

---

### AWS Storage Gateway

**Almacenamiento híbrido on-prem ↔ S3**

#### Tipos:
- **File Gateway:** NFS/SMB → S3, cache local
- **Volume Gateway:**
  - Stored: Datos primarios local, backups a S3
  - Cached: Datos primarios en S3, cache local
- **Tape Gateway:** Virtual tape library (VTL) → S3/Glacier

**Casos de uso:** Backup híbrido, disaster recovery, cloud migration

> 💡 **Exam tip:** Puente entre on-prem y cloud storage

---

## ⚖️ 17. COMPARACIONES CRÍTICAS

### EC2 vs Lambda

| EC2 | Lambda |
|-----|--------|
| Control total sobre OS e infraestructura | Serverless, cero administración |
| Workloads de larga duración | Event-driven, máximo 15 minutos |
| Apps que requieren personalización | Pago por invocación + duración |
| Pago por hora/segundo | Auto-scaling automático e infinito |
| Administración manual de escalado | Sin gestión de infraestructura |
| Ideal para aplicaciones monolíticas | Perfecto para microservicios |

---

### RDS vs DynamoDB

| RDS | DynamoDB |
|-----|----------|
| Relacional tradicional (OLTP) | NoSQL serverless |
| ACID completo, SQL estándar | Latencia de milisegundos |
| Joins complejos | Key-value / document store |
| Multi-AZ para alta disponibilidad | Global Tables multi-región |
| Escalado vertical principalmente | Escalado horizontal ilimitado |
| Esquema fijo y estructurado | Esquema flexible |

---

### S3 vs EBS

| S3 | EBS |
|----|-----|
| Almacenamiento de objetos | Volúmenes de bloques |
| Durabilidad 99.999999999% (11 9s) | Adjuntado a una instancia EC2 |
| Static websites, archival | Restringido a una AZ |
| Capacidad ilimitada | Boot volumes, databases locales |
| Multiple storage classes | Snapshots para backup |
| $0.023/GB Standard | $0.08-0.125/GB gp3 |

---

### CloudFront vs Global Accelerator

| CloudFront | Global Accelerator |
|------------|-------------------|
| Cachea contenido estático/dinámico | NO cachea (proxy inteligente) |
| 450+ edge locations globales | 2 IPs Anycast estáticas |
| Enfoque en HTTP/HTTPS | TCP/UDP, mejores health checks |
| Reduce carga en origen | Siempre va a origen |
| TTL configurable | Routing óptimo por red AWS |
| Ideal para contenido web | Ideal para apps no-HTTP |

---

### ALB vs NLB

| ALB (Application Load Balancer) | NLB (Network Load Balancer) |
|---------------------------------|-----------------------------|
| Layer 7 (HTTP/HTTPS) | Layer 4 (TCP/UDP) |
| Routing avanzado (path, host, headers) | Ultra-performance (millones req/s) |
| Targets: EC2, IP, Lambda | IP estática por AZ |
| WebSocket support | Preserva source IP |
| Ideal para aplicaciones web | Ideal para gaming, IoT |

---

### Direct Connect vs Site-to-Site VPN

| Direct Connect | Site-to-Site VPN |
|----------------|------------------|
| Conexión dedicada física | Conexión sobre Internet público |
| Alta bandwidth (1-100 Gbps) | Bandwidth variable |
| Latencia consistente y predecible | Latencia puede variar |
| Setup: semanas, más costoso | Setup rápido (minutos) |
| No cifrado por defecto | Cifrado IPsec automático |
| Mejor para cargas enterprise | Ideal para empezar rápido |

---

## 📊 18. TABLAS DE DECISIÓN

### Almacenamiento

| Necesito... | Usa | Por qué |
|-------------|-----|---------|
| Archivos estáticos, backups | S3 | Durabilidad 11 9s, ilimitado, storage classes |
| Bloques para EC2 | EBS | Baja latencia, una AZ, snapshots |
| Sistema archivos compartido Linux | EFS | Multi-AZ, NFS, escalado automático |
| Sistema archivos Windows | FSx Windows | SMB, integración AD |
| HPC ultra-rápido | FSx Lustre | Sub-ms latency, integración S3 |
| Archival largo plazo | S3 Glacier | Muy barato, retrieval horas OK |

---

### Base de Datos

| Necesito... | Usa | Por qué |
|-------------|-----|---------|
| SQL transaccional (OLTP) | RDS | Multi-motor, familiar, ACID |
| SQL alta performance | Aurora | 5x MySQL, auto-scaling, HA |
| NoSQL serverless | DynamoDB | Latencia ms, escalado masivo |
| Data warehouse (OLAP) | Redshift | Columnar, queries complejas, PB escala |
| Cache en memoria | ElastiCache | Microsegundos, reduce carga DB |
| Grafos, relaciones | Neptune | Optimizado para grafos |
| MongoDB compatible | DocumentDB | API MongoDB, administrado |
| Ledger inmutable | QLDB | Auditoría completa, criptográfico |

---

### Compute

| Necesito... | Usa | Por qué |
|-------------|-----|---------|
| Control total, larga duración | EC2 | Flexibilidad máxima, Spot/RI |
| Event-driven, <15min | Lambda | Serverless, pago por uso |
| Contenedores serverless | Fargate | Sin gestión EC2 |
| Contenedores con control | ECS en EC2 | Spot instances, ahorro |
| Kubernetes | EKS | K8s estándar, ecosistema |
| Batch jobs | Batch | Provisioning automático, Spot |
| Deploy rápido sin DevOps | Elastic Beanstalk | PaaS, múltiples lenguajes |

---

### Integración y Mensajería

| Necesito... | Usa | Por qué |
|-------------|-----|---------|
| Desacoplamiento asíncrono | SQS | Colas confiables, FIFO/Standard |
| Pub/sub, fan-out | SNS | Múltiples suscriptores, notificaciones |
| Event routing complejo | EventBridge | 100+ integraciones, filtros avanzados |
| Workflows serverless | Step Functions | Orquestación visual, state machines |
| Message broker tradicional | MQ | Compatibilidad ActiveMQ/RabbitMQ |

---

### Networking

| Necesito... | Usa | Por qué |
|-------------|-----|---------|
| Conexión dedicada on-prem | Direct Connect | Alta bandwidth, consistente |
| Conexión rápida on-prem | Site-to-Site VPN | Setup minutos, cifrado |
| Usuarios remotos | Client VPN | OpenVPN, autenticación flexible |
| Conectar múltiples VPCs | Transit Gateway | Hub-and-spoke, simplifica topología |
| DNS y routing inteligente | Route 53 | 7 políticas routing, health checks |
| Distribución tráfico HTTP | ALB | Layer 7, routing avanzado |
| Distribución tráfico TCP | NLB | Layer 4, ultra-performance |
| CDN global | CloudFront | 450+ edges, cachea contenido |
| Acelerar tráfico global | Global Accelerator | IPs Anycast, mejor routing |

---

## 🎯 19. DOMINIOS DEL EXAMEN SAA-C03

### Dominio 1: Diseño de Arquitecturas Seguras (30%)

**Temas clave:**
- Diseñar acceso seguro a recursos AWS (IAM, roles, policies)
- Diseñar cargas de trabajo y aplicaciones seguras
- Determinar controles de seguridad apropiados

**Enfócate en:** IAM, KMS, Cognito, VPC Security (SG, NACL), encryption at rest/transit, GuardDuty, Inspector, Macie, WAF, Shield

---

### Dominio 2: Diseño de Arquitecturas Resilientes (26%)

**Temas clave:**
- Diseñar arquitecturas escalables y de alta disponibilidad
- Diseñar soluciones de desacoplamiento
- Diseñar arquitecturas multi-tier

**Enfócate en:** Multi-AZ, Auto Scaling, ELB, Route 53 health checks, SQS/SNS, disaster recovery (RPO/RTO), backup strategies

---

### Dominio 3: Diseño de Arquitecturas de Alto Rendimiento (24%)

**Temas clave:**
- Determinar soluciones de almacenamiento y BD de alto rendimiento
- Diseñar soluciones elásticas y escalables
- Determinar servicios de red de alto rendimiento

**Enfócate en:** Caching (CloudFront, ElastiCache, DAX), DB read replicas, storage types, compute optimization, Global Accelerator

---

### Dominio 4: Diseño de Arquitecturas Optimizadas en Costos (20%)

**Temas clave:**
- Diseñar soluciones de almacenamiento optimizadas en costos
- Diseñar soluciones de cómputo optimizadas en costos

**Enfócate en:** S3 storage classes, EC2 pricing (Spot, RI, Savings Plans), RDS optimization, lifecycle policies, Cost Explorer, Budgets

---

## ✅ 20. CHECKLIST PRE-EXAMEN

### Conceptos Fundamentales
- [ ] Comprendo los 5 pilares del Well-Architected Framework
- [ ] Conozco diferencias entre AZ, Region, Edge Location
- [ ] Entiendo modelo de responsabilidad compartida
- [ ] Sé cuándo usar cada servicio compute (EC2, Lambda, Fargate, ECS, EKS)
- [ ] Domino VPC y componentes (subnets, routing, NAT, IGW, endpoints)
- [ ] Comprendo IAM roles, policies, best practices
- [ ] Conozco todos los tipos de ELB y cuándo usar cada uno
- [ ] Entiendo S3 storage classes y lifecycle policies

---

### Patrones Arquitectónicos
- [ ] Puedo diseñar arquitecturas multi-tier (web, app, DB)
- [ ] Sé implementar alta disponibilidad (Multi-AZ, Multi-Region)
- [ ] Comprendo patrones de desacoplamiento (SQS, SNS, EventBridge)
- [ ] Puedo diseñar disaster recovery con diferentes RPO/RTO
- [ ] Entiendo arquitecturas serverless completas
- [ ] Sé diseñar arquitecturas híbridas (on-prem + AWS)
- [ ] Comprendo estrategias de caching en múltiples capas
- [ ] Puedo optimizar costos sin sacrificar funcionalidad

---

### Servicios Clave
- [ ] EC2: tipos, pricing models, placement groups, user data
- [ ] S3: storage classes, versioning, replication, security features
- [ ] RDS/Aurora: Multi-AZ vs Read Replicas, backups, encryption
- [ ] DynamoDB: keys, indexes, streams, capacity modes, Global Tables
- [ ] Lambda: limits, triggers, best practices, cold starts
- [ ] CloudFormation: templates, stacks, change sets, drift detection
- [ ] Route 53: todas las routing policies y cuándo usarlas
- [ ] CloudWatch: metrics, logs, alarms, custom metrics
- [ ] CloudTrail: auditoría, governance, integration con CloudWatch
- [ ] KMS: encryption, key policies, envelope encryption

---

### Comparaciones Críticas
- [ ] Puedo elegir entre RDS, DynamoDB, Redshift, Aurora
- [ ] Sé cuándo usar S3 vs EBS vs EFS vs FSx
- [ ] Entiendo diferencias entre ALB, NLB, GWLB
- [ ] Comprendo Direct Connect vs VPN vs PrivateLink
- [ ] Sé cuándo usar CloudFront vs Global Accelerator
- [ ] Puedo elegir entre EC2, Lambda, Fargate según caso
- [ ] Entiendo Kinesis Data Streams vs Firehose
- [ ] Comprendo SNS vs SQS vs EventBridge
- [ ] Sé diferenciar Multi-AZ vs Read Replicas
- [ ] Entiendo KMS vs CloudHSM vs Secrets Manager

---

### Seguridad
- [ ] IAM best practices (least privilege, MFA, roles sobre users)
- [ ] Encryption en reposo (KMS) y en tránsito (TLS/SSL)
- [ ] Security Groups (stateful) vs NACLs (stateless)
- [ ] GuardDuty, Inspector, Macie, Detective - qué hace cada uno
- [ ] Compliance: CloudTrail (quién hizo qué), Config (configuración)
- [ ] Shield Standard vs Advanced, WAF para L7 protection
- [ ] Cognito User Pools vs Identity Pools

---

### Optimización de Costos
- [ ] EC2 pricing: On-Demand, Reserved, Spot, Savings Plans
- [ ] S3 storage classes y cuándo usar cada una
- [ ] Right-sizing con Compute Optimizer
- [ ] Reserved capacity para RDS, DynamoDB, ElastiCache
- [ ] Cost monitoring: Budgets (alertas), Cost Explorer (análisis)
- [ ] Lifecycle policies para transicionar a storage más barato
- [ ] Spot instances para cargas fault-tolerant

---

## 🔍 21. SEÑALES CLAVE EN PREGUNTAS DEL EXAMEN

### Cuando la pregunta dice "MENOR COSTO"...
- **Compute:** Lambda (serverless), Spot instances, Savings Plans
- **Storage:** S3 IA, Glacier, Lifecycle policies
- **Database:** Aurora Serverless, DynamoDB on-demand
- **Network:** CloudFront caching, VPC endpoints (evita NAT)

---

### Cuando la pregunta dice "ALTA DISPONIBILIDAD"...
- **Deploy:** Multi-AZ (RDS, EFS, ELB)
- **Scaling:** Auto Scaling Groups con múltiples AZs
- **Database:** Aurora (6 copias 3 AZ), DynamoDB auto-replication
- **Storage:** S3 (99.99% disponibilidad), EFS multi-AZ
- **DNS:** Route 53 health checks con failover

---

### Cuando la pregunta dice "MÍNIMA LATENCIA"...
- **Cache:** CloudFront (global), ElastiCache (microsegundos), DAX (DynamoDB)
- **Database:** Aurora read replicas, DynamoDB (single-digit ms)
- **Network:** Global Accelerator, Direct Connect
- **Compute:** Lambda en misma región, EC2 Placement Groups

---

### Cuando la pregunta dice "DESACOPLAMIENTO"...
- **Async:** SQS (colas), SNS (pub/sub)
- **Event-driven:** EventBridge (routing complejo)
- **Workflows:** Step Functions (orquestación)
- **Streaming:** Kinesis (real-time)

---

### Cuando la pregunta dice "SERVERLESS"...
- **Compute:** Lambda, Fargate
- **Storage:** S3
- **Database:** DynamoDB, Aurora Serverless
- **APIs:** API Gateway, AppSync
- **Analytics:** Athena, Glue

---

### Cuando la pregunta dice "MIGRACIÓN RÁPIDA"...
- **Servidores:** Application Migration Service (MGN)
- **Databases:** DMS con replicación continua
- **Archivos grandes:** DataSync (automatizado)
- **Datos masivos:** Snow Family (offline)

---

### Cuando la pregunta dice "ON-PREMISES INTEGRATION"...
- **Network:** Direct Connect, Site-to-Site VPN
- **Storage:** Storage Gateway (File/Volume/Tape)
- **Sync:** DataSync (automated transfer)
- **Compute:** Outposts (AWS hardware on-prem)

---

### Cuando la pregunta dice "COMPLIANCE/AUDIT"...
- **API Tracking:** CloudTrail (quién hizo qué)
- **Configuration:** Config (compliance rules, remediation)
- **Threat Detection:** GuardDuty
- **Data Classification:** Macie (PII en S3)
- **Vulnerability:** Inspector
- **Centralized:** Security Hub

---

### Cuando la pregunta dice "REAL-TIME"...
- **Streaming:** Kinesis Data Streams
- **Database:** DynamoDB Streams
- **Notifications:** SNS
- **WebSocket:** API Gateway WebSocket, AppSync

---

### Cuando la pregunta dice "BIG DATA/ANALYTICS"...
- **Processing:** EMR (Hadoop/Spark), Glue (ETL serverless)
- **Query:** Athena (SQL on S3)
- **Warehouse:** Redshift (OLAP)
- **Streaming:** Kinesis, MSK (Kafka)
- **Visualization:** QuickSight

---

## 🚀 22. RECURSOS Y ESTRATEGIA FINAL

### Información del Examen

- **Preguntas:** 65 (50 scored + 15 unscored)
- **Duración:** 130 minutos (~2 minutos/pregunta)
- **Formato:** Multiple choice y multiple response
- **Puntaje mínimo:** 720/1000
- **Costo:** $150 USD
- **Validez:** 3 años

---

### Recursos Recomendados

#### 📚 Práctica Hands-on
- **AWS Free Tier:** Experimenta con servicios reales
- **AWS Workshops:** workshops.aws (escenarios guiados)
- **AWS Well-Architected Labs:** Escenarios prácticos
- **Skill Builders CloudQuest:** Aprendizaje gamificado

#### ✍️ Exámenes de Práctica
- **Tutorials Dojo:** Exámenes muy similares al real (MUY recomendado)
- **AWS Official Practice Exam:** $20, feeling del examen real
- **WhizLabs:** Múltiples practice tests


#### 📖 Documentación
- **AWS FAQs:** Lee FAQs de servicios clave (S3, EC2, RDS, VPC)
- **AWS Whitepapers:** Well-Architected Framework (ESENCIAL)
- **AWS Documentation:** Límites de servicio y best practices
- **AWS Architecture Center:** Reference architectures

#### 🎓 Cursos Online
- **Stephane Maarek (Udemy):** Curso completo SAA-C03
- **Adrian Cantrill:** Profundidad técnica excepcional
- **A Cloud Guru/Pluralsight:** Cursos interactivos


---

### Estrategia el Día del Examen

1. **Lee cuidadosamente:** Identifica palabras clave (menor costo, alta disponibilidad, mínima latencia)
2. **Elimina opciones:** Descarta respuestas obviamente incorrectas primero
3. **Marca y continúa:** Marca preguntas difíciles, vuelve después
4. **Gestiona tiempo:** ~2 min/pregunta, prioriza rápidas primero
5. **No cambies respuestas:** A menos que estés seguro del error
6. **Revisa marcadas:** Usa tiempo restante para revisar
7. **No dejes vacías:** No hay penalización por respuesta incorrecta

---

### 🏆 Tips de Oro

- ⭐ **AWS siempre prefiere:** Managed services > Self-managed
- ⭐ **Serverless primero:** Si es posible, serverless es la respuesta
- ⭐ **Multi-AZ para HA:** Casi siempre la respuesta correcta para disponibilidad
- ⭐ **Security Groups:** Primero en seguridad de red (stateful > stateless)
- ⭐ **IAM Roles:** Siempre sobre credenciales hardcoded
- ⭐ **Least privilege:** Dar solo permisos necesarios
- ⭐ **Encryption everywhere:** At rest (KMS) y in transit (TLS)
- ⭐ **CloudWatch:** Para monitoring, CloudTrail para auditing
- ⭐ **S3 para todo:** Backups, static content, data lakes
- ⭐ **Auto Scaling:** Casi siempre parte de la solución

---

## 🎉 ¡Estás Listo!

Has completado esta guía exhaustiva para el examen AWS SAA-C03.

Con dedicación, práctica hands-on y exámenes de práctica, **¡aprobarás tu certificación!**

💪 **¡Mucha suerte en tu examen!** 🚀

