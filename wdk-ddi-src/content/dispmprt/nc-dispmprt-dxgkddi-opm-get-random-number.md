---
UID: NC.dispmprt.DXGKDDI_OPM_GET_RANDOM_NUMBER
title: DXGKDDI_OPM_GET_RANDOM_NUMBER
author: windows-driver-content
description: The DxgkDdiOPMGetRandomNumber function retrieves the given protected output object's 128-bit cryptographically secure random number.
old-location: display\dxgkddiopmgetrandomnumber.htm
old-project: display
ms.assetid: 91b07a5c-ed25-4268-bd6d-273ae8b1ac28
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiOPMGetRandomNumber
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
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: IDebugSystemObjects4
---

# DXGKDDI_OPM_GET_RANDOM_NUMBER callback



## -description
<p>The<i> DxgkDdiOPMGetRandomNumber</i> function retrieves the given protected output object's 128-bit cryptographically secure random number.</p>


## -prototype

````
DXGKDDI_OPM_GET_RANDOM_NUMBER DxgkDdiOPMGetRandomNumber;

NTSTATUS DxgkDdiOPMGetRandomNumber(
  _In_  PVOID                      MiniportDeviceContext,
  _In_  HANDLE                     ProtectedOutputHandle,
  _Out_ PDXGKMDT_OPM_RANDOM_NUMBER RandomNumber
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportDeviceContext</i> [in]

<dd>
<p>A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.</p>
</dd>

### -param <i>ProtectedOutputHandle</i> [in]

<dd>
<p>The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-create-protected-output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.</p>
</dd>

### -param <i>RandomNumber</i> [out]

<dd>
<p>A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt--dxgkmdt-opm-random-number.md">DXGKMDT_OPM_RANDOM_NUMBER</a> structure that receives the protected output object's 128-bit cryptographically secure random number if <i>DxgkDdiOPMGetRandomNumber</i> returns successfully.</p>
<p>If <i>DxgkDdiOPMGetRandomNumber</i> fails, the value that <i>RandomNumber</i> points to is unchanged.</p>
<p>Each protected output object must have a different 128-bit cryptographically secure random number associated with it. </p>
</dd>
</dl>

## -returns
<p><i>DxgkDdiOPMGetRandomNumber</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. </p>

## -remarks
<p><i>DxgkDdiOPMGetRandomNumber</i> is called only once for each protected output and is never called after the call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-set-signing-key-and-sequence-numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function occurs.</p>

<p>For more information about cryptographically secure random numbers, see section 2.8 in <i>Applied Cryptography</i>, Second Edition.</p>

<p><i>DxgkDdiOPMGetRandomNumber</i> should be made pageable.</p>

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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-create-protected-output.md">DxgkDdiOPMCreateProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-opm-set-signing-key-and-sequence-numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt--dxgkmdt-opm-random-number.md">DXGKMDT_OPM_RANDOM_NUMBER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_RANDOM_NUMBER callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
