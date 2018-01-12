---
UID: NS:wdfcompaniontarget._WDF_TASK_SEND_OPTIONS
title: _WDF_TASK_SEND_OPTIONS
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_send_options.htm
old-project: wdf
ms.assetid: cb2fd11c-c6a5-4499-a340-f96ffcfbbe0f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _WDF_TASK_SEND_OPTIONS, WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfcompaniontarget.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
req.umdf-ver: 
req.alt-api: WDF_TASK_SEND_OPTIONS
req.alt-loc: wdfcompaniontarget.h
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
req.typenames: WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS
req.product: Windows 10 or later.
---

# _WDF_TASK_SEND_OPTIONS structure



## -description
For internal use only.



## -syntax

````
typedef struct _WDF_TASK_SEND_OPTIONS {
  ULONG    Size;
  ULONG    Flags;
  LONGLONG Timeout;
} WDF_TASK_SEND_OPTIONS, *PWDF_TASK_SEND_OPTIONS;
````


## -struct-fields

### -field Size


### -field Flags


### -field Timeout


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.23

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfcompaniontarget.h</dt>
</dl>
</td>
</tr>
</table>