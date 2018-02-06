---
UID: NF:rilapi.RIL_SetUiccServiceState
title: RIL_SetUiccServiceState function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setuiccservicestate.htm
old-project: netvista
ms.assetid: 96b17a3f-1e69-47f5-aa09-59abfb5c1505
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_SetUiccServiceState, RIL_SetUiccServiceState method [Network Drivers Starting with Windows Vista], RIL_SetUiccServiceState, netvista.ril_setuiccservicestate
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
-	RIL_SetUiccServiceState
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---


# RIL_SetUiccServiceState function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SetUiccServiceState(
   HRIL                         hRil,
   LPVOID                       lpContext,
   HUICCAPP                     hUiccApp,
   RILUICCSERVICESERVICE        dwService,
   const RILUICCLOCKCREDENTIAL  lpLockCredential,
   BOOL                         fEnable
);
````

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`dwService`



`lpLockCredential`



`fEnable`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |