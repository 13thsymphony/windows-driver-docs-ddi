---
UID: NF:rilapi.RIL_DeleteMsg
title: RIL_DeleteMsg function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_deletemsg.htm
old-project: netvista
ms.assetid: bda4663b-0aae-481a-8bd6-f242c6e6b1de
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_DeleteMsg, RIL_DeleteMsg method [Network Drivers Starting with Windows Vista], netvista.ril_deletemsg, RIL_DeleteMsg
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
-	RIL_DeleteMsg
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_DeleteMsg function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_DeleteMsg(
   HRIL     hRil,
   LPVOID   lpContext,
   HUICCAPP hUiccApp,
   DWORD    dwIndex
);
````

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`dwIndex`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |