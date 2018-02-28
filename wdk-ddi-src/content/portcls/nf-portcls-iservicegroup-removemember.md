---
UID: NF:portcls.IServiceGroup.RemoveMember
title: IServiceGroup::RemoveMember method
author: windows-driver-content
description: The RemoveMember method removes the specified member from the service group.
old-location: audio\iservicegroup_removemember.htm
old-project: audio
ms.assetid: f257c861-036b-44d1-9f99-dc5c0ab6e715
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IServiceGroup, IServiceGroup interface [Audio Devices], RemoveMember method, IServiceGroup::RemoveMember, RemoveMember method [Audio Devices], RemoveMember method [Audio Devices], IServiceGroup interface, RemoveMember,IServiceGroup.RemoveMember, audio.iservicegroup_removemember, audmp-routines_0b3fd59f-9233-4344-aa0c-f58505eee693.xml, portcls/IServiceGroup::RemoveMember
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
req.lib: portcls.h
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
-	IServiceGroup.RemoveMember
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# RemoveMember method
The <code>RemoveMember</code> method removes the specified member from the service group.

## Syntax

````
void RemoveMember(
  [in] PSERVICESINK pServiceSink
);
````

## Parameters

`pServiceSink`

Pointer to the <a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> interface of the member that is to be removed


## Return Value

None

## Remarks

The <code>RemoveMember</code> method removes a service sink that was previously added to the service group by an <b>AddMember</b> call. The <b>AddMember</b> method called <b>AddRef</b> on the service sink object, and the <code>RemoveMember</code> method calls <b>Release</b> on the service sink object. This behavior is in accordance with the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IServiceGroup::RemoveMember method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>