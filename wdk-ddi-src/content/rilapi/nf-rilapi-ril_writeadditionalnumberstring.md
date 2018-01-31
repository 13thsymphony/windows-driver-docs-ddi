---
UID : NF:rilapi.RIL_WriteAdditionalNumberString
title : RIL_WriteAdditionalNumberString function
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\ril_writeadditionalnumberstring.htm
old-project : netvista
ms.assetid : 9ddf148b-7d36-4a95-a866-57e26220a549
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_WriteAdditionalNumberString method [Network Drivers Starting with Windows Vista], RIL_WriteAdditionalNumberString, rilapi/RIL_WriteAdditionalNumberString, netvista.ril_writeadditionalnumberstring
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


# RIL_WriteAdditionalNumberString function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_WriteAdditionalNumberString(
   HRIL                                      hRil,
   LPVOID                                    lpContext,
   HUICCAPP                                  hUiccApp,
   const RILPHONEBOOKADDITIONALNUMBERSTRING  lpRilPBANS
);
````

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`lpRilPBANS`




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