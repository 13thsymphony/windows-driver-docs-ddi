---
UID : NF:printoem.OEMQueryAdvanceWidths
title : OEMQueryAdvanceWidths function
author : windows-driver-content
description : The OEMQueryAdvanceWidths function returns character advance widths for a specified set of glyphs.
old-location : print\oemqueryadvancewidths.htm
old-project : print
ms.assetid : 058ced7e-50bc-4847-b082-57608ac5ddd2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print_unidrv-pscript_rendering_14849fac-0d28-4961-b37b-ee14cd285018.xml, print.oemqueryadvancewidths, OEMQueryAdvanceWidths, OEMQueryAdvanceWidths function [Print Devices], printoem/OEMQueryAdvanceWidths
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


# OEMQueryAdvanceWidths function
The <code>OEMQueryAdvanceWidths</code> function returns character advance widths for a specified set of glyphs.

## Syntax

````
BOOL APIENTRY OEMQueryAdvanceWidths(
        DHPDEV                                       dhpdev,
        FONTOBJ                                      *pfo,
        ULONG                                        iMode,
  _In_  _reads_(cGlyphs) HGLYPH                      *phg,
  _Out_ _writes_bytes_(cGlyphs*sizeof(USHORT)) PVOID pvWidths,
        ULONG                                        cGlyphs
);
````

## Parameters

`dhpdev`



`pfo`



`iMode`



`phg`



`pvWidths`



`cGlyphs`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printoem.h (include Printoem.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |