## API Report File for "@backstage/plugin-kubernetes-common"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { Entity } from '@backstage/catalog-model';
import type { JsonObject } from '@backstage/types';
import { PodStatus } from '@kubernetes/client-node';
import { V1ConfigMap } from '@kubernetes/client-node';
import { V1CronJob } from '@kubernetes/client-node';
import { V1DaemonSet } from '@kubernetes/client-node';
import { V1Deployment } from '@kubernetes/client-node';
import { V1HorizontalPodAutoscaler } from '@kubernetes/client-node';
import { V1Ingress } from '@kubernetes/client-node';
import { V1Job } from '@kubernetes/client-node';
import { V1LimitRange } from '@kubernetes/client-node';
import { V1Pod } from '@kubernetes/client-node';
import { V1ReplicaSet } from '@kubernetes/client-node';
import { V1Service } from '@kubernetes/client-node';
import { V1StatefulSet } from '@kubernetes/client-node';

// @public
export const ANNOTATION_KUBERNETES_API_SERVER = 'kubernetes.io/api-server';

// @public
export const ANNOTATION_KUBERNETES_API_SERVER_CA =
  'kubernetes.io/api-server-certificate-authority';

// @public
export const ANNOTATION_KUBERNETES_AUTH_PROVIDER =
  'kubernetes.io/auth-provider';

// @public
export const ANNOTATION_KUBERNETES_DASHBOARD_APP =
  'kubernetes.io/dashboard-app';

// @public
export const ANNOTATION_KUBERNETES_DASHBOARD_URL =
  'kubernetes.io/dashboard-url';

// @public
export const ANNOTATION_KUBERNETES_OIDC_TOKEN_PROVIDER =
  'kubernetes.io/oidc-token-provider';

// @public
export const ANNOTATION_KUBERNETES_SKIP_METRICS_LOOKUP =
  'kubernetes.io/skip-metrics-lookup';

// @public
export const ANNOTATION_KUBERNETES_SKIP_TLS_VERIFY =
  'kubernetes.io/skip-tls-verify';

// @public (undocumented)
export type AuthProviderType = 'google' | 'serviceAccount' | 'aws' | 'azure';

// @public (undocumented)
export interface ClientContainerStatus {
  // (undocumented)
  container: string;
  // (undocumented)
  cpuUsage: ClientCurrentResourceUsage;
  // (undocumented)
  memoryUsage: ClientCurrentResourceUsage;
}

// @public (undocumented)
export interface ClientCurrentResourceUsage {
  // (undocumented)
  currentUsage: number | string;
  // (undocumented)
  limitTotal: number | string;
  // (undocumented)
  requestTotal: number | string;
}

// @public (undocumented)
export interface ClientPodStatus {
  // (undocumented)
  containers: ClientContainerStatus[];
  // (undocumented)
  cpu: ClientCurrentResourceUsage;
  // (undocumented)
  memory: ClientCurrentResourceUsage;
  // (undocumented)
  pod: V1Pod;
}

// @public (undocumented)
export interface ClusterAttributes {
  dashboardApp?: string;
  dashboardParameters?: JsonObject;
  dashboardUrl?: string;
  name: string;
}

// @public (undocumented)
export interface ClusterObjects {
  // (undocumented)
  cluster: ClusterAttributes;
  // (undocumented)
  errors: KubernetesFetchError[];
  // (undocumented)
  podMetrics: ClientPodStatus[];
  // (undocumented)
  resources: FetchResponse[];
}

// @public (undocumented)
export interface ConfigMapFetchResponse {
  // (undocumented)
  resources: Array<V1ConfigMap>;
  // (undocumented)
  type: 'configmaps';
}

// @public (undocumented)
export interface CronJobsFetchResponse {
  // (undocumented)
  resources: Array<V1CronJob>;
  // (undocumented)
  type: 'cronjobs';
}

// @public (undocumented)
export interface CustomObjectsByEntityRequest {
  // (undocumented)
  auth: KubernetesRequestAuth;
  // (undocumented)
  customResources: CustomResourceMatcher[];
  // (undocumented)
  entity: Entity;
}

// @public (undocumented)
export interface CustomResourceFetchResponse {
  // (undocumented)
  resources: Array<any>;
  // (undocumented)
  type: 'customresources';
}

// @public (undocumented)
export interface CustomResourceMatcher {
  // (undocumented)
  apiVersion: string;
  // (undocumented)
  group: string;
  // (undocumented)
  plural: string;
}

// @public (undocumented)
export interface DaemonSetsFetchResponse {
  // (undocumented)
  resources: Array<V1DaemonSet>;
  // (undocumented)
  type: 'daemonsets';
}

// @public (undocumented)
export interface DeploymentFetchResponse {
  // (undocumented)
  resources: Array<V1Deployment>;
  // (undocumented)
  type: 'deployments';
}

// @public (undocumented)
export type FetchResponse =
  | PodFetchResponse
  | ServiceFetchResponse
  | ConfigMapFetchResponse
  | DeploymentFetchResponse
  | LimitRangeFetchResponse
  | ReplicaSetsFetchResponse
  | HorizontalPodAutoscalersFetchResponse
  | JobsFetchResponse
  | CronJobsFetchResponse
  | IngressesFetchResponse
  | CustomResourceFetchResponse
  | StatefulSetsFetchResponse
  | DaemonSetsFetchResponse
  | PodStatusFetchResponse;

// @public (undocumented)
export interface HorizontalPodAutoscalersFetchResponse {
  // (undocumented)
  resources: Array<V1HorizontalPodAutoscaler>;
  // (undocumented)
  type: 'horizontalpodautoscalers';
}

// @public (undocumented)
export interface IngressesFetchResponse {
  // (undocumented)
  resources: Array<V1Ingress>;
  // (undocumented)
  type: 'ingresses';
}

// @public (undocumented)
export interface JobsFetchResponse {
  // (undocumented)
  resources: Array<V1Job>;
  // (undocumented)
  type: 'jobs';
}

// @public (undocumented)
export type KubernetesErrorTypes =
  | 'BAD_REQUEST'
  | 'UNAUTHORIZED_ERROR'
  | 'NOT_FOUND'
  | 'SYSTEM_ERROR'
  | 'UNKNOWN_ERROR';

// @public (undocumented)
export type KubernetesFetchError = StatusError | RawFetchError;

// @public (undocumented)
export interface KubernetesRequestAuth {
  // (undocumented)
  google?: string;
  // (undocumented)
  oidc?: {
    [key: string]: string;
  };
}

// @public (undocumented)
export interface KubernetesRequestBody {
  // (undocumented)
  auth?: KubernetesRequestAuth;
  // (undocumented)
  entity: Entity;
}

// @public (undocumented)
export interface LimitRangeFetchResponse {
  // (undocumented)
  resources: Array<V1LimitRange>;
  // (undocumented)
  type: 'limitranges';
}

// @public (undocumented)
export interface ObjectsByEntityResponse {
  // (undocumented)
  items: ClusterObjects[];
}

// @public (undocumented)
export interface PodFetchResponse {
  // (undocumented)
  resources: Array<V1Pod>;
  // (undocumented)
  type: 'pods';
}

// @public (undocumented)
export interface PodStatusFetchResponse {
  // (undocumented)
  resources: Array<PodStatus>;
  // (undocumented)
  type: 'podstatus';
}

// @public (undocumented)
export interface RawFetchError {
  // (undocumented)
  errorType: 'FETCH_ERROR';
  // (undocumented)
  message: string;
}

// @public (undocumented)
export interface ReplicaSetsFetchResponse {
  // (undocumented)
  resources: Array<V1ReplicaSet>;
  // (undocumented)
  type: 'replicasets';
}

// @public (undocumented)
export interface ServiceFetchResponse {
  // (undocumented)
  resources: Array<V1Service>;
  // (undocumented)
  type: 'services';
}

// @public (undocumented)
export interface StatefulSetsFetchResponse {
  // (undocumented)
  resources: Array<V1StatefulSet>;
  // (undocumented)
  type: 'statefulsets';
}

// @public (undocumented)
export interface StatusError {
  // (undocumented)
  errorType: KubernetesErrorTypes;
  // (undocumented)
  resourcePath?: string;
  // (undocumented)
  statusCode?: number;
}

// @public (undocumented)
export interface WorkloadsByEntityRequest {
  // (undocumented)
  auth: KubernetesRequestAuth;
  // (undocumented)
  entity: Entity;
}
```