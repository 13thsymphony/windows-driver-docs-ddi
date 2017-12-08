---
UID: NS.NTDDVDEO._DXGK_WIN32K_PARAM_DATA
title: _DXGK_WIN32K_PARAM_DATA
author: windows-driver-content
description: The DXGK_WIN32K_PARAM_DATA structure is reserved for system use.
old-location: display\dxgk_win32k_param_data.htm
old-project: display
ms.assetid: a6bb2127-64f7-402d-906e-199d5ec1b313
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_WIN32K_PARAM_DATA, *PDXGK_WIN32K_PARAM_DATA, DXGK_WIN32K_PARAM_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_WIN32K_PARAM_DATA
req.alt-loc: ntddvdeo.h
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

# _DXGK_WIN32K_PARAM_DATA structure



## -description
The DXGK_WIN32K_PARAM_DATA structure is reserved for system use.


## -syntax

````
typedef struct _DXGK_WIN32K_PARAM_DATA {
  PVOID PathsArray;
  PVOID ModesArray;
  ULONG NumPathArrayElements;
  ULONG NumModeArrayElements;
  ULONG SDCFlags;
} DXGK_WIN32K_PARAM_DATA, *PDXGK_WIN32K_PARAM_DATA;
````


## -struct-fields

### -field PathsArray

Reserved for system use.

### -field ModesArray

Reserved for system use.

### -field NumPathArrayElements

Reserved for system use.

### -field NumModeArrayElements

Reserved for system use.

### -field SDCFlags

Reserved for system use.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>