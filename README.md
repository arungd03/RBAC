# RBAC
ClusterRole

What is RBAC?
RBAC is a system that provides fine-grained access control to Kubernetes resources. It determines who (user or ServiceAccount) can perform what actions (verbs) on which resources.

ServiceAccount
--------------
A ServiceAccount in Kubernetes is used by applications running in Pods to interact with the Kubernetes API. Every Pod has a ServiceAccount associated with it, and it determines the API permissions for that Pod.

Default ServiceAccount
----------------------
-> Kubernetes automatically creates a default ServiceAccount in every namespace.
-> If no ServiceAccount is explicitly assigned, the default one is used.

Custom ServiceAccount
---------------------
You can create a custom ServiceAccount to assign specific permissions for workloads.

ClusterRole
-----------
-> A ClusterRole defines permissions (verbs) for cluster-scoped resources (e.g., nodes, persistentvolumes) or for namespace-scoped resources across all namespaces.

RoleBinding
-----------
-> A RoleBinding associates a Role or ClusterRole with users, groups, or ServiceAccounts. When binding to a ClusterRole, the permissions can be applied in a namespace-specific scope.

Using ServiceAccount with ClusterRole and RoleBinding
-----------------------------------------------------
Let’s see how to combine these concepts with an example.

Objective
---------
Create a ServiceAccount.
Assign a ClusterRole with permissions to list pods in all namespaces.
Bind the ClusterRole to the ServiceAccount using a RoleBinding.
