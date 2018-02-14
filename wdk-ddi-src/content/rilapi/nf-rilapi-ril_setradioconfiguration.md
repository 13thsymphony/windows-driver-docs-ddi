---
UID: NF:rilapi.RIL_SetRadioConfiguration
title: RIL_SetRadioConfiguration function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setradioconfiguration.htm
old-project: netvista
ms.assetid: b48ba9fe-3b7c-4ca8-8dcb-1e2a586353b9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_setradioconfiguration, RIL_SetRadioConfiguration, RIL_SetRadioConfiguration method [Network Drivers Starting with Windows Vista], rilapi/RIL_SetRadioConfiguration
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapi.h
apiname:
-	RIL_SetRadioConfiguration
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_SetRadioConfiguration function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SetRadioConfiguration(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwConfigIdx
);
````

## Parameters

`hRil`



`lpContext`



`dwConfigIdx`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |