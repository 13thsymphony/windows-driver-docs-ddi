---
UID: NF:rilapi.RIL_WriteMsg
title: RIL_WriteMsg function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_writemsg.htm
old-project: netvista
ms.assetid: 6d8e934a-9f1e-4b65-9491-02cf7f5f9255
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL_WriteMsg, RIL_WriteMsg method [Network Drivers Starting with Windows Vista], netvista.ril_writemsg, rilapi/RIL_WriteMsg
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
-	RIL_WriteMsg
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_WriteMsg function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_WriteMsg(
   HRIL              hRil,
   LPVOID            lpContext,
   HUICCAPP          hUiccApp,
   const RILMESSAGE  lpMessage,
   RILMESSAGESTATUS  dwStatus
);
````

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`lpMessage`



`dwStatus`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |