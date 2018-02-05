---
UID : NF:printoem.OEMDevicePropertySheets
title : OEMDevicePropertySheets function
author : windows-driver-content
description : OEMDevicePropertySheets function
old-location : print\oemdevicepropertysheets.htm
old-project : print
ms.assetid : 7042a08d-b45e-49f2-acd2-1f5b6146c1da
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print_obsoletefunctions_50e101c3-3bd4-4966-b29d-4a10f7295835.xml, print.oemdevicepropertysheets, OEMDevicePropertySheets, printoem/OEMDevicePropertySheets, OEMDevicePropertySheets function [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : printoem.h
req.include-header : Printoem.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
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
req.typenames : STDVARIABLEINDEX
req.product : Windows 10 or later.
---


# OEMDevicePropertySheets function


## Syntax

````
LRESULT APIENTRY OEMDevicePropertySheets(
   PPROPSHEETUI_INFO *pPSUIInfo,
   LPARAM            lParam
);
````

## Parameters

`pPSUIInfo`



`lParam`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |