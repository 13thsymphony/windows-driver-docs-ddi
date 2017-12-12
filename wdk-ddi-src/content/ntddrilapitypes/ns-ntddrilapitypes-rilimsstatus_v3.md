---
UID: NS.NTDDRILAPITYPES.RILIMSSTATUS_V3
title: RILIMSSTATUS_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v3.htm
old-project: netvista
ms.assetid: 4c0ee205-2508-4414-afa5-cb6e7a358fc8
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILIMSSTATUS_V3, RILIMSSTATUS, *LPRILIMSSTATUS, RILIMSSTATUS_V3, *LPRILIMSSTATUS_V3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILIMSSTATUS_V3
req.alt-loc: ntddrilapitypes.h
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

# RILIMSSTATUS_V3 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILIMSSTATUS_V3 {
  DWORD             cbSize;
  DWORD             dwParams;
  DWORD             dwExecutor;
  HUICCAPP          hUiccApp;
  DWORD             dwAvailableServices;
  RILSMSFORMAT      dwSMSSupportedFormat;
  WCHAR [256]       wszServingDomain;
  RILIMSSYSTEMTYPE  dwIMSSystemType;
} RILIMSSTATUS_V3, RILIMSSTATUS_V3;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwAvailableServices


### -field dwSMSSupportedFormat


### -field wszServingDomain


### -field dwIMSSystemType


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>