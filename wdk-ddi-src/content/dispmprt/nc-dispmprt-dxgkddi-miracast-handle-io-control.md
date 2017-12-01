---
UID: NC.dispmprt.DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
title: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
author: windows-driver-content
description: Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the MiracastIoControl function.
old-location: display\dxgkddimiracastiocontrol.htm
old-project: display
ms.assetid: 83E817C3-A30D-4597-A490-C4FB93A78FCE
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiMiracastIoControl
req.alt-loc: Dispmprt.h
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
req.iface: IDebugSystemObjects4
---

# DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback



## -description
<p>Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function.</p>


## -prototype

````
DXGKDDI_MIRACAST_HANDLE_IO_CONTROL DxgkDdiMiracastIoControl;

NTSTATUS* DxgkDdiMiracastIoControl(
  _In_  PVOID DriverContext,
  _In_  PVOID MiracastContext,
  _In_  ULONG InputBufferSize,
  _In_  VOID  *pInputBuffer,
  _In_  ULONG OutBufferSize,
  _Out_ VOID  *pOutputBuffer,
  _Out_ ULONG *BytesReturned
)
{ ... }
````


## -parameters
<dl>

### -param <i>DriverContext</i> [in]

<dd>
<p>A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.</p>
</dd>

### -param <i>MiracastContext</i> [in]

<dd>
<p>The Miracast device context, supplied by the operating system. This context was provided by the display miniport driver in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-create-context.md">DxgkDdiMiracastCreateContext</a> function.</p>
</dd>

### -param <i>InputBufferSize</i> [in]

<dd>
<p>Supplied by the operating system as the size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.</p>
</dd>

### -param <i>pInputBuffer</i> [in]

<dd>
<p>Supplied by the operating system as a pointer to the input buffer. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.</p>
<p><i>InputBufferSize</i> specifies the size of the buffer.</p>
</dd>

### -param <i>OutBufferSize</i> [in]

<dd>
<p>Supplied by the operating system as the size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function's <i>OutputBufferSize</i> parameter.</p>
</dd>

### -param <i>pOutputBuffer</i> [out]

<dd>
<p>Supplied by the operating system as a pointer to the output buffer. This value originated as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function's <i>pOutputBuffer</i> parameter.</p>
<p><i>OutBufferSize</i> specifies the size of the buffer.</p>
</dd>

### -param <i>BytesReturned</i> [out]

<dd>
<p>Supplied by the operating system as a pointer to a buffer that holds a <b>ULONG</b>-type value that is the number of bytes that the display miniport driver returned in the buffer pointed to by <i>pOutputBuffer</i>.</p>
</dd>
</dl>

## -returns
<p>Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.</p>

## -remarks
<p>The operating system guarantees that a call to <i>DxgkDdiMiracastIoControl</i> occurs in the same process space as the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> request is called in. </p>

<p>Even though the operating system merely copies the values of the input and output buffer sizes from the respective parameters of <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a>, the display miniport driver is responsible for checking buffer sizes before using the buffers. Also, the driver should perform probing operations within a try/except calling block, using <a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a> and/or <a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a> functions, to verify any user-mode memory that input buffers point to.</p>

<p>This I/O control operation is processed synchronously with a call to the user-mode <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function.</p>

<p>The operating system groups the <a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-create-context.md">DxgkDdiMiracastCreateContext</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-destroy-context.md">DxgkDdiMiracastDestroyContext</a>, and <i>DxgkDdiMiracastIoControl</i> functions as a <i>Miracast</i> class. </p>

<p>The threading and synchronization level for this function is set by how the user-mode driver sets the <i>HardwareAccess</i> parameter in a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a> function:<ul>
<li>If <i>HardwareAccess</i> is <b>FALSE</b>, then the operating system guarantees that <i>DxgkDdiMiracastIoControl</i> follows the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. <i>DxgkDdiMiracastIoControl</i> can be called when other level 0, 1, or non-Miracast classes of level 2 functions are being called on another thread context. However, only one of the level 2 Miracast-class functions can be called at a time.</li>
<li>If <i>HardwareAccess</i> is <b>TRUE</b>, then <i>DxgkDdiMiracastIoControl</i> follows the third-level synchronization mode as defined in <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">Threading and Synchronization Third Level</a>. Note that the flushing of the GPU will create substantial processing overhead.</li>
</ul>
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-create-context.md">DxgkDdiMiracastCreateContext</a>
</dt>
<dt>
<a href="..\netdispumdddi\nc-netdispumdddi-pfn-miracast-io-control.md">MiracastIoControl</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
