---
UID: NS.WINDDIUI._DEVICEPROPERTYHEADER
title: _DEVICEPROPERTYHEADER
author: windows-driver-content
description: The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function.
old-location: print\devicepropertyheader.htm
old-project: print
ms.assetid: f1b9cd2f-fa5b-4f34-a237-06d00badf1d1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER, PDEVICEPROPERTYHEADER, *PDEVICEPROPERTYHEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICEPROPERTYHEADER
req.alt-loc: winddiui.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _DEVICEPROPERTYHEADER structure



## -description
The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's <a href="print.drvdevicepropertysheets">DrvDevicePropertySheets</a> function.



## -syntax

````
typedef struct _DEVICEPROPERTYHEADER {
  WORD   cbSize;
  WORD   Flags;
  HANDLE hPrinter;
  LPTSTR pszPrinterName;
} DEVICEPROPERTYHEADER, *PDEVICEPROPERTYHEADER;
````


## -struct-fields

### -field cbSize

Size, in bytes, of the DEVICEPROPERTYHEADER structure.


### -field Flags

Is a set of flags that can be set to the following value: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DPS_NOPERMISSION

</td>
<td>
If set, the user is not permitted to update device settings.

</td>
</tr>
</table>
 


### -field hPrinter

Printer handle.


### -field pszPrinterName

Pointer to a NULL-terminated string representing a printer name.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winddiui.h (include Winddiui.h)</dt>
</dl>
</td>
</tr>
</table>