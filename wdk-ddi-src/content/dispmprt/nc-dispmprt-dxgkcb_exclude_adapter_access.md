---
UID: NC.dispmprt.DXGKCB_EXCLUDE_ADAPTER_ACCESS
title: DXGKCB_EXCLUDE_ADAPTER_ACCESS
author: windows-driver-content
description: The DxgkCbExcludeAdapterAccess function prevents all access to the display adapter and calls a provided DxgkProtectedCallback callback routine while in this protected state.
old-location: display\dxgkcbexcludeadapteraccess.htm
old-project: display
ms.assetid: e74e79fe-3b36-427e-ae0b-4072a0438c4e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbExcludeAdapterAccess
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
---

# DXGKCB_EXCLUDE_ADAPTER_ACCESS callback



## -description
The <b>DxgkCbExcludeAdapterAccess</b> function prevents all access to the display adapter and calls a provided <a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a> callback routine while in this protected state.


## -prototype

````
DXGKCB_EXCLUDE_ADAPTER_ACCESS DxgkCbExcludeAdapterAccess;

NTSTATUS DxgkCbExcludeAdapterAccess(
  _In_ HANDLE                     DeviceHandle,
  _In_ ULONG                      Attributes,
  _In_ DXGKDDI_PROTECTED_CALLBACK DxgkProtectedCallback,
  _In_ PVOID                      ProtectedCallbackContext
)
{ ... }
````


## -parameters

### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver obtained this handle in the <b>DeviceHandle</b> member of the <a href="display.dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>.

### -param Attributes [in]

A value that specifies video memory operations. This parameter can be any combination of the following bit flag values, except that DXGK_EXCLUDE_EVICT_ALL and DXGK_EXCLUDE_CALL_SYNCHRONOUS are mutually exclusive. These values are defined in <i>Dispmprt.h</i>.


### -param DXGK_EXCLUDE_EVICT_ALL

All video memory in the adapter is copied to system memory; this is an expensive operation. If the <i>Attributes</i> parameter is not set to this value, access to locked surfaces in system memory is suspended.

### -param DXGK_EXCLUDE_CALL_SYNCHRONOUS

Executes the protected <a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a> driver callback routine in the same thread context as the caller. The caller must be calling from a <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level</a> or <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">third level</a> synchronized DDI call. Otherwise the <b>DxgkCbExcludeAdapterAccess</b> function will fail.

### -param DXGK_EXCLUDE_BRIDGE_ACCESS

Protects access to the PCI Express (PCIe) root port when the driver needs to access the root port configuration space. Set the <i>Attributes</i> parameter to this value before calling <a href="..\dispmprt\nc-dispmprt-dxgkcb_read_device_space.md">DxgkCbReadDeviceSpace</a> or <a href="..\dispmprt\nc-dispmprt-dxgkcb_write_device_space.md">DxgkCbWriteDeviceSpace</a> functions with the <i>DataType</i> parameter set to DXGK_WHICHSPACE_BRIDGE.
</dd>
</dl>

### -param DxgkProtectedCallback [in]

The callback routine to be called back when all access to the adapter has been halted.

### -param ProtectedCallbackContext [in]

A pointer to the value to pass to the <i>ProtectedCallbackContext</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a> callback routine.

## -returns
<b>DxgkCbExcludeAdapterAccess</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## -remarks
Application requests will be blocked until this function returns. While in this protective state, the provided <a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a> callback routine is called at IRQL = PASSIVE_LEVEL.

<b>DxgkCbExcludeAdapterAccess</b> acquires exclusive adapter access in order to prevent graphics-related I/O operations to the display adapter and all links. This effectively idles the GPU for the entire duration of the call.

This function also prevents all PCI configuration space access to the PCI Express (PCIe) root port if DXGK_EXCLUDE_BRIDGE_ACCESS is specified in the <i>Attributes</i> parameter.

The driver should not block continued execution of the calling thread by waiting for the <a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a> callback routine to return. For example, the driver could schedule an asynchronous worker thread to handle the callback routine.

An exception to this blocking of application requests occurs when the user-mode display driver has set the <b>UseAlternateVA</b> bit-field flag in the <b>Flags</b> member of the <a href="display.d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function. <b>DxgkCbExcludeAdapterAccess</b> does not block this type of allocation lock, and the CPU can access the display adapter while the protected callback routine is executing.

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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_protected_callback.md">DxgkProtectedCallback</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_EXCLUDE_ADAPTER_ACCESS callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
