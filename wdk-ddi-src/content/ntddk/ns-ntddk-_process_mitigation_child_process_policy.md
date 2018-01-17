---
UID: NS:ntddk._PROCESS_MITIGATION_CHILD_PROCESS_POLICY
title: _PROCESS_MITIGATION_CHILD_PROCESS_POLICY
author: windows-driver-content
description: Stores policy information about creating child processes.
old-location: kernel\process_mitigation_child_process_policy.htm
old-project: kernel
ms.assetid: 8f388c0e-41ee-40e4-b633-687eeff74a0a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PROCESS_MITIGATION_CHILD_PROCESS_POLICY, PROCESS_MITIGATION_CHILD_PROCESS_POLICY, *PPROCESS_MITIGATION_CHILD_PROCESS_POLICY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PROCESS_MITIGATION_CHILD_PROCESS_POLICY
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PROCESS_MITIGATION_CHILD_PROCESS_POLICY, *PPROCESS_MITIGATION_CHILD_PROCESS_POLICY
---

# _PROCESS_MITIGATION_CHILD_PROCESS_POLICY structure



## -description
Stores policy information about creating child processes.



## -syntax

````
typedef struct _PROCESS_MITIGATION_CHILD_PROCESS_POLICY {
  union {
    struct {
      ULONG NoChildProcessCreation  :1;
      ULONG AuditNoChildProcessCreation  :1;
      ULONG AllowSecureProcessCreation  :1;
      ULONG ReservedFlags  :29;
    } DUMMYSTRUCTNAME;
  } DUMMYUNIONNAME;
} PROCESS_MITIGATION_CHILD_PROCESS_POLICY, PROCESS_MITIGATION_CHILD_PROCESS_POLICY;
````


## -struct-fields

### -field DUMMYUNIONNAME


### -field DUMMYSTRUCTNAME


### -field NoChildProcessCreation

If set, the process cannot create child processes.


### -field AuditNoChildProcessCreation

If set, causes audit events to be generated when child processes are created by the process. If both <b>NoChildProcessCreation</b> and <b>AuditNoChildProcessCreation</b> are set, <b>NoChildProcessCreation</b> takes precedence over audit setting.


### -field AllowSecureProcessCreation

Denies creation of child processes unless the child process is a secure process and if creation was previously blocked. It allows a process to spawn a child process on behalf of another process that cannot itself create child processes. See PROCESS_CREATION_CHILD_PROCESS_OVERRIDE in <a href="https://msdn.microsoft.com/5fc3e04f-9b2a-440c-a9aa-d78d9b25b341">UpdateProcThreadAttribute</a>.


### -field ReservedFlags

Reserved.

</dd>
</dl>
</dd>
</dl>

## -remarks
