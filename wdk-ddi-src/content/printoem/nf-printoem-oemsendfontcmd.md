---
UID: NF:printoem.OEMSendFontCmd
title: OEMSendFontCmd function
author: windows-driver-content
description: OEMSendFontCmd function
old-location: print\oemsendfontcmd.htm
old-project: print
ms.assetid: 4dcc2ec0-6a75-4fc0-800c-c1ce12e3fd6a
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: OEMSendFontCmd, print.oemsendfontcmd, printoem/OEMSendFontCmd, OEMSendFontCmd function [Print Devices], print_obsoletefunctions_f54bf949-57eb-49ea-a69b-f9edfdfb9da6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	printoem.h
apiname:
-	OEMSendFontCmd
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMSendFontCmd function


## Syntax

````
VOID APIENTRY OEMSendFontCmd(
   PDEVOBJ      pdevobj,
   PUNIFONTOBJ  pUFObj,
   PFINVOCATION pFInv
);
````

## Parameters

`pdevobj`



`pUFObj`



`pFInv`




## Return Value

This function does not return a value.

<h2><a id="ddk_oemsendfontcmd_gg"></a><a id="DDK_OEMSENDFONTCMD_GG"></a></h2>
This function is obsolete for Windows XP and later. It is supported only for earlier Unidrv plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554274">IPrintOemUni::SendFontCmd</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |