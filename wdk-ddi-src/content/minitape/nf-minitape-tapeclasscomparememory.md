---
UID : NF:minitape.TapeClassCompareMemory
title : TapeClassCompareMemory function
author : windows-driver-content
description : The TapeClassCompareMemory routine compares two memory buffers and returns the number of bytes that are equivalent.
old-location : storage\tapeclasscomparememory.htm
old-project : storage
ms.assetid : dfff350c-ff76-49d3-b4ba-a5a51fabd419
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.tapeclasscomparememory, tapeclas_77631fdd-b72a-4569-8066-54f260cb4d9a.xml, minitape/TapeClassCompareMemory, TapeClassCompareMemory, TapeClassCompareMemory routine [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : minitape.h
req.include-header : Minitape.h
req.target-type : Desktop
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
req.lib : Tape.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PTAPE_STATUS, TAPE_STATUS"
---


# TapeClassCompareMemory function
The <b>TapeClassCompareMemory</b> routine compares two memory buffers and returns the number of bytes that are equivalent.

## Syntax

````
ULONG TapeClassCompareMemory(
  _Inout_ PVOID Source1,
  _Inout_ PVOID Source2,
  _In_    ULONG Length
);
````

## Parameters

`Source1`

Pointer to the first buffer to be compared.

`Source2`

Pointer to the second buffer to be compared.

`Length`

Specifies the number of bytes to be compared.


## Return Value

<b>TapeClassCompareMemory</b> returns the number of bytes that are equivalent.

## Remarks

A tape miniclass driver uses <b>TapeClassCompareMemory</b> to compare memory in a portable way. For example, a miniclass driver uses <b>TapeClassCompareMemory</b> in its TapeMiniVerifyInquiry routine to determine whether a given product ID matches one of the devices the driver supports.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | minitape.h (include Minitape.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\minitape\nc-minitape-tape_verify_inquiry_routine.md">TapeMiniVerifyInquiry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TapeClassCompareMemory routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>