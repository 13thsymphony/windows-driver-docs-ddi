---
UID: NC.dispmprt.DXGKDDI_MIRACAST_QUERY_CAPS
title: DXGKDDI_MIRACAST_QUERY_CAPS
author: windows-driver-content
description: Queries the Miracast capabilities of the current display adapter.
old-location: display\dxgkddimiracastquerycaps.htm
old-project: display
ms.assetid: C10CAA33-C407-4183-9090-B9D78B07CD12
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, PSYMBOL_INFO_EX, *PSYMBOL_INFO_EX
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
req.alt-api: DxgkDdiMiracastQueryCaps
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
---

# DXGKDDI_MIRACAST_QUERY_CAPS callback



## -description
Queries the Miracast capabilities of the current display adapter. The operating system  calls this function only when the display adapter is first started and then stores the capabilities that are returned.<div class="alert"><b>Note</b>  The capabilities of the display adapter must not change while it is connected.</div>
<div> </div>




## -prototype

````
DXGKDDI_MIRACAST_QUERY_CAPS DxgkDdiMiracastQueryCaps;

NTSTATUS* DxgkDdiMiracastQueryCaps(
  _In_  PVOID              DriverContext,
  _In_  ULONG              MiracastCapsSize,
  _Out_ DXGK_MIRACAST_CAPS *MiracastCaps
)
{ ... }
````


## -parameters

### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastCapsSize [in]

The size, supplied by the operating system, of the <a href="display.dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a> structure pointed to by the <i>MiracastCaps</i> parameter.

The driver should check this value before it fills the structure.


### -param MiracastCaps [out]

A pointer to an operating system-provided buffer that holds a <a href="display.dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a> structure that the driver fills with Miracast device capabilities.


## -returns
Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.


## -remarks
The operating system guarantees that this function follows the third-level synchronization mode as defined in <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">Threading and Synchronization Third Level</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
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
<a href="display.dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MIRACAST_QUERY_CAPS callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

