---
UID: NS.HBAAPI.HBA_FCPTARGETMAPPING
title: HBA_FCPTargetMapping
author: windows-driver-content
description: The HBA_FCPTargetMapping structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of target devices.
old-location: storage\hba_fcptargetmapping.htm
old-project: storage
ms.assetid: 666f4aea-2fcb-46cf-8d25-d1322c0517c9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: HBA_FCPTargetMapping, HBA_FCPTARGETMAPPING, *PHBA_FCPTARGETMAPPING, PHBA_FCPTARGETMAPPING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_FCPTARGETMAPPING
req.alt-loc: hbaapi.h
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

# HBA_FCPTargetMapping structure



## -description
The HBA_FCPTargetMapping structure contains an array of bindings between operating system and fibre channel protocol (FCP) identifiers for a set of target devices. 



## -syntax

````
typedef struct HBA_FCPTargetMapping {
  HBA_UINT32       NumberOfEntries;
  HBA_FCPSCSIENTRY entry[1];
} HBA_FCPTARGETMAPPING, *PHBA_FCPTARGETMAPPING;
````


## -struct-fields

### -field NumberOfEntries

Indicates the number of bindings.


### -field entry

Contains a variable length array of structures of type <a href="..\hbaapi\ns-hbaapi-hba_fcpscsientry.md">HBA_FcpScsiEntry</a> each of which defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_fcpscsientry.md">HBA_FcpScsiEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FCPTargetMapping structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

