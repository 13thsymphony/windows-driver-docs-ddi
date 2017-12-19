---
UID: NF.spb.SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
title: SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function
author: windows-driver-content
description: The SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer.SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer.
old-location: spb\spb_transfer_list_entry_init_simple.htm
old-project: SPB
ms.assetid: 38F50F76-5D14-47CE-A211-3FC4F1399A74
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
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
req.alt-api: SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE
req.alt-loc: Spb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any IRQL
req.product: Windows 10 or later.
---

# SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function



## -description

The <b>SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to describe a simple data buffer.



The <b>SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to describe a simple data buffer.



## -syntax

````
SPB_TRANSFER_LIST_ENTRY SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE(
  _In_ SPB_TRANSFER_DIRECTION Direction,
  _In_ ULONG                  DelayInUs,
  _In_ PVOID                  Buffer,
  _In_ ULONG                  BufferCb
);
````


## -parameters

### -param Direction [in]

The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param DelayInUs [in]

An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


### -param Buffer [in]

A pointer to a data buffer. The function writes this value to the <b>Buffer.Simple.Buffer</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Buffer</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.


### -param BufferCb [in]

The size, in bytes, of the buffer pointed to by <i>Buffer</i>. The function writes this value to the <b>Buffer.Simple.BufferCb</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>BufferCb</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>.


## -returns
<b>SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.


## -remarks
This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

<b>SPB_MDL_TRANSFER_ENTRY</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatSimple</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Spb.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any IRQL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406217">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

