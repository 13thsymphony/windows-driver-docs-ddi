---
UID : NF:rilapi.RIL_SetSystemSelectionPrefs
title : RIL_SetSystemSelectionPrefs function
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\ril_setsystemselectionprefs.htm
old-project : netvista
ms.assetid : 57384690-9fe0-4fee-a578-5451e57cfc6b
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapi/RIL_SetSystemSelectionPrefs, RIL_SetSystemSelectionPrefs method [Network Drivers Starting with Windows Vista], RIL_SetSystemSelectionPrefs, netvista.ril_setsystemselectionprefs
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
req.typenames : RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product : Windows 10 or later.
---


# RIL_SetSystemSelectionPrefs function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SetSystemSelectionPrefs(
   HRIL                           hRil,
   LPVOID                         lpContext,
   RILSETSYSTEMSELECTIONPREFSFLAG dwFlags,
   const RILSYSTEMSELECTIONPREFS  lpRilSystemSelectionPrefs
);
````

## Parameters

`hRil`



`lpContext`



`dwFlags`



`lpRilSystemSelectionPrefs`




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