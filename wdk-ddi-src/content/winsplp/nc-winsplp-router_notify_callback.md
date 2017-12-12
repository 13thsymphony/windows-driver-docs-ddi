---
UID: NC.winsplp.ROUTER_NOTIFY_CALLBACK
title: ROUTER_NOTIFY_CALLBACK
author: windows-driver-content
description: .
old-location: print\router_notify_callback.htm
old-project: print
ms.assetid: 97D8FEEA-B6D7-4AD7-A067-B503AF8F23FF
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _SCARD_IO_REQUEST, SCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, *PSCARD_IO_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ROUTER_NOTIFY_CALLBACK
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
req.product: Windows 10 or later.
---

# ROUTER_NOTIFY_CALLBACK callback



## -description




## -prototype

````
ROUTER_NOTIFY_CALLBACK ROUTER_NOTIFY_CALLBACK;

 ROUTER_NOTIFY_CALLBACK(
  _In_  DWORD                    dwCommand,
  _In_  PVOID                    pContext,
  _In_  DWORD                    dwColor,
  _In_  PPRINTER_NOTIFY_INFO     pNofityInfo,
  _In_  DWORD                    fdwFlags,
  _Out_ PDWORD                   pdwResult
)
{ ... }
````


## -parameters

### -param dwCommand [in]


### -param pContext [in]


### -param dwColor [in]


### -param pNofityInfo [in]


### -param fdwFlags [in]


### -param pdwResult [out]


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