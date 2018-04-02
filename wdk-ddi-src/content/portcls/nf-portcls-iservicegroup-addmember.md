---
UID: NF:portcls.IServiceGroup.AddMember
title: IServiceGroup::AddMember method
author: windows-driver-content
description: The AddMember method adds a member to the service group.
old-location: audio\iservicegroup_addmember.htm
old-project: audio
ms.assetid: 1eddb631-db85-4243-89a4-a4ab042cee28
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: AddMember method [Audio Devices], AddMember method [Audio Devices], IServiceGroup interface, AddMember,IServiceGroup.AddMember, IServiceGroup, IServiceGroup interface [Audio Devices], AddMember method, IServiceGroup::AddMember, audio.iservicegroup_addmember, audmp-routines_0d318d56-28e9-4e42-84b3-1d0eb4110f71.xml, portcls/IServiceGroup::AddMember
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IServiceGroup.AddMember
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IServiceGroup::AddMember method
The <code>AddMember</code> method adds a member to the service group.

## Syntax

```
NTSTATUS AddMember(
  PSERVICESINK pServiceSink
);
```

## Parameters

`pServiceSink`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a> interface of the new member of the service group


## Return Value

<code>AddMember</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

The <code>AddMember</code> method calls <b>AddRef</b> on the <i>pServiceSink</i> object. When the object is later removed, the <b>RemoveMember</b> method calls <b>Release</b> on the <i>pServiceSink</i> object. This behavior is in accordance with the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a>