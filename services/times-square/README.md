# times-square

An API service for managing and rendering parameterized Jupyter notebooks.

**Homepage:** <https://github.com/lsst-sqre/times-square>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | redis | 17.1.6 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity rules for the times-square deployment pod |
| autoscaling.enabled | bool | `false` | Enable autoscaling of times-square deployment |
| autoscaling.maxReplicas | int | `100` | Maximum number of times-square deployment pods |
| autoscaling.minReplicas | int | `1` | Minimum number of times-square deployment pods |
| autoscaling.targetCPUUtilizationPercentage | int | `80` | Target CPU utilization of times-square deployment pods |
| cloudsql.enabled | bool | `false` | Enable the Cloud SQL Auth Proxy sidecar, used with CloudSQL databases on Google Cloud |
| cloudsql.image.pullPolicy | string | `"IfNotPresent"` | Pull policy for Cloud SQL Auth Proxy images |
| cloudsql.image.repository | string | `"gcr.io/cloudsql-docker/gce-proxy"` | Cloud SQL Auth Proxy image to use |
| cloudsql.image.tag | string | `"1.32.0"` | Cloud SQL Auth Proxy tag to use |
| cloudsql.instanceConnectionName | string | `""` | Instance connection name for a CloudSQL PostgreSQL instance |
| cloudsql.serviceAccount | string | `""` | The Google service account that has an IAM binding to the `times-square` Kubernetes service accounts and has the `cloudsql.client` role |
| config.databaseUrl | string | None, must be set | URL for the PostgreSQL database |
| config.enableGitHubApp | string | `"False"` | Toggle to enable the GitHub App functionality |
| config.githubAppId | string | `""` | GitHub application ID |
| config.logLevel | string | `"INFO"` | Logging level: "DEBUG", "INFO", "WARNING", "ERROR", "CRITICAL" |
| config.name | string | `"times-square"` | Name of the service. |
| config.profile | string | `"production"` | Run profile: "production" or "development" |
| config.queueRedisUrl | string | Points to embedded Redis | URL for Redis arq queue database |
| config.redisUrl | string | Points to embedded Redis | URL for Redis html / noteburst job cache database |
| fullnameOverride | string | `""` | Override the full name for resources (includes the release name) |
| global.baseUrl | string | Set by times-square Argo CD Application | Base URL for the environment |
| global.host | string | Set by times-square Argo CD Application | Host name for ingress |
| global.vaultSecretsPathPrefix | string | Set by times-square Argo CD Application | Base path for Vault secrets |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the times-square image |
| image.repository | string | `"ghcr.io/lsst-sqre/times-square"` | Image to use in the times-square deployment |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Secret names to use for all Docker pulls |
| ingress.annotations | object | `{}` | Additional annotations for the ingress rule |
| ingress.className | string | `"nginx"` | Class name that should serve this ingress |
| ingress.enabled | bool | `true` | Create an ingress resource |
| ingress.gafaelfawrAuthQuery | string | `"scope=exec:admin&auth_type=basic"` | Gafaelfawr auth query string |
| ingress.path | string | `"/times-square/api"` | Root URL path prefix for times-square API |
| ingress.pathType | string | `"ImplementationSpecific"` | Path type for the ingress rule |
| nameOverride | string | `""` | Override the base name for resources |
| nodeSelector | object | `{}` | Node selection rules for the times-square deployment pod |
| podAnnotations | object | `{}` | Annotations for the times-square deployment pod |
| redis.auth.enabled | bool | `false` |  |
| redis.fullnameOverride | string | `"times-square-redis"` |  |
| replicaCount.api | int | `1` | Number of API deployment pods to start |
| replicaCount.worker | int | `1` | Number of worker deployment pods to start |
| resources | object | `{}` | Resource limits and requests for the times-square deployment pod |
| service.port | int | `8080` | Port of the service to create and map to the ingress |
| service.type | string | `"ClusterIP"` | Type of service to create |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account. If CloudSQL is in use, the annotation specifying the Google service account will also be added. |
| serviceAccount.create | bool | `false` | Force creation of a service account. Normally, no service account is used or mounted. If CloudSQL is enabled, a service account is always created regardless of this value. |
| serviceAccount.name | string | Name based on the fullname template | Name of the service account to use |
| tolerations | list | `[]` | Tolerations for the times-square deployment pod |
