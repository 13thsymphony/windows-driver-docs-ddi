---
UID: NF:rilapi.RIL_GetPSMediaConfiguration
title: RIL_GetPSMediaConfiguration function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getpsmediaconfiguration.htm
old-project: netvista
ms.assetid: f7b1f2a6-d57a-44ec-b14b-8b41b020935e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL_GetPSMediaConfiguration, RIL_GetPSMediaConfiguration method [Network Drivers Starting with Windows Vista], netvista.ril_getpsmediaconfiguration, rilapi/RIL_GetPSMediaConfiguration
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
-	RIL_GetPSMediaConfiguration
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_GetPSMediaConfiguration function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_GetPSMediaConfiguration(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwExecutor
);
````

## Parameters

`hRil`



`lpContext`



`dwExecutor`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |