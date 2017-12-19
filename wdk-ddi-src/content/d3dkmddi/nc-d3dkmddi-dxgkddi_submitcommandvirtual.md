---
UID: NC.d3dkmddi.DXGKDDI_SUBMITCOMMANDVIRTUAL
title: DXGKDDI_SUBMITCOMMANDVIRTUAL
author: windows-driver-content
description: DxgkDdiSubmitCommandVirtual is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.
old-location: display\dxgkddisubmitcommandvirtual.htm
old-project: display
ms.assetid: 7A55FB51-BDC2-4215-895E-3250579BEAF0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSubmitCommandVirtual
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
---

# DXGKDDI_SUBMITCOMMANDVIRTUAL callback



## -description
<b>DxgkDdiSubmitCommandVirtual</b> is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.



The driver is responsible for making sure the correct address space is restored ahead of submitting a particular DMA buffer.
  



## -prototype

````
DXGKDDI_SUBMITCOMMANDVIRTUAL DxgkDdiSubmitCommandVirtual;

NTSTATUS APIENTRY DxgkDdiSubmitCommandVirtual(
  _In_ const HANDLE                       hAdapter,
  _In_ const DXGKARG_SUBMITCOMMANDVIRTUAL *pSubmitCommand
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. 


### -param pSubmitCommand [in]

A pointer to a <a href="display.dxgkarg_submitcommandvirtual">DXGKARG_SUBMITCOMMANDVIRTUAL</a> structure that describes operation.


## -returns
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>The submitted command is well-formed.
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>The DMA or private data is determined to be malformed. In this case, the OS will put the calling device in an error state and all subsequent calls on it will fail. The <b>SubmissionFenceId</b> value passed to this call will be considered completed after all previous packets on the hardware finished and at that point the driver notion of the last completed fence ID should be updated to this value.
<dl>
<dt></dt>
</dl>All other return values will lead to the OS <i>bugcheck</i>.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_submitcommandvirtual">DXGKARG_SUBMITCOMMANDVIRTUAL</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SUBMITCOMMANDVIRTUAL callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

