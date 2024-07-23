---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DnsAuditEvents
---


| Column | Type | Description |
|---|---|---|
| Action | string | If a query meets the criteria of a policy, the action is the response that the policy requires. |
| ActiveKey | string | Signing key of the KSK's active key. |
| AdditionalData | dynamic | Additional information not already scoped into its own dedicated field. |
| Base64Data | string | Key data. |
| _BilledSize | real | The record size in bytes |
| BufferSize | int | Size of the buffer used for logging the event data.(in bytes) |
| ChildZone | string | Name of a child zone. |
| ClientSubnetList | string | The list of IPv4 and IPv6 of the client subnet. |
| ClientSubnetRecord | string | Then name of the client subnet. |
| Condition | string | Specific circumstances or requirements that trigger certain actions or policies. |
| Criteria | string | Criteria or conditions that triggered the event. |
| CryptoAlgorithm | string | The cryptographic algorithm used for securing DNS-related operations. |
| CurrentRolloverStatus | string | The state of the key rollover process from one key to another. |
| CurrentState | string | The current status of a DNS key or zone. |
| DenialOfExistence | string | The method used to prove that a certain DNS record does not exist. |
| Digest | string | A secure fingerprint, allowing DNS resolvers to validate the authenticity of the trust anchor information. |
| DigestType | string | Specifies the type of cryptographic hash algorithm used for generating the digest (hash) value. |
| DistributeTrustAnchor | string | Relates to the distribution of a trust anchor for DNSSEC, which is a secure public key that helps in the validation of DNS data. |
| DnsKeyRecordSetTtl | int | The time-to-live (TTL) value assigned to DNSKEY records when signing a DNS zone. This value determines how long a DNSKEY record will be considered valid before it needs to be refreshed.  |
| DnsKeySignatureValidityPeriod | int | The duration in seconds that a DNSKEY record’s signature is considered valid. |
| DnsQuery | string | The domain that needs to be resolved. |
| DnsQueryType | int | The DNS resource record type codes as defined by the Internet Assigned Numbers Authority (IANA). |
| DSRecordGenerationAlgorithm | string | The algorithm used to generate the Delegation Signer (DS) record from the DNSKEY record. |
| DSRecordSetTtl | int | The time-to-live (TTL) value for the DS (Delegation Signer) record set. |
| DSSignatureValidityPeriod | int |  The period in seconds that a DS (Delegation Signer) record’s signature is considered valid. |
| EnableRfc5011KeyRollover | string | The process of automating the update and rollover of DNSSEC keys in accordance with RFC 5011 standards. |
| EventGuid | string | Unique identifier for the specific event. |
| EventId | string | Identifier for the underlying Windows event. |
| EventString | string | Human-readable description of the event. |
| EventType | string | Type of DNS event (e.g., zone transfer, dynamic update, DNSSEC signing). |
| FilePath | string | The location of a file or directory that the DNS server is interacting with. |
| Forwarders | string | DNS forwarders used by the server. |
| InitialRolloverOffset | int | The initial time delay (in seconds) before the first rollover action is triggered for a DNSSEC key. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsEnabled | string | This parameter indicates whether the policy or exception list is currently active. |
| IsKeyMasterServer | string | Whether the DNS server is the key master server for a DNSSEC-signed zone. |
| KeyId | string | The unique identifier of a DNSSEC signing key. |
| KeyLength | int | The length of the cryptographic key used in DNSSEC signing operations. |
| KeyMasterServer | string | The DNS server that is responsible for generating and managing the DNSSEC keys for a zone. |
| KeyOrZone | string | The signing key used for authentication and data integrity in a specific DNS zone. |
| KeyProtocol | string | Protocol used for DNSSEC key management (e.g., DNSKEY, DS). |
| KeyStorageProvider | string | The system or service that is responsible for securely storing the DNSSEC keys. |
| KeyTag | int | A numeric identifier for the cryptographic key used by the DS record. |
| KeyType | string | The type of DNSSEC signing key being used. |
| KskOrZsk | string | The type of signing key used in a specific DNS zone. |
| LastRolloverTime | datetime | The last time a rollover process took place. |
| ListenAddresses | string | IP addresses on which the DNS server listens. |
| LookupValue | string | Type of DNS lookup (e.g., recursive, iterative). |
| MasterServer | string | The primary DNS server from which a secondary DNS server obtains zone data. |
| Name | string | Specifies the domain name or hostname associated with a specific record. |
| NameServer | string | Name server responsible for the DNS event. |
| NewPropertyValues | string | The set of properties after they were updated for a specific policy or exception list in the DNS server or zone. |
| NewValue | string | The updated value assigned to a specific property key within the DNS zone. |
| NextKey | string | The upcoming key that will be used in the DNS zone signing process after the current active and standby keys. |
| NextRolloverAction | string | The rollover action performed. |
| NextRolloverTime | datetime | The next time a rollover process should happen. |
| NodeName | string | The node name within the DNS zone. |
| NSec3HashAlgorithm | int | The cryptographic hash algorithm used in the NSEC3 protocol for DNSSEC. |
| NSec3Iterations | int | The number of additional hashing iterations a DNSSEC-enabled DNS server uses. |
| NSec3OptOut | string | Indicates if the DNSSEC NSEC3 protocol is configured to allow unsigned delegations. |
| NSec3RandomSaltLength | int | The length of the random salt value used in the NSEC3 protocol for DNSSEC. |
| NSec3UserSalt | string | The user-defined salt value used in the NSEC3 protocol for DNSSEC. |
| OldPropertyValues | string | The set of properties before they were updated for a specific policy or exception list in the DNS server or zone. |
| ParentHasSecureDelegation | string | Whether the parent zone has a secure delegation to the child zone. |
| Policy | string | Defines rules or guidelines for managing specific aspects of DNS behavior. |
| ProcessingOrder | int | Determines the sequence in which policies are applied. |
| PropagationTime | int | Time taken for the event information to propagate. Duration (e.g., milliseconds) or “Immediate” if no delay. |
| PropertyKey | string | Specific property or setting affected by the event. |
| RDATA | string | Represents the data of the resource record that was created, deleted, or scavenged in the DNS zone. |
| RecursionScope | string | A specific area or set of conditions under which DNS recursion is allowed or applied on a DNS server. |
| ReplicationScope | string | Scope of DNS replication (e.g., forest-wide, domain-specific). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RolloverPeriod | int | Time interval for log rollover (e.g., daily, weekly). |
| RolloverType | string | Type of rollover (e.g., overwrite, append).  |
| ScavengeServers | string | Servers involved in DNS scavenging (aging and cleanup of stale records). |
| Scope | string | The scope of the event (e.g., server-wide, zone-specific). |
| Scopes | string | DNS scopes impacted by the event (e.g., global, local). |
| SecureDelegationPollingPeriod | int | Interval for polling secure delegation information. Numeric value (e.g., minutes) or “Disabled” if not applicable. |
| SeizedOrTransferred | string | Refers to the action taken, either a seizure (when control is forcibly transferred) or a voluntary transfer of the key master role. |
| ServerName | string | Represents the DNS server where the policy or exception list is being configured. |
| Setting | string | Specific DNS configuration setting modified by the event. |
| SignatureInceptionOffset | int | Offset time for DNSSEC signature inception. Duration (e.g., seconds) or “Immediate” if no delay. |
| Source | string | Source of the DNS event (e.g., server, client). |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StandbyKey | string | the backup key that will be used if the current active key is compromised or needs to be replaced in the DNS zone signing process. |
| StoreKeysInAD | string | Specifies whether the keys are stored in Active Directory Domain Services (AD DS). This setting applies only to Active Directory-integrated zones when the vendor of KeyStorageProvider is Microsoft. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubTreeAging | string | Mechanism that affects the aging (expiration) of DNS records within a specific subtree or branch of a DNS zone. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| TTL | int | The time-to-live for the DNS record, indicating how long the record should be cached before it is discarded or refreshed. |
| Type | string | The name of the table |
| VirtualizationID | string |  A unique key to manage and coordinate activities within the virtualized environment. |
| WithNewKeys | string | Indicates whether new DNSSEC keys were generated. |
| WithWithout | string | Whether key signing key (KSK) metadata is included or excluded when exporting DNSSEC settings for a specific zone. |
| Zone | string | The zone related to the activity. |
| ZoneFile | string | The name of the zone file. |
| ZoneName | string | The name of a DNS zone on which the zone which the event relates to. |
| ZoneScope | string | A list of scopes and weights for the zone. |
| ZoneSignatureValidityPeriod | int | The amount of time that signatures that cover all other record sets are valid. |
