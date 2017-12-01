---
UID: NS.hbaapi.HBA_FCPTargetMappingV2
title: HBA_FCPTargetMappingV2
author: windows-driver-content
description: The HBA_FCPTargetMappingV2 structure contains a variable length array of target mappings.
old-location: storage\hba_fcptargetmappingv2.htm
old-project: storage
ms.assetid: 2c241a38-c6b6-4c77-a8ba-be7ba2a8a701
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_FCPTargetMappingV2, HBA_FCPTARGETMAPPINGV2, *PHBA_FCPTARGETMAPPINGV2
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
req.alt-api: HBA_FCPTARGETMAPPINGV2
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
req.iface: 
---

# HBA_FCPTargetMappingV2 structure



## -description
<p>The HBA_FCPTargetMappingV2 structure contains a variable length array of target mappings. </p>


## -syntax

````
typedef struct HBA_FCPTargetMappingV2 {
  HBA_UINT32         NumberOfEntries;
  HBA_FCPSCSIENTRYV2 entry[1];
} HBA_FCPTARGETMAPPINGV2, *PHBA_FCPTARGETMAPPINGV2;
````


## -struct-fields
<dl>

### -field <b>NumberOfEntries</b>

<dd>
<p>Indicates the number of bindings.</p>
</dd>

### -field <b>entry</b>

<dd>
<p>Contains a variable length array of structures of type <a href="..\hbaapi\ns-hbaapi-hba-fcpscsientryv2.md">HBA_FcpScsiEntryV2</a> each of which defines a mapping between an operating system identifier, a logical unit ID descriptor (LUID) and the corresponding fibre channel protocol (FCP) identifier for a logical unit. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\hbaapi\nf-hbaapi-hba-getfcptargetmappingv2.md">HBA_GetFcpTargetMappingV2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FCPTargetMappingV2 structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
