---
UID: NF:rilapi.RIL_RegisterUiccToolkitService
title: RIL_RegisterUiccToolkitService function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_registeruicctoolkitservice.htm
old-project: netvista
ms.assetid: 1f406818-b81c-4dc8-bfc7-0c977495b285
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_RegisterUiccToolkitService, RIL_RegisterUiccToolkitService method [Network Drivers Starting with Windows Vista], netvista.ril_registeruicctoolkitservice, rilapi/RIL_RegisterUiccToolkitService
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_RegisterUiccToolkitService
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_RegisterUiccToolkitService function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_RegisterUiccToolkitService(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwSlotIndex
);
````

## Parameters

`hRil`



`lpContext`



`dwSlotIndex`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |