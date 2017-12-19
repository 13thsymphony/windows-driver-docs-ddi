---
UID: NS.NTDDRILAPITYPES.RILADDITIONALCALLERINFO
title: RILADDITIONALCALLERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladditionalcallerinfo.htm
old-project: NetVista
ms.assetid: dd622ebc-beba-4c96-a0e8-97ad614e3937
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILADDITIONALCALLERINFO, *LPRILADDITIONALCALLERINFO, LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO
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
req.alt-api: RILADDITIONALCALLERINFO
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

# RILADDITIONALCALLERINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILADDITIONALCALLERINFO {
  DWORD     cbSize;
  DWORD     dwParams;
  DWORD     dwExecutor;
  DWORD     dwCallId;
  DWORD     dwCallerInfoLength;
  WCHAR [1] wszCallerInfo;
} RILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwCallId


### -field dwCallerInfoLength


### -field wszCallerInfo


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