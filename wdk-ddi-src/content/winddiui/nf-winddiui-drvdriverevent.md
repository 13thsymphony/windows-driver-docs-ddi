---
UID : NF:winddiui.DrvDriverEvent
title : DrvDriverEvent function
author : windows-driver-content
description : The print spooler calls a printer interface DLL's DrvDriverEvent function when the spooler processes driver-specific events that might require action by the printer driver.
old-location : print\drvdriverevent.htm
old-project : print
ms.assetid : 84d1f438-b6ee-4199-89ae-9384601203b3
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : DrvDriverEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winddiui.h
req.include-header : Winddiui.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DrvDriverEvent
req.alt-loc : winddiui.h
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
req.typenames : WINBIO_VERSION, *PWINBIO_VERSION
req.product : Windows 10 or later.
---


# DrvDriverEvent function
The print spooler calls a printer interface DLL's <b>DrvDriverEvent</b> function when the spooler processes driver-specific events that might require action by the printer driver.

## Syntax

````
BOOL DrvDriverEvent(
           DWORD  dwDriverEvent,
           DWORD  dwLevel,
  _In_opt_ LPBYTE pDriverInfo,
           LPARAM lParam
);
````

## Parameters

`dwDriverEvent`

Caller-supplied bit flag indicating the event that has occurred. Valid flags are listed in the following table.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DRIVER_EVENT_DELETE

</td>
<td>
The driver is being removed.

</td>
</tr>
<tr>
<td>
DRIVER_EVENT_INITIALIZE

</td>
<td>
The driver has just been installed.

</td>
</tr>
</table>

`dwLevel`

Caller-supplied value indicating the type of structure pointed to by the <i>pDriverInfo</i> parameter, as indicated in the following table.

<table>
<tr>
<th><i>dwLevel</i> Value</th>
<th>Structure pointed to by <i>pDriverInfo</i></th>
</tr>
<tr>
<td>
1

</td>
<td>
DRIVER_INFO_1

</td>
</tr>
<tr>
<td>
2

</td>
<td>
DRIVER_INFO_2

</td>
</tr>
<tr>
<td>
3

</td>
<td>
DRIVER_INFO_3

</td>
</tr>
</table>
 

<dl>
<dd>
The DRIVER_INFO_<i>N</i> structures are described in the Microsoft Windows SDK documentation.

</dd>
</dl>

`pDriverInfo`

Caller-supplied pointer to a structure whose type is identified by the <i>dwLevel</i> parameter.

`lParam`

Caller-supplied flags. See the following Remarks section.


## Return Value

If the operation succeeds, the function should return <b>TRUE</b>. Otherwise, it should return <b>FALSE</b>.

## Remarks

The optional <b>DrvDriverEvent</b> function is called by the spooler's <b>AddPrinterDriverEx</b> and <b>DeletePrinterDriverEx</b> functions, which are described in the Windows SDK documentation.

The function's purpose is to allow a printer driver's <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> to perform operations needed when the driver is installed or removed. A typical operation for this function to perform is to create or remove extra driver-specific files that are not specified as dependent files in a <a href="https://msdn.microsoft.com/33f1c836-0846-49d5-8ab5-baadf9e0678c">printer INF file</a>.

If <i>dwDriverEvent</i> is DRIVER_EVENT_DELETE, the <i>lparam</i> parameter contains the flags that were specified for the <b>DeletePrinterDriverEx</b> function's <i>dwDeleteFlag</i> parameter. The <i>lparam</i> parameter is not used if <i>dwDriverEvent</i> is DRIVER_EVENT_INITIALIZE.

Because the <b>DrvDriverEvent</b> function is called in the context of the print spooler, it cannot display a user interface.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winddiui.h (include Winddiui.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |