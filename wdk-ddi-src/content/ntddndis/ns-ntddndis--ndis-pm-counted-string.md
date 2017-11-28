---
UID: NS.ntddndis._NDIS_PM_COUNTED_STRING
title: NDIS_PM_COUNTED_STRING
author: windows-driver-content
description: The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management structures.
old-location: netvista\ndis_pm_counted_string.htm
old-project: netvista
ms.assetid: 070ee8e2-80ed-4380-89ac-bfb5db2bcf7e
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING
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
req.iface: 
---

# NDIS_PM_COUNTED_STRING structure



## -description
<p>The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management
  structures.</p>


## -syntax

````
typedef struct _NDIS_PM_COUNTED_STRING {
  USHORT Length;
  WCHAR  String[NDIS_PM_MAX_STRING_SIZE + 1];
} NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING;
````


## -struct-fields
<dl>

### -field <b>Length</b>

<dd>
<p>The length, in bytes, of the string.</p>
</dd>

### -field <b>String</b>

<dd>
<p>A WCHAR array that contains a NULL-terminated string that is limited to a maximum size of
     NDIS_PM_MAX_STRING_SIZE.</p>
</dd>
</dl>

## -remarks
<p>The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566768">NDIS_PM_WOL_PATTERN</a> power management
    structures to define name strings.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566768">NDIS_PM_WOL_PATTERN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PM_COUNTED_STRING structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
