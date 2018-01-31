---
UID : NF:rilapi.RIL_RemoveCallForwarding
title : RIL_RemoveCallForwarding function
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\ril_removecallforwarding.htm
old-project : netvista
ms.assetid : d2ac3147-fe34-4643-b735-c795b6ba4768
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ril_removecallforwarding, RIL_RemoveCallForwarding, rilapi/RIL_RemoveCallForwarding, RIL_RemoveCallForwarding method [Network Drivers Starting with Windows Vista]
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


# RIL_RemoveCallForwarding function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_RemoveCallForwarding(
   HRIL                            hRil,
   LPVOID                          lpContext,
   DWORD                           dwExecutor,
   RILCALLFORWARDINGSETTINGSREASON dwReason,
   DWORD                           dwInfoClasses
);
````

## Parameters

`hRil`



`lpContext`



`dwExecutor`



`dwReason`



`dwInfoClasses`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |