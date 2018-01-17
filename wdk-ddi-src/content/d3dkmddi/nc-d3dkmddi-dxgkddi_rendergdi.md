---
UID: NC:d3dkmddi.DXGKDDI_RENDERGDI
title: DXGKDDI_RENDERGDI function
author: windows-driver-content
description: DxgkDdiRenderGdi is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkddirendergdi.htm
old-project: display
ms.assetid: 90C34125-FC32-46E3-81F7-6B2AACED9BAC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_RENDERGDI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiRenderGdi
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
req.irql: 
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_RENDERGDI function



## -description
<b>DxgkDdiRenderGdi</b> is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.



## -syntax

````
DXGKDDI_RENDERGDI DxgkDdiRenderGdi;

NTSTATUS APIENTRY DxgkDdiRenderGdi(
  _In_    const HANDLE            hContext,
  _Inout_       DXGKARG_RENDERGDI *pRenderGdi
)
{ ... }
````


## -parameters

### -param hContext [in]

A handle to a context block that is associated with a display adapter. 


### -param pRenderGdi [in, out]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_rendergdi.md">DXGKARG_RENDERGDI</a> structure that describes operation.


## -returns
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>The submitted command is well-formed.
<dl>
<dt>(other)</dt>
</dl>All other return values will lead to the OS <i>bugcheck</i>.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_rendergdi.md">DXGKARG_RENDERGDI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RENDERGDI callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

