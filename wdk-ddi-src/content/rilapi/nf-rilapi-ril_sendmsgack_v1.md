---
UID: NF:rilapi.RIL_SendMsgAck_V1
title: RIL_SendMsgAck_V1 function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendmsgack_v1.htm
old-project: netvista
ms.assetid: 5a3c148e-d113-4cbc-a88a-691531bb3d9d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_SendMsgAck_V1 method [Network Drivers Starting with Windows Vista], netvista.ril_sendmsgack_v1, rilapi/RIL_SendMsgAck_V1, RIL_SendMsgAck_V1
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
-	RIL_SendMsgAck_V1
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---


# RIL_SendMsgAck_V1 function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SendMsgAck_V1(
   HRIL            hRil,
   LPVOID          lpContext,
   DWORD           dwExecutor,
   HUICCAPP        hUiccApp,
   DWORD           dwAckID,
   RILMSGACKSTATUS dwMsgStatus
);
````

## Parameters

`hRil`



`lpContext`



`dwExecutor`



`hUiccApp`



`dwAckID`



`dwMsgStatus`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |