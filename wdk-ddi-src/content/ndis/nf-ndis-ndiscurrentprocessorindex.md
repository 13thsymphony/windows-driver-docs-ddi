---
UID: NF:ndis.NdisCurrentProcessorIndex
title: NdisCurrentProcessorIndex function
author: windows-driver-content
description: The NdisCurrentProcessorIndex function returns the system-assigned number of the current processor that the caller is running on.
old-location: netvista\ndiscurrentprocessorindex.htm
old-project: netvista
ms.assetid: 68ac845e-9b2f-4e35-8e61-83c799b3cd59
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisCurrentProcessorIndex, NdisCurrentProcessorIndex function [Network Drivers Starting with Windows Vista], ndis/NdisCurrentProcessorIndex, ndis_processor_group_ref_c19efe7e-be4a-4093-bd50-80d3c0588dc6.xml, netvista.ndiscurrentprocessorindex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: ">= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCurrentProcessorIndex
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCurrentProcessorIndex function
The 
  <b>NdisCurrentProcessorIndex</b> function returns the system-assigned number of the current processor that
  the caller is running on.

## Syntax

````
ULONG NdisCurrentProcessorIndex(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>NdisCurrentProcessorIndex</b> returns a ULONG value that represents the processor that the caller is
     currently running on. The number of processors in a symmetric multiprocessor (SMP) computer is a
     zero-based value.

## Remarks

NDIS drivers call the 
    <b>NdisCurrentProcessorIndex</b> function to obtain the system-assigned number of the current processor
    that the caller is running on.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | ">= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564915">NDIS_CURRENT_PROCESSOR_NUMBER</a>



<a href="..\ntddk\nf-ntddk-kegetcurrentprocessornumber.md">KeGetCurrentProcessorNumber</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCurrentProcessorIndex function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>