---
UID: NC:d3dkmddi.DXGKDDI_DESTROYDEVICE
title: DXGKDDI_DESTROYDEVICE function
author: windows-driver-content
description: The DxgkDdiDestroyDevice function destroys a graphics context device.
old-location: display\dxgkddidestroydevice.htm
old-project: display
ms.assetid: c067fe92-2364-4122-a7ed-03df7906ae64
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_DESTROYDEVICE
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
req.alt-api: DxgkDdiDestroyDevice
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

# DXGKDDI_DESTROYDEVICE function



## -description
The <i>DxgkDdiDestroyDevice</i> function destroys a graphics context device.



## -syntax

````
DXGKDDI_DESTROYDEVICE DxgkDdiDestroyDevice;

NTSTATUS APIENTRY DxgkDdiDestroyDevice(
  _In_ const HANDLE hDevice
)
{ ... }
````


## -parameters

### -param hDevice [in]

[in] A handle to the graphics context device that <i>DxgkDdiDestroyDevice</i> will destroy. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure. 


## -returns
<i>DxgkDdiDestroyDevice</i> returns STATUS_SUCCESS, or an appropriate error result if the graphics context device is not successfully destroyed. 


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiDestroyDevice</i> function to destroy a graphics context device that the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function created. <i>DxgkDdiDestroyDevice</i> should free all of the resources that were allocated for the device and clean up any internal tracking data structures. 

<i>DxgkDdiDestroyDevice</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DESTROYDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

