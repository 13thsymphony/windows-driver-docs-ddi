---
UID: NC:d3dkmddi.DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
title: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 function
author: windows-driver-content
description: DxgkDdiCheckMultiPlaneOverlaySupport2 is called to determine whether a specific multi-plane overlay configuration is supported.
old-location: display\dxgkddicheckmultiplaneoverlaysupport2.htm
old-project: display
ms.assetid: A453B59F-0DD1-4FFF-A0E6-09494211780F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiCheckMultiPlaneOverlaySupport2
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

# DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 function



## -description
<b>DxgkDdiCheckMultiPlaneOverlaySupport2</b> is called to determine whether a specific multi-plane overlay configuration is supported.  It must be implemented by Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays.



## -syntax

````
DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 DxgkDdiCheckMultiPlaneOverlaySupport2;

NTSTATUS APIENTRY DxgkDdiCheckMultiPlaneOverlaySupport2(
  _In_    const HANDLE                                 hAdapter,
  _Inout_       DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 *pData
)
{ ... }
````


## -parameters

### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pData [in, out]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport2.md">DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2</a> structure that describes the surfaces and display options to present.


## -returns
If this routine succeeds, it returns <b>NTSTATUS_SUCCESS</b>. The driver should always return a success code.


## -remarks
The kernel mode driver reports whether the specified configuration is supported.  The kernel mode driver should not raise or lower the available bandwidth in anticipation to this configuration getting set.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport2.md">DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

