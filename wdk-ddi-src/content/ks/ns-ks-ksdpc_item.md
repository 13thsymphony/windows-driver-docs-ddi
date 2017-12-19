---
UID: NS.KS.KSDPC_ITEM
title: KSDPC_ITEM
author: windows-driver-content
description: The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL.
old-location: stream\ksdpc_item.htm
old-project: stream
ms.assetid: 7732b1a8-4f76-49d0-acbf-ce0be6b36858
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSDPC_ITEM, PKSDPC_ITEM, KSDPC_ITEM, *PKSDPC_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSDPC_ITEM
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# KSDPC_ITEM structure



## -description
The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL.



## -syntax

````
typedef struct {
  KDPC       Dpc;
  ULONG      ReferenceCount;
  KSPIN_LOCK AccessLock;
} KSDPC_ITEM, *PKSDPC_ITEM;
````


## -struct-fields

### -field Dpc

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is queued to perform notifications that cannot occur at raised IRQL.


### -field ReferenceCount

Specifies whether pending DPCs will reference this structure. This is initially set to 1 when the event structure is created, and decremented when the event structure is destroyed. If the reference count is nonzero at that time, then the last DPC to run frees the structure rather than the event disable call.


### -field AccessLock

This lock is used to synchronize deletion of an event item with any DPC that might be running.


## -remarks
KSDPC_ITEM uses a reference counting scheme to determine when to free the structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDPC_ITEM structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

