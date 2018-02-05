---
UID : NF:rilapi.RIL_WriteMsg
title : RIL_WriteMsg function
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\ril_writemsg.htm
old-project : netvista
ms.assetid : 6d8e934a-9f1e-4b65-9491-02cf7f5f9255
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ril_writemsg, RIL_WriteMsg, rilapi/RIL_WriteMsg, RIL_WriteMsg method [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : rilapi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product : Windows 10 or later.
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
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |