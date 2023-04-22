Introducing access modes
As the name suggests, access modes are an option you can set when you create a 
PersistentVolume type that will tell Kubernetes how the volume should be mounted. 
PersistentVolumes supports three access modes, as follows:
• ReadWriteOnce: This volume allows read/write by only one Node at the same 
time.
• ReadOnlyMany: This volume allows read-only mode by many Nodes at the same 
time.
• ReadWriteMany: This volume allows read/write by multiple Nodes at the same 
time