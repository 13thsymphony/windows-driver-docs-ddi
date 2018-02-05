---
UID : NF:rilapi.RIL_GetUiccRecordStatus
title : RIL_GetUiccRecordStatus function
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\ril_getuiccrecordstatus.htm
old-project : netvista
ms.assetid : f4834b37-7269-47e3-9af4-81d17fa79179
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_GetUiccRecordStatus, netvista.ril_getuiccrecordstatus, RIL_GetUiccRecordStatus method [Network Drivers Starting with Windows Vista], rilapi/RIL_GetUiccRecordStatus
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


# RIL_GetUiccRecordStatus function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_GetUiccRecordStatus(
   HRIL                   hRil,
   LPVOID                 lpContext,
   const RILUICCFILEPATH  lpFilePath
);
````

## Parameters

`hRil`



`lpContext`



`lpFilePath`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |