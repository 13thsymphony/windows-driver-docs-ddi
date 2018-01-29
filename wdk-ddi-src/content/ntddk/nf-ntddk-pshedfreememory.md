---
UID : NF:ntddk.PshedFreeMemory
title : PshedFreeMemory function
author : windows-driver-content
description : The PshedFreeMemory function frees a block of memory that was previously allocated by calling the PshedAllocateMemory function.
old-location : whea\pshedfreememory.htm
old-project : whea
ms.assetid : e0784b46-9929-480c-88d0-9983d80fd753
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : whea.pshedfreememory, PshedFreeMemory function [WHEA Drivers and Applications], ntddk/PshedFreeMemory, PshedFreeMemory, whearef_e17812c6-f817-490d-b1f7-bf5fa16d769b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib : Pshed.lib
req.dll : Pshed.dll
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# PshedFreeMemory function
The <b>PshedFreeMemory</b> function frees a block of memory that was previously allocated by calling the <a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a> function.

## Syntax

````
VOID PshedFreeMemory(
  _In_ PVOID Address
);
````

## Parameters

`Address`

A pointer to the block of memory being freed.


## Return Value

None

## Remarks

A PSHED plug-in calls the <b>PshedFreeMemory</b> function to free a block of memory that it previously allocated by calling the <a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-pshedallocatememory.md">PshedAllocateMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PshedFreeMemory function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>