---
UID: NC.ntdd8042.PI8042_MOUSE_ISR
title: PI8042_MOUSE_ISR
author: windows-driver-content
description: A PI8042_MOUSE_ISR-typed callback routine customizes the operation of the I8042prt mouse ISR.
old-location: hid\pi8042_mouse_isr.htm
old-project: hid
ms.assetid: 7c8a0dc8-49ec-476f-b183-1baa419e831d
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: MSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MouseIsr
req.alt-loc: ntdd8042.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.iface: 
---

# PI8042_MOUSE_ISR callback



## -description
<p>A PI8042_MOUSE_ISR-typed callback routine customizes the operation of the I8042prt mouse ISR.</p>


## -prototype

````
PI8042_MOUSE_ISR MouseIsr;

BOOLEAN MouseIsr(
  _In_    PVOID                 IsrContext,
  _In_    PMOUSE_INPUT_DATA     CurrentInput,
  _In_    POUTPUT_PACKET        CurrentOutput,
  _In_    UCHAR                 StatusByte,
  _In_    PUCHAR                Byte,
  _Inout_ PBOOLEAN              ContinueProcessing,
  _In_    PMOUSE_STATE          MouseState,
  _In_    PMOUSE_RESET_SUBSTATE ResetSubState
)
{ ... }
````


## -parameters
<dl>

### -param <i>IsrContext</i> [in]

<dd>
<p>Pointer to the filter device object of the driver that supplies this callback.</p>
</dd>

### -param <i>CurrentInput</i> [in]

<dd>
<p>Pointer to the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a> structure being constructed by the ISR.</p>
</dd>

### -param <i>CurrentOutput</i> [in]

<dd>
<p>Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543218">OUTPUT_PACKET</a> structure, which specifies an array of bytes being written to the hardware device.</p>
</dd>

### -param <i>StatusByte</i> [in]

<dd>
<p>Specifies a status byte that is read from I/O port 60 when the interrupt occurs.</p>
</dd>

### -param <i>Byte</i> [in]

<dd>
<p>Specifies a data byte that is read from I/O port 64 when the interrupt occurs.</p>
</dd>

### -param <i>ContinueProcessing</i> [in, out]

<dd>
<p>Specifies, if <b>TRUE</b>, that processing in the I8042prt mouse ISR will continue after this callback completes. Otherwise, processing does not continue.</p>
</dd>

### -param <i>MouseState</i> [in]

<dd>
<p>Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542405">MOUSE_STATE</a> enumeration value, which identifies the state of mouse input.</p>
</dd>

### -param <i>ResetSubState</i> [in]

<dd>
<p>Pointer to MOUSE_RESET_SUBSTATE enumeration value, which identifies the mouse reset substate. See the Remarks section.</p>
</dd>
</dl>

## -returns
<p>A PI8042_MOUSE_ISR callback returns <b>TRUE</b> if the I8042prt mouse ISR should continue; otherwise it returns <b>FALSE</b>.</p>

## -remarks
<p>A PI8042_MOUSE_ISR callback is not needed if the default operation of the I8042prt mouse ISR is sufficient.</p>

<p>An upper-level keyboard filter driver can provide a mouse ISR callback. After the I8042prt mouse ISR validates the interrupt, it calls the mouse ISR callback.</p>

<p>To reset a mouse, I8042prt goes through a sequence of operational substates, each one of which is identified by a MOUSE_RESET_SUBSTATE enumeration value. For more information about how I8042prt resets a mouse and the corresponding mouse reset substates, see the documentation of MOUSE_RESET_SUBSTATE in ntdd8042.h.</p>

<p>A PI8042_MOUSE_ISR callback runs in kernel mode at the IRQL of the I8042prt mouse ISR.</p>

<p>A PI8042_MOUSE_ISR callback is not needed if the default operation of the I8042prt mouse ISR is sufficient.</p>

<p>An upper-level keyboard filter driver can provide a mouse ISR callback. After the I8042prt mouse ISR validates the interrupt, it calls the mouse ISR callback.</p>

<p>To reset a mouse, I8042prt goes through a sequence of operational substates, each one of which is identified by a MOUSE_RESET_SUBSTATE enumeration value. For more information about how I8042prt resets a mouse and the corresponding mouse reset substates, see the documentation of MOUSE_RESET_SUBSTATE in ntdd8042.h.</p>

<p>A PI8042_MOUSE_ISR callback runs in kernel mode at the IRQL of the I8042prt mouse ISR.</p>

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
<dt>Ntdd8042.h (include Ntdd8042.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/34d0a7e9-4a1e-43ba-a643-800ebaadc360">MouFilter_IsrHook</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542405">MOUSE_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543218">OUTPUT_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_MOUSE_ISR callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
