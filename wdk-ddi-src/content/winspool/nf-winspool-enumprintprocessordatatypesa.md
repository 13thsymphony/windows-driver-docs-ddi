---
UID: NF:winspool.EnumPrintProcessorDatatypesA
title: EnumPrintProcessorDatatypesA function
author: windows-driver-content
description: A print processor's EnumPrintProcessorDatatypes function enumerates the data types that the print processor supports.
old-location: print\enumprintprocessordatatypes.htm
old-project: print
ms.assetid: 018880d0-0b0b-4130-bd8f-93814e40fe1e
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: EnumPrintProcessorDatatypes, EnumPrintProcessorDatatypes function [Print Devices], EnumPrintProcessorDatatypesA, spoolfnc_f0686e8e-e1bc-448a-8dd1-eeccfb66dd9e.xml, print.enumprintprocessordatatypes, winspool/EnumPrintProcessorDatatypes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
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
-	winspool.h
apiname:
-	EnumPrintProcessorDatatypes
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# EnumPrintProcessorDatatypesA function
A print processor's <b>EnumPrintProcessorDatatypes</b> function enumerates the data types that the print processor supports.

## Syntax

````
BOOL EnumPrintProcessorDatatypes(
  _In_opt_  LPTSTR  pName,
  _In_      LPTSTR  pPrintProcessorName,
            DWORD   Level,
  _Out_opt_ LPBYTE  pDatatypes,
            DWORD   cbBuf,
  _Out_     LPDWORD pcbNeeded,
  _Out_     LPDWORD pcReturned
);
````

## Parameters

`pName`

Caller-supplied pointer to a string representing name of the server on which the print processor is installed. If <b>NULL</b>, the server is the local system.

`pPrintProcessorName`

Caller-supplied pointer to a string representing the print processor name.

`Level`

Caller-supplied value indicating the type of the structures to be returned in the buffer pointed to by <i>pDatatypes</i>. This value must be 1, indicating that the structure is DATATYPES_INFO_1.

`pDatatypes`

Caller-supplied pointer to a buffer to receive an array of DATATYPES_INFO_1 structures, followed by a set of character strings representing data type names. The DATATYPES_INFO_1 structure is described in the Microsoft Windows SDK documentation. The structure member <i>pName</i> must be of type LPWSTR.

`cbBuf`

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pDatatypes</i>.

`pcbNeeded`

Caller-supplied pointer to a location to receive the minimum required size for the buffer pointed to by <i>pDatatypes</i>.

`pcReturned`

Caller-supplied pointer to a location to receive the number of DATATYPES_INFO_1 structures returned in the buffer pointed to by <i>pDatatypes</i>.


## Return Value

If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>FALSE</b>.

## Remarks

Print processors are required to export an <b>EnumPrintProcessorDatatypes</b> function. The local print provider calls the function during initialization. The function is also called when an application calls the spooler's version of the same function.

The function must return an array of DATATYPES_INFO_1 structures, with each structure pointing to a string that represents a data type. The actual strings must also be included in the buffer, after the structure array. See <a href="https://msdn.microsoft.com/42ab44f2-dba4-4b52-870a-2cb42fc2d0a9">Sample Print Processor</a> for an example.

The function should return the number of DATATYPES_INFO_1 structures returned (that is, the number of data types supported) in the location pointed to by <i>pcReturned</i>.

The function should return the minimum required buffer size in the location pointed to by <i>pcbNeeded</i>. If the supplied buffer is too small, the function should specify a value for <i>pcbNeeded</i>, set the error code to ERROR_INSUFFICIENT_BUFFER, and return <b>FALSE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | winspool.h (include Winspool.h) |
| **Library** | NtosKrnl.exe |