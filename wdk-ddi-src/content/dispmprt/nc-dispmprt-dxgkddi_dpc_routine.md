---
UID: NC.dispmprt.DXGKDDI_DPC_ROUTINE
title: DXGKDDI_DPC_ROUTINE
author: windows-driver-content
description: The DxgkDdiDpcRoutine function is called back at IRQL DISPATCH_LEVEL after the display miniport driver calls DxgkCbQueueDpc.
old-location: display\dxgkddidpcroutine.htm
old-project: display
ms.assetid: 2767906a-f084-4ccc-b24f-ba7d66c96477
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiDpcRoutine
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
---

# DXGKDDI_DPC_ROUTINE callback



## -description
The <i>DxgkDdiDpcRoutine</i> function is called back at IRQL DISPATCH_LEVEL after the display miniport driver calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>.



## -prototype

````
DXGKDDI_DPC_ROUTINE DxgkDdiDpcRoutine;

VOID DxgkDdiDpcRoutine(
  _In_ const PVOID MiniportDeviceContext
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


## -returns
None


## -remarks
Only one deferred procedure call (DPC) can be scheduled (at a given time) for a given display adapter.

If the display miniport driver is supporting several display adapters, the <i>DxgkDdiDpcRoutine</i> might be called in a reentrant fashion. That is, while <i>DxgkDdiDpcRoutine</i> is executing on one processor on behalf of a particular display adapter, it could be called again on another processor on behalf of a different display adapter.


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
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DPC_ROUTINE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

