---
UID: NC.dispmprt.DXGKCB_EVAL_ACPI_METHOD
title: DXGKCB_EVAL_ACPI_METHOD
author: windows-driver-content
description: The DxgkCbEvalAcpiMethod function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.
old-location: display\dxgkcbevalacpimethod.htm
ms.assetid: ce54cf4e-5b50-4142-b3c7-ff29b7bdbb35
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbEvalAcpiMethod
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
req.irql: PASSIVE_LEVEL
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
req.iface: IDebugSystemObjects4
---

# DXGKCB_EVAL_ACPI_METHOD callback



## -description
<p>The <b>DxgkCbEvalAcpiMethod</b> function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.</p>


## -prototype

````
DXGKCB_EVAL_ACPI_METHOD DxgkCbEvalAcpiMethod;

NTSTATUS DxgkCbEvalAcpiMethod(
  _In_  HANDLE                          DeviceHandle,
  _In_  ULONG                           DeviceUid,
  _In_  PACPI_EVAL_INPUT_BUFFER_COMPLEX AcpiInputBuffer,
  _In_  ULONG                           AcpiInputSize,
  _Out_ PACPI_EVAL_OUTPUT_BUFFER        AcpiOutputBuffer,
  _In_  ULONG                           AcpiOutputSize
)
{ ... }
````


## -parameters
<dl>

### -param <i>DeviceHandle</i> [in]

<dd>
<p>A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.</p>
</dd>

### -param <i>DeviceUid</i> [in]

<dd>
<p>The unique identifier for the ACPI device on which the method will be evaluated. If the ACPI device is a child of the display adapter, this is the <b>ChildUid</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure that the display miniport driver filled in during <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>. If the ACPI device is the display adapter itself, this parameter must be set to DISPLAY_ADAPTER_HW_ID.</p>
</dd>

### -param <i>AcpiInputBuffer</i> [in]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure (defined in <i>Acpiioct.h</i>) allocated and filled in by the display miniport driver. The structure contains the arguments that are required by the ACPI method. See the following Remarks section for more information.</p>
</dd>

### -param <i>AcpiInputSize</i> [in]

<dd>
<p>The total size, in bytes, of the buffer pointed to by <i>AcpiInputBuffer</i>.</p>
</dd>

### -param <i>AcpiOutputBuffer</i> [out]

<dd>
<p>A pointer to an ACPI_EVAL_OUTPUT_BUFFER structure (defined in <i>Acpiioct.h</i>) that receives the return value of the ACPI method. This parameter can be <b>NULL</b>.</p>
</dd>

### -param <i>AcpiOutputSize</i> [in]

<dd>
<p>The total size, in bytes, of the buffer pointed to by <i>AcpiOutputBuffer</i>.</p>
</dd>
</dl>

## -returns
<p><b>DxgkCbEvalAcpiMethod</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.</p>

## -remarks
<p>To evaluate ACPI methods on an ACPI device, the device itself must be in the ACPI namespace. In addition, the display miniport driver must have set the lower 16 bits of the <b>ChildUid</b> value for any ACPI child devices that the display miniport driver reports to the identifier that ACPI reported.</p>

<p>Before it returns, <b>DxgkCbEvalAcpiMethod</b> resets the <b>Signature</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE. In Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating systems, if the display miniport driver has child devices, it should set <b>Signature</b> to DXGK_ACPI_PASS_ARGS_TO_CHILDREN before it makes any call to <b>DxgkCbEvalAcpiMethod</b>.</p>

<p>The following code example shows how to evaluate an ACPI method.</p>

<p>To evaluate ACPI methods on an ACPI device, the device itself must be in the ACPI namespace. In addition, the display miniport driver must have set the lower 16 bits of the <b>ChildUid</b> value for any ACPI child devices that the display miniport driver reports to the identifier that ACPI reported.</p>

<p>Before it returns, <b>DxgkCbEvalAcpiMethod</b> resets the <b>Signature</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a> structure to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE. In Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating systems, if the display miniport driver has child devices, it should set <b>Signature</b> to DXGK_ACPI_PASS_ARGS_TO_CHILDREN before it makes any call to <b>DxgkCbEvalAcpiMethod</b>.</p>

<p>The following code example shows how to evaluate an ACPI method.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536116">ACPI_EVAL_INPUT_BUFFER_COMPLEX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fdefde51-0e90-4324-9c14-e8259fc872b3">DxgkDdiNotifyAcpiEvent</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_EVAL_ACPI_METHOD callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
