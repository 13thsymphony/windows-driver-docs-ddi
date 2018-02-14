---
UID: NF:winsplp.GetPrintProcessorCapabilities
title: GetPrintProcessorCapabilities function
author: windows-driver-content
description: A print processor's GetPrintProcessorCapabilities function returns capabilities associated with a specified input data type.
old-location: print\getprintprocessorcapabilities.htm
old-project: print
ms.assetid: 81aacb41-cba7-4bd0-aded-919a4df0b934
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.getprintprocessorcapabilities, GetPrintProcessorCapabilities function [Print Devices], spoolfnc_4ca0ae34-060f-4144-91de-a2556d1b5261.xml, winsplp/GetPrintProcessorCapabilities, GetPrintProcessorCapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
-	winsplp.h
apiname:
-	GetPrintProcessorCapabilities
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# GetPrintProcessorCapabilities function
A print processor's <b>GetPrintProcessorCapabilities</b> function returns capabilities associated with a specified input data type.

## Syntax

````
DWORD GetPrintProcessorCapabilities(
  _In_  LPTSTR  pValueName,
  _In_  DWORD   dwAttributes,
  _Out_ LPBYTE  pData,
  _In_  DWORD   nSize,
  _Out_ LPDWORD pcbNeeded
);
````

## Parameters

`pValueName`

Caller-supplied pointer to a string that represents a data type that is supported by the print processor. The string pointer must be of type LPWSTR.

`dwAttributes`

Caller-supplied attributes flags. Refer to the <b>Attributes</b> member of PRINTER_INFO_<i>x</i> structures (described in the Microsoft Windows SDK documentation).

`pData`

Caller-supplied pointer to a PRINTPROCESSOR_CAPS_1 or PRINTPROCESSOR_CAPS_2 structure (described in the Windows SDK documentation).

`nSize`

Caller-supplied value that represents the size of the buffer pointed to by <i>pData</i>.

If the value is less than sizeof(PRINTPROCESSOR_CAPS_1), this function should supply a value that is equal to sizeof(PRINTPROCESSOR_CAPS_1) or sizeof(PRINTPROCESSOR_CAPS_2), depending on which structure is supported by the print processor.

<div class="alert"><b>Note</b>    If the value is less than sizeof(PRINTPROCESSOR_CAPS_1), the winprint print processor will supply a value of sizeof(PRINTPROCESSOR_CAPS_2) for Windows Vista operating systems, or sizeof(PRINTPROCESSOR_CAPS_1) for earlier operating system versions.</div>
<div> </div>

`pcbNeeded`

Caller-supplied pointer to a location to receive the minimum required size for the buffer pointed to by <i>pData</i>.


## Return Value

If the operation succeeds, the function should return ERROR_SUCCESS. Otherwise, it should return a Win32 error code.

## Remarks

Print processors can optionally export a <b>GetPrintProcessorCapabilities</b> function. The function's purpose is to return a filled-in PRINTPROCESSOR_CAPS_1 or PRINTPROCESSOR_CAPS_2 structure for every input data type that the print processor supports.

The spooler calls a print processor's <b>GetPrintProcessorCapabilities</b> function when an application calls <b>GetPrinterData</b> (described in the Windows SDK documentation), specifying a value name with a format of PrintProcCaps_<i>datatype</i>, where <i>datatype</i> is the name of an input data type. Before calling <b>GetPrintProcessorCapabilities,</b> the spooler removes the PrintProcCaps_ prefix from the value name string.

The function should determine if the received buffer is large enough and, if it is, should fill in either the PRINTPROCESSOR_CAPS_1 or PRINTPROCESSOR_CAPS_2 structure (defined in the Windows SDK documentation) and return. The value of <i>nSize</i> determines whether PRINTPROCESSOR_CAPS_1 or PRINTPROCESSOR_CAPS_2 will be used.

The function should always use the location pointed to by <i>pcbNeeded</i> to return the required buffer size, whether or not the actual buffer is large enough.

The specified return value becomes the return value that the spooler provides for <b>GetPrinterData</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | winsplp.h (include Winsplp.h) |
| **Library** | NtosKrnl.exe |