---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
title: SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function
author: windows-driver-content
description: The SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer in nonpaged memory.
old-location: spb\spb_transfer_list_entry_init_non_paged.htm
old-project: SPB
ms.assetid: 5ED8DC18-75B8-40EB-B7D2-6F8597BCEBF9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spb_transfer_list_entry_init_non_paged, SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED, SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function [Buses], spb/SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spb.h
req.include-header: 
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Spb.h
apiname:
-	SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_DIRECTION, *PSPB_TRANSFER_DIRECTION
req.product: Windows 10 or later.
---


# SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function
The <b>SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to describe a simple data buffer in nonpaged memory.

## Syntax

````
SPB_TRANSFER_LIST_ENTRY SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED(
  _In_ SPB_TRANSFER_DIRECTION Direction,
  _In_ ULONG                  DelayInUs,
  _In_ PVOID                  Buffer,
  _In_ ULONG                  BufferCb
);
````

## Parameters

`Direction`

The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

`DelayInUs`

An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

`Buffer`

A pointer to a data buffer. The function writes this value to the <b>Buffer.Simple.Buffer</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Buffer</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.

`BufferCb`

The size, in bytes, of the buffer pointed to by <i>Buffer</i>. The function writes this value to the <b>Buffer.Simple.BufferCb</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>BufferCb</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.


## Return Value

<b>SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

## Remarks

This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatSimpleNonPaged</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | spb.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any IRQL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>