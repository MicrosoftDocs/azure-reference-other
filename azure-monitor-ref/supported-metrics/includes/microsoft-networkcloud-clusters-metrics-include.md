---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkCloud/clusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|API Server|**APIServer Audit Requests Rejected Total**<p><p>Counter of API server requests rejected due to an error in the audit logging backend |`ApiserverAuditRequestsRejectedTotal` |Count |Average |`Component`, `Pod Name`|PT1M |No|
|API Server|**APIServer Clnt Cert Exp Sec Sum (Preview)**<p><p>Sum of API server client certificate expiration (seconds) |`ApiserverClientCertificateExpirationSecondsSum` |Seconds |Average |`Component`, `Pod Name`|PT1M |No|
|API Server|**APIServer Storage Data Key Gen Fail**<p><p>Total number of operations that failed Data Encryption Key (DEK) generation |`ApiserverStorageDataKeyGenerationFailuresTotal` |Count |Average |`Component`, `Pod Name`|PT1M |No|
|API Server|**APIServer TLS Handshake Err (Preview)**<p><p>Number of requests dropped with 'TLS handshake' error |`ApiserverTlsHandshakeErrorsTotal` |Count |Average |`Component`, `Pod Name`|PT1M |No|
|Container|**Container FS I/O Time Seconds Total (Preview)**<p><p>Time taken for container Input/Output (I/O) operations |`ContainerFsIoTimeSecondsTotal` |Seconds |Average |`Device`, `Host`|PT1M |No|
|Container|**Container Memory Fail Count**<p><p>Number of times a container's memory usage limit is hit |`ContainerMemoryFailcnt` |Count |Average |`Container`, `Host`, `Namespace`, `Pod`|PT1M |No|
|Container|**Container Memory Usage Bytes**<p><p>Current memory usage, including all memory regardless of when it was accessed |`ContainerMemoryUsageBytes` |Bytes |Average |`Container`, `Host`, `Namespace`, `Pod`|PT1M |No|
|Container|**Container Net Rx Errors (Preview)**<p><p>Number of errors encountered while receiving bytes over the network |`ContainerNetworkReceiveErrorsTotal` |Count |Average |`Interface`, `Namespace`, `Pod`|PT1M |No|
|Container|**Container Net Tx Err Total (Preview)**<p><p>Count of errors that happened while transmitting |`ContainerNetworkTransmitErrorsTotal` |Count |Average |`Interface`, `Namespace`, `Pod`|PT1M |No|
|Container|**Container Scrape Error**<p><p>Indicates whether there was an error while getting container metrics |`ContainerScrapeError` |Unspecified |Average |`Host`|PT1M |No|
|Container|**Container Tasks State**<p><p>Number of tasks or processes in a given state (sleeping, running, stopped, uninterruptible, or waiting) in a container |`ContainerTasksState` |Count |Average |`Container`, `Host`, `Namespace`, `Pod`, `State`|PT1M |No|
|Controller|**Controller Reconcile Errors Total**<p><p>Total number of reconciliation errors per controller |`ControllerRuntimeReconcileErrorsTotal` |Count |Average |`Controller`, `Namespace`, `Pod Name`|PT1M |No|
|Controller|**Controller Reconciliations Total**<p><p>Total number of reconciliations per controller |`ControllerRuntimeReconcileTotal` |Count |Average |`Controller`, `Namespace`, `Pod Name`|PT1M |No|
|CoreDNS|**CoreDNS Requests Total**<p><p>Total number of DNS requests |`CorednsDnsRequestsTotal` |Count |Average |`Family`, `Pod Name`, `Proto`, `Server`, `Type`|PT1M |No|
|CoreDNS|**CoreDNS Responses Total**<p><p>Total number of DNS responses |`CorednsDnsResponsesTotal` |Count |Average |`Pod Name`, `Server`, `Rcode`|PT1M |No|
|CoreDNS|**CoreDNS Frwd Hlthchk Broken (Preview)**<p><p>Total number of times all upstreams are unhealthy |`CorednsForwardHealthcheckBrokenTotal` |Count |Average |`Pod Name`, `Namespace`|PT1M |No|
|CoreDNS|**CoreDNS Frwd Max Concurrent Rejects (Preview)**<p><p>Total number of rejected queries because concurrent queries were at the maximum limit |`CorednsForwardMaxConcurrentRejectsTotal` |Count |Average |`Pod Name`, `Namespace`|PT1M |No|
|CoreDNS|**CoreDNS Health Request Failures Total**<p><p>The number of times the self health check failed |`CorednsHealthRequestFailuresTotal` |Count |Average |`Pod Name`|PT1M |No|
|CoreDNS|**CoreDNS Panics Total**<p><p>Total number of panics |`CorednsPanicsTotal` |Count |Average |`Pod Name`|PT1M |No|
|CoreDNS|**CoreDNS Reload Failed Total**<p><p>Total number of failed reload attempts |`CorednsReloadFailedTotal` |Count |Average |`Pod Name`, `Namespace`|PT1M |No|
|Etcd|**Etcd Disk Backend Commit Duration Sec**<p><p>The latency distribution of commits called by the backend |`EtcdDiskBackendCommitDurationSecondsSum` |Seconds |Total |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Disk WAL Fsync Duration Sec**<p><p>The sum of latency distributions of 'fsync' called by the write-ahead log (WAL) |`EtcdDiskWalFsyncDurationSecondsSum` |Seconds |Total |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Health Failures**<p><p>Total server health failures |`EtcdServerHealthFailures` |Count |Average |`Pod Name`|PT1M |No|
|Etcd|**Etcd Server Is Leader**<p><p>Whether or not this member is a leader; 1 if is, 0 otherwise |`EtcdServerIsLeader` |Unspecified |Count |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Is Learner**<p><p>Whether or not this member is a learner; 1 if is, 0 otherwise |`EtcdServerIsLearner` |Unspecified |Count |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Leader Changes Seen Total**<p><p>The number of leader changes seen |`EtcdServerLeaderChangesSeenTotal` |Count |Average |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Proposals Applied Total**<p><p>The total number of consensus proposals applied |`EtcdServerProposalsAppliedTotal` |Count |Average |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Proposals Committed Total**<p><p>The total number of consensus proposals committed |`EtcdServerProposalsCommittedTotal` |Count |Average |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Proposals Failed Total**<p><p>The total number of failed proposals |`EtcdServerProposalsFailedTotal` |Count |Average |`Component`, `Pod Name`, `Tier`|PT1M |No|
|Etcd|**Etcd Server Slow Apply Total (Preview)**<p><p>The total number of slow apply requests |`EtcdServerSlowApplyTotal` |Count |Average |`Pod Name`, `Tier`|PT1M |No|
|Calico|**Felix Active Local Endpoints**<p><p>Number of active endpoints on this host |`FelixActiveLocalEndpoints` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Cluster Num Host Endpoints**<p><p>Total number of host endpoints cluster-wide |`FelixClusterNumHostEndpoints` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Cluster Number of Hosts**<p><p>Total number of Calico hosts in the cluster |`FelixClusterNumHosts` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Cluster Nmbr Workload Endpoints**<p><p>Total number of workload endpoints cluster-wide |`FelixClusterNumWorkloadEndpoints` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Interface Dataplane Failures**<p><p>Number of times dataplane updates failed and will be retried |`FelixIntDataplaneFailures` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Ipset Errors**<p><p>Number of 'ipset' command failures |`FelixIpsetErrors` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Ipsets Calico**<p><p>Number of active Calico IP sets |`FelixIpsetsCalico` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix IP Tables Restore Errors**<p><p>Number of 'iptables-restore' errors |`FelixIptablesRestoreErrors` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix IP Tables Save Errors**<p><p>Number of 'iptables-save' errors |`FelixIptablesSaveErrors` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Resyncs Started**<p><p>Number of times Felix has started resyncing with the datastore |`FelixResyncsStarted` |Count |Average |`Host`|PT1M |No|
|Calico|**Felix Resync State**<p><p>Current datastore state |`FelixResyncState` |Unspecified |Average |`Host`|PT1M |No|
|Daemonset|**Daemonsets Current Number Scheduled**<p><p>Number of daemonsets currently scheduled |`KubeDaemonsetStatusCurrentNumberScheduled` |Count |Average |`Daemonset`, `Namespace`|PT1M |No|
|Daemonset|**Daemonsets Desired Number Scheduled**<p><p>Number of daemonsets desired scheduled |`KubeDaemonsetStatusDesiredNumberScheduled` |Count |Average |`Daemonset`, `Namespace`|PT1M |No|
|Daemonset|**Daemonsets Not Scheduled**<p><p>Number of daemonsets not scheduled |`KubeDaemonsetStatusNotScheduled` |Count |Average |`Daemonset`, `Namespace`|PT1M |No|
|Deployment|**Deployment Replicas Available**<p><p>Number of deployment replicas available |`KubeDeploymentStatusReplicasAvailable` |Count |Average |`Deployment`, `Namespace`|PT1M |No|
|Deployment|**Deployment Replicas Available Percent**<p><p>Percentage of deployment replicas available |`KubeDeploymentStatusReplicasAvailablePercent` |Percent |Average |`Deployment`, `Namespace`|PT1M |No|
|Deployment|**Deployment Replicas Ready**<p><p>Number of deployment replicas ready |`KubeDeploymentStatusReplicasReady` |Count |Average |`Deployment`, `Namespace`|PT1M |No|
|Deployment|**Deployment Replicas Unavailable**<p><p>Number of deployment replicas unavailable |`KubeDeploymentStatusReplicasUnavailable` |Count |Average |`Deployment`, `Namespace`|PT1M |No|
|Job|**Jobs Active**<p><p>Number of jobs active |`KubeJobStatusActive` |Count |Average |`Job`, `Namespace`|PT1M |No|
|Job|**Jobs Failed**<p><p>Number and reason of jobs failed |`KubeJobStatusFailed` |Count |Average |`Job`, `Namespace`, `Reason`|PT1M |No|
|Job|**Jobs Succeeded**<p><p>Number of jobs succeeded |`KubeJobStatusSucceeded` |Count |Average |`Job`, `Namespace`|PT1M |No|
|Kubelet|**Kubelet Running Containers**<p><p>Number of containers currently running |`KubeletRunningContainers` |Count |Average |`Container State`, `Host`|PT1M |No|
|Kubelet|**Kubelet Running Pods**<p><p>Number of pods running on the node |`KubeletRunningPods` |Count |Average |`Host`|PT1M |No|
|Kubelet|**Kubelet Runtime Operations Errors Total**<p><p>Cumulative number of runtime operation errors by operation type |`KubeletRuntimeOperationsErrorsTotal` |Count |Average |`Host`, `Operation Type`|PT1M |No|
|Kubelet|**Kubelet Started Pods Errors Total**<p><p>Cumulative number of errors when starting pods |`KubeletStartedPodsErrorsTotal` |Count |Average |`Host`|PT1M |No|
|Kubelet|**Volume Available Bytes**<p><p>Number of available bytes in the volume |`KubeletVolumeStatsAvailableBytes` |Bytes |Average |`Host`, `Namespace`, `Persistent Volume Claim`|PT1M |No|
|Kubelet|**Volume Capacity Bytes**<p><p>Capacity (in bytes) of the volume |`KubeletVolumeStatsCapacityBytes` |Bytes |Average |`Host`, `Namespace`, `Persistent Volume Claim`|PT1M |No|
|Kubelet|**Volume Used Bytes**<p><p>Number of used bytes in the volume |`KubeletVolumeStatsUsedBytes` |Bytes |Average |`Host`, `Namespace`, `Persistent Volume Claim`|PT1M |No|
|Node|**Node Resources Allocatable**<p><p>Node resources allocatable for pods |`KubeNodeStatusAllocatable` |Count |Average |`Node`, `Resource`, `Unit`|PT1M |No|
|Node|**Node Resources Capacity**<p><p>Total amount of node resources available |`KubeNodeStatusCapacity` |Count |Average |`Node`, `Resource`, `Unit`|PT1M |No|
|Node|**Node Status Condition**<p><p>The condition of a node |`KubeNodeStatusCondition` |Count |Average |`Condition`, `Node`, `Status`|PT1M |No|
|Pod|**Container Resources Limits**<p><p>The container's resources limits |`KubePodContainerResourceLimits` |Count |Average |`Container`, `Namespace`, `Node`, `Pod`, `Resource`, `Unit`|PT1M |No|
|Pod|**Container Resources Requests**<p><p>The container's resources requested |`KubePodContainerResourceRequests` |Count |Average |`Container`, `Namespace`, `Node`, `Pod`, `Resource`, `Unit`|PT1M |No|
|Pod|**Container State Started (Preview)**<p><p>Unix timestamp start time of a container |`KubePodContainerStateStarted` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Status Last Terminated Reason**<p><p>The reason of a container's last terminated status |`KubePodContainerStatusLastTerminatedReason` |Count |Average |`Container`, `Namespace`, `Pod`, `Reason`|PT1M |No|
|Pod|**Container Status Ready**<p><p>Describes whether the container's readiness check succeeded |`KubePodContainerStatusReady` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Restarts**<p><p>The number of container restarts |`KubePodContainerStatusRestartsTotal` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Status Running**<p><p>The number of containers with a status of 'running' |`KubePodContainerStatusRunning` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Status Terminated**<p><p>The number of containers with a status of 'terminated' |`KubePodContainerStatusTerminated` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Status Terminated Reason**<p><p>The number and reason of containers with a status of 'terminated' |`KubePodContainerStatusTerminatedReason` |Count |Average |`Container`, `Namespace`, `Pod`, `Reason`|PT1M |No|
|Pod|**Container Status Waiting**<p><p>The number of containers with a status of 'waiting' |`KubePodContainerStatusWaiting` |Count |Average |`Container`, `Namespace`, `Pod`|PT1M |No|
|Pod|**Container Status Waiting Reason**<p><p>The number and reason of containers with a status of 'waiting' |`KubePodContainerStatusWaitingReason` |Count |Average |`Container`, `Namespace`, `Pod`, `Reason`|PT1M |No|
|Pod|**Pod Deletion Timestamp (Preview)**<p><p>The timestamp of the pod's deletion |`KubePodDeletionTimestamp` |Count |Average |`Namespace`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Ready**<p><p>The number of ready pod init containers |`KubePodInitContainerStatusReady` |Count |Average |`Namespace`, `Container`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Restarts**<p><p>The number of pod init containers restarts |`KubePodInitContainerStatusRestartsTotal` |Count |Average |`Namespace`, `Container`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Running**<p><p>The number of running pod init containers |`KubePodInitContainerStatusRunning` |Count |Average |`Namespace`, `Container`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Terminated**<p><p>The number of terminated pod init containers |`KubePodInitContainerStatusTerminated` |Count |Average |`Namespace`, `Container`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Terminated Reason**<p><p>The number of pod init containers with terminated reason |`KubePodInitContainerStatusTerminatedReason` |Count |Average |`Namespace`, `Container`, `Pod`, `Reason`|PT1M |No|
|Pod|**Pod Init Container Waiting**<p><p>The number of pod init containers waiting |`KubePodInitContainerStatusWaiting` |Count |Average |`Namespace`, `Container`, `Pod`|PT1M |No|
|Pod|**Pod Init Container Waiting Reason**<p><p>The reason the pod init container is waiting |`KubePodInitContainerStatusWaitingReason` |Count |Average |`Namespace`, `Container`, `Pod`, `Reason`|PT1M |No|
|Pod|**Pod Status Phase**<p><p>The pod status phase |`KubePodStatusPhase` |Count |Average |`Namespace`, `Pod`, `Phase`|PT1M |No|
|Pod|**Pod Ready State**<p><p>Signifies if the pod is in ready state |`KubePodStatusReady` |Count |Average |`Namespace`, `Pod`|PT1M |No|
|Pod|**Pod Status Reason**<p><p>NodeAffinity |`KubePodStatusReason` |Count |Average |`Namespace`, `Pod`, `Reason`|PT1M |No|
|Statefulset|**Statefulset Desired Replicas Number**<p><p>The desired number of statefulset replicas |`KubeStatefulsetReplicas` |Count |Average |`Namespace`, `Statefulset`|PT1M |No|
|Statefulset|**Statefulset Replicas Number**<p><p>The number of replicas per statefulset |`KubeStatefulsetStatusReplicas` |Count |Average |`Namespace`, `Statefulset`|PT1M |No|
|VMOrchestrator|**Kubevirt Info**<p><p>Kubevirt version information |`KubevirtInfo` |Unspecified |Average |`Kube Version`|PT1M |No|
|VMOrchestrator|**Kubevirt Virt Controller Leading**<p><p>Indication for an operating virt-controller |`KubevirtVirtControllerLeading` |Unspecified |Average |`Pod Name`|PT1M |No|
|VMOrchestrator|**Kubevirt Virt Controller Ready**<p><p>Indication for a virt-controller that is ready to take the lead |`KubevirtVirtControllerReady` |Unspecified |Average |`Pod Name`|PT1M |No|
|VMOrchestrator|**Kubevirt Virt Operator Ready**<p><p>Indication for a virt operator being ready |`KubevirtVirtOperatorReady` |Unspecified |Average |`Pod Name`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Memory Balloon Bytes**<p><p>Current balloon size (in bytes) |`KubevirtVmiMemoryActualBalloonBytes` |Bytes |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Memory Available Bytes**<p><p>Amount of usable memory as seen by the domain. This value may not be accurate if a balloon driver is in use or if the guest OS does not initialize all assigned pages |`KubevirtVmiMemoryAvailableBytes` |Bytes |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Mem Dom Bytes (Preview)**<p><p>The amount of memory (in bytes) allocated to the domain. The memory value in domain XML file |`KubevirtVmiMemoryDomainBytesTotal` |Bytes |Average |`Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Mem Swp In Traffic Bytes**<p><p>The total amount of data read from swap space of the guest (in bytes) |`KubevirtVmiMemorySwapInTrafficBytesTotal` |Bytes |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Mem Swp Out Traffic Bytes**<p><p>The total amount of memory written out to swap space of the guest (in bytes) |`KubevirtVmiMemorySwapOutTrafficBytesTotal` |Bytes |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Memory Unused Bytes**<p><p>The amount of memory left completely unused by the system. Memory that is available but used for reclaimable caches should NOT be reported as free |`KubevirtVmiMemoryUnusedBytes` |Bytes |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Memory Usage**<p><p>The amount of memory used in percentage |`KubevirtVmiMemoryUsage` |Percent |Average |`Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Net Rx Packets**<p><p>Total network traffic received packets |`KubevirtVmiNetworkReceivePacketsTotal` |Bytes |Average |`Interface`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Net Tx Packets Drop**<p><p>The total number of transmit packets dropped on virtual NIC (vNIC) interfaces |`KubevirtVmiNetworkTransmitPacketsDroppedTotal` |Bytes |Average |`Interface`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Net Tx Packets Total**<p><p>Total network traffic transmitted packets |`KubevirtVmiNetworkTransmitPacketsTotal` |Bytes |Average |`Interface`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Outdated Count**<p><p>Indication for the total number of VirtualMachineInstance (VMI) workloads that are not running within the most up-to-date version of the virt-launcher environment |`KubevirtVmiOutdatedCount` |Count |Average |`Name`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Phase Count**<p><p>Sum of VirtualMachineInstances (VMIs) per phase and node |`KubevirtVmiPhaseCount` |Count |Average |`Node`, `Phase`, `Workload`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Storage IOPS Read Total**<p><p>Total number of Input/Output (I/O) read operations |`KubevirtVmiStorageIopsReadTotal` |Count |Average |`Drive`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Storage IOPS Write Total**<p><p>Total number of Input/Output (I/O) write operations |`KubevirtVmiStorageIopsWriteTotal` |Count |Average |`Drive`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Storage Read Times Total (Preview)**<p><p>Total time in milliseconds (ms) spent on read operations |`KubevirtVmiStorageReadTimesMsTotal` |Milliseconds |Average |`Drive`, `Name`, `Node`|PT1M |No|
|VMOrchestrator|**Kubevirt VMI Storage Write Times Total (Preview)**<p><p>Total time in milliseconds (ms) spent on write operations |`KubevirtVmiStorageWriteTimesMsTotal` |Milliseconds |Average |`Drive`, `Name`, `Node`|PT1M |No|
|Network Cloud|**CPU Pinning Map (Preview)**<p><p>Pinning map of virtual CPUs (vCPUs) to CPUs |`NcVmiCpuAffinity` |Count |Average |`CPU`, `NUMA Node`, `VMI Namespace`, `VMI Node`, `VMI Name`|PT1M |No|
|Calico|**Typha Client Latency Secs**<p><p>Per-client latency. I.e. how far behind the current state each client is. |`TyphaClientLatencySecsCount` |Count |Average |`Pod Name`|PT1M |No|
|Calico|**Typha Connections Accepted**<p><p>Total number of connections accepted over time |`TyphaConnectionsAccepted` |Count |Average |`Pod Name`|PT1M |No|
|Calico|**Typha Connections Dropped**<p><p>Total number of connections dropped due to rebalancing |`TyphaConnectionsDropped` |Count |Average |`Pod Name`|PT1M |No|
|Calico|**Typha Ping Latency**<p><p>Round-trip ping/pong latency to client. Typha's protocol includes a regular ping/pong keepalive to verify that the connection is still up |`TyphaPingLatencyCount` |Count |Average |`Pod Name`|PT1M |No|