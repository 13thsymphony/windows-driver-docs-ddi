---
UID: NC:d3dkmddi.DXGKDDI_RESTARTFROMTIMEOUT
title: DXGKDDI_RESTARTFROMTIMEOUT function
author: windows-driver-content
description: The DxgkDdiRestartFromTimeout function indicates that the driver can access the graphics processing unit (GPU) again after the recovery from a hardware timeout has completed.
old-location: display\dxgkddirestartfromtimeout.htm
old-project: display
ms.assetid: 433babb7-9a53-4079-9a65-43a5ed0c201a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_RESTARTFROMTIMEOUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiRestartFromTimeout
req.alt-loc: d3dkmddi.h
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
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_RESTARTFROMTIMEOUT function



## -description
The <i>DxgkDdiRestartFromTimeout</i> function indicates that the driver can access the graphics processing unit (GPU) again after the recovery from a hardware timeout has completed.



## -syntax

````
DXGKDDI_RESTARTFROMTIMEOUT DxgkDdiRestartFromTimeout;

NTSTATUS APIENTRY DxgkDdiRestartFromTimeout(
  _In_ const HANDLE hAdapter
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


## -returns
<i>DxgkDdiRestartFromTimeout</i> returns STATUS_SUCCESS to indicate that the driver handled the call successfully; otherwise, the operating system bug checks and causes a restart. 


## -remarks
The operating system calls the <i>DxgkDdiRestartFromTimeout</i> function after the recovery of a hardware tim-eout completes from the operating system's perspective (for example, all of the system-managed resources, mappings, and so on are released). The <i>DxgkDdiRestartFromTimeout</i> function indicates that the driver can begin to access the GPU and release any driver-managed resources. However, most drivers might not be required to perform any actions during a call to <i>DxgkDdiRestartFromTimeout</i>. Regardless of whether <i>DxgkDdiRestartFromTimeout</i> performs any actions, it must still be implemented and can simply return STATUS_SUCCESS immediately.

<i>DxgkDdiRestartFromTimeout</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetfromtimeout.md">DxgkDdiResetFromTimeout</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RESTARTFROMTIMEOUT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

