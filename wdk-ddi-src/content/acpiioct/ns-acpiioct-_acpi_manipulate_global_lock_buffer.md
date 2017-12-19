---
UID: NS.ACPIIOCT._ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
title: _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
author: windows-driver-content
description: This topic describes the ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure.
old-location: acpi\acpi_manipulate_global_lock_buffer.htm
old-project: acpi
ms.assetid: 841CC16D-BDFC-4A3F-9DDD-940A591EBEF2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, *PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER
req.alt-loc: Acpiioct.h
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

# _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER structure



## -description
This topic describes the  <b>ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER</b> structure.



## -syntax

````
typedef struct _ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER {
  ULONG Signature;
  PVOID LockObject;
} ACPI_MANIPULATE_GLOBAL_LOCK_BUFFER, *PACPI_MANIPULATE_GLOBAL_LOCK_BUFFER;
````


## -struct-fields

### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.


### -field LockObject

Defines the <b>PVOID</b> member <b>LockObject</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>