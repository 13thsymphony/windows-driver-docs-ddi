---
UID: NF.spb.SPB_TRANSFER_LIST_ENTRY_INIT_MDL
title: SPB_TRANSFER_LIST_ENTRY_INIT_MDL
author: windows-driver-content
description: The SPB_TRANSFER_LIST_ENTRY_INIT_MDL function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to use an MDL to describe a data buffer.
old-location: spb\spb_transfer_list_entry_init_mdl.htm
ms.assetid: FFE8761B-5769-48E5-ACE9-50009C490714
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: SPB
req.header: spb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPB_TRANSFER_LIST_ENTRY_INIT_MDL
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
ms.keywords: SPB_TRANSFER_LIST_ENTRY_INIT_MDL
req.iface: 
req.product: Windows 10 or later.
---

# SPB_TRANSFER_LIST_ENTRY_INIT_MDL function



## -description
<p>The <b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> function returns an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structure that is initialized to use an MDL to describe a data buffer.</p>


## -syntax

````
SPB_TRANSFER_LIST_ENTRY SPB_TRANSFER_LIST_ENTRY_INIT_MDL(
  _In_ SPB_TRANSFER_DIRECTION Direction,
  _In_ ULONG                  DelayInUs,
  _In_ PMDL                   Mdl
);
````


## -parameters
<dl>

### -param <i>Direction</i> [in]

<dd>
<p>The direction of the transfer. The function writes this value to the <b>Direction</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.</p>
</dd>

### -param <i>DelayInUs</i> [in]

<dd>
<p>An optional delay in microseconds. The function writes this value to the <b>DelayInUs</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure.</p>
</dd>

### -param <i>Mdl</i> [in]

<dd>
<p>A pointer to an MDL that describes a data buffer. The function writes this value to the <b>Buffer.Mdl</b> member of the <b>SPB_TRANSFER_LIST_ENTRY</b> structure. For more information, see the description of the <b>Mdl</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>.</p>
</dd>
</dl>

## -returns
<p><b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> returns an initialized <b>SPB_TRANSFER_LIST_ENTRY</b> structure.</p>

## -remarks
<p>This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.</p>

<p><b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatMdl</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.</p>

<p>This initialization function returns an unnamed local variable of type <b>SPB_TRANSFER_LIST_ENTRY</b>. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.</p>

<p><b>SPB_TRANSFER_LIST_ENTRY_INIT_MDL</b> sets the <b>Buffer.Format</b> member of the  <b>SPB_TRANSFER_LIST_ENTRY</b> structure to <b>SpbTransferBufferFormatMdl</b>. For more information about buffer formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spb.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any IRQL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406215">SPB_TRANSFER_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406216">SPB_TRANSFER_BUFFER_FORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST_ENTRY_INIT_MDL function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
