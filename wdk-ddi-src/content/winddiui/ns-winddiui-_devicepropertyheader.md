---
UID : NS:winddiui._DEVICEPROPERTYHEADER
title : "_DEVICEPROPERTYHEADER"
author : windows-driver-content
description : The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function.
old-location : print\devicepropertyheader.htm
old-project : print
ms.assetid : f1b9cd2f-fa5b-4f34-a237-06d00badf1d1
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : DEVICEPROPERTYHEADER, _DEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER structure [Print Devices], print_interface-graphics_7dc4be04-e0ab-43bb-8e6d-f500cc7cf51c.xml, print.devicepropertyheader, *PDEVICEPROPERTYHEADER, PDEVICEPROPERTYHEADER structure pointer [Print Devices], winddiui/PDEVICEPROPERTYHEADER, winddiui/DEVICEPROPERTYHEADER, PDEVICEPROPERTYHEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : winddiui.h
req.include-header : Winddiui.h
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDEVICEPROPERTYHEADER, DEVICEPROPERTYHEADER"
req.product : Windows 10 or later.
---

# _DEVICEPROPERTYHEADER structure
The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's <a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a> function.

## Syntax
````
typedef struct _DEVICEPROPERTYHEADER {
  WORD   cbSize;
  WORD   Flags;
  HANDLE hPrinter;
  LPTSTR pszPrinterName;
} DEVICEPROPERTYHEADER, *PDEVICEPROPERTYHEADER;
````

## Members


`cbSize`

Size, in bytes, of the DEVICEPROPERTYHEADER structure.

`Flags`

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

`hPrinter`

Printer handle.

`pszPrinterName`

Pointer to a NULL-terminated string representing a printer name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winddiui.h (include Winddiui.h) |