---
UID: NF:rilapi.RIL_SetSlotPower
title: RIL_SetSlotPower function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setslotpower.htm
old-project: netvista
ms.assetid: c7e12c2a-3382-478b-a306-7c86c93d45d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ril_setslotpower, rilapi/RIL_SetSlotPower, RIL_SetSlotPower method [Network Drivers Starting with Windows Vista], RIL_SetSlotPower
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
-	RIL_SetSlotPower
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---


# RIL_SetSlotPower function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SetSlotPower(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwSlotIndex,
   BOOL   fPowerOn
);
````

## Parameters

`hRil`



`lpContext`



`dwSlotIndex`



`fPowerOn`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |