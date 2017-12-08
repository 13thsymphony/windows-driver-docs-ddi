---
UID: NS.hbaapi.HBA_fc4types
title: HBA_fc4types
author: windows-driver-content
description: The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports.
old-location: storage\hba_fc4types.htm
old-project: storage
ms.assetid: ef043a97-3ef4-4fd3-93a6-ac1621503713
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_fc4types, HBA_FC4TYPES, *PHBA_FC4TYPES
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
req.alt-api: HBA_FC4TYPES
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

# HBA_fc4types structure



## -description
<p>The HBA_fc4types structure contains a set of up to 32 values indicating the FC-4 types that the HBA supports. </p>


## -syntax

````
typedef struct HBA_fc4types {
  HBA_UINT8 bits[32];
} HBA_FC4TYPES, *PHBA_FC4TYPES;
````


## -struct-fields
<dl>

### -field bits

<dd>
<p>Contains 32 bytes of FC4 type information. Each byte indicates a support FC-4 type. For a complete list of the values that can be assigned to this member, see .the T11 committee's <i>Fibre Channel Generic Services -4 (FC-GS-4) </i>specification.</p>
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
<a href="..\hbaapi\ns-hbaapi-hba-portattributes.md">HBA_PortAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_fc4types structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
