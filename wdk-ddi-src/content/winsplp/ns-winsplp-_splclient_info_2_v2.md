---
UID: NS:winsplp._SPLCLIENT_INFO_2_V2
title: _SPLCLIENT_INFO_2_V2
author: windows-driver-content
description: .
old-location: print\splclient_info_2_winxp.htm
old-project: print
ms.assetid: 48BD760E-6017-49B2-854F-7F48671974F3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _SPLCLIENT_INFO_2_V2, SPLCLIENT_INFO_2_WINXP, *PSPLCLIENT_INFO_2, *LPSPLCLIENT_INFO_2, SPLCLIENT_INFO_2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPLCLIENT_INFO_2_WINXP
req.alt-loc: Winsplp.h
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
req.typenames: SPLCLIENT_INFO_2_WINXP
req.product: Windows 10 or later.
---

# _SPLCLIENT_INFO_2_V2 structure



## -description




## -syntax

````
typedef struct _SPLCLIENT_INFO_2_V2 {
#ifdef _WIN64
  DWORD64  hSplPrinter;
#else 
  DWORD32  hSplPrinter;
#endif 
} SPLCLIENT_INFO_2_WINXP;
````


## -struct-fields

### -field hSplPrinter

Specifies the server-side handle to be used for direct calls.


### -field hSplPrinter

Specifies the server-side handle to be used for direct calls.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>