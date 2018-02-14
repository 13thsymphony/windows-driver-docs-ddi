---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST
title: SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function
author: windows-driver-content
description: The SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a scatter-gather list.SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a scatter-gather list.
old-location: spb\spb_transfer_list_entry_init_buffer_list.htm
old-project: SPB
ms.assetid: 39FFE334-1696-43EF-81FA-C9B05F8FB644
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function [Buses], SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST, SPB.spb_transfer_list_entry_init_buffer_list, spb/SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST
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
-	SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST
product: Windows
targetos: Windows
req.typenames: "*PSPB_TRANSFER_DIRECTION, SPB_TRANSFER_DIRECTION"
req.product: Windows 10 or later.
---


# SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function
The <b>SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to describe a scatter-gather list.

## Syntax

````
SPB_TRANSFER_LIST_ENTRY SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST(
  _In_ SPB_TRANSFER_DIRECTION         Direction,
  _In_ ULONG                          DelayInUs,
  _In_ SPB_TRANSFER_BUFFER_LIST_ENTRY BufferList[],
  _In_ ULONG                          BufferListCe
);
````

## Parameters

`Direction`

The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

`DelayInUs`

An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

`BufferList`

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a> structures that describes a scatter-gather list. The function writes this value to the <b>Buffer.BufferList.List</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>BufferList.List</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>.

`BufferListCe`

The number of buffers in the scatter-gather list pointed to by <i>BufferList</i>. The function writes this value to the <b>Buffer.BufferList.ListCe</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>BufferList.ListCe</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>.


## Return Value

<b>SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.

## Remarks

This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatList</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | spb.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any IRQL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>