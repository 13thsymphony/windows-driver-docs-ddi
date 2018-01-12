---
UID: NS:ntddndis._NDIS_PM_COUNTED_STRING
title: _NDIS_PM_COUNTED_STRING
author: windows-driver-content
description: The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management structures.
old-location: netvista\ndis_pm_counted_string.htm
old-project: netvista
ms.assetid: 070ee8e2-80ed-4380-89ac-bfb5db2bcf7e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PM_COUNTED_STRING
req.alt-loc: ntddndis.h
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
req.typenames: NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING
---

# _NDIS_PM_COUNTED_STRING structure



## -description
The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management
  structures.



## -syntax

````
typedef struct _NDIS_PM_COUNTED_STRING {
  USHORT Length;
  WCHAR  String[NDIS_PM_MAX_STRING_SIZE + 1];
} NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING;
````


## -struct-fields

### -field Length

The length, in bytes, of the string.


### -field String

A WCHAR array that contains a NULL-terminated string that is limited to a maximum size of
     NDIS_PM_MAX_STRING_SIZE.


## -remarks
The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a> and 
    <a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a> power management
    structures to define name strings.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ntddndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_pm_protocol_offload.md">NDIS_PM_PROTOCOL_OFFLOAD</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PM_COUNTED_STRING structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

