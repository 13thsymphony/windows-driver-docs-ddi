---
UID: NC.d3d10umddi.PFND3D11_1DDI_GETCAPTUREHANDLE
title: PFND3D11_1DDI_GETCAPTUREHANDLE
author: windows-driver-content
description: Returns the handle for a specified resource that was allocated by the driver. This function also returns the size and location of specified data within the resource.
old-location: display\getcapturehandle.htm
old-project: display
ms.assetid: b1ca7cf0-fe63-452f-8360-fdba05875719
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetCaptureHandle
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_GETCAPTUREHANDLE callback



## -description
Returns the handle for a specified resource that was allocated by the driver. This function also returns the size and location of specified data within the resource.



## -prototype

````
PFND3D11_1DDI_GETCAPTUREHANDLE GetCaptureHandle;

VOID APIENTRY* GetCaptureHandle(
  _In_    D3D10DDI_HDEVICE                hDevice,
  _Inout_ D3D11_1DDI_GETCAPTUREHANDLEDATA *pHandleData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pHandleData [in, out]

A pointer to a <a href="display.d3d11_1ddi_getcapturehandledata">D3D11_1DDI_GETCAPTUREHANDLEDATA</a> structure that defines the resource allocation. 


## -returns
This callback function does not return a value.


## -remarks
Before the Microsoft Direct3D runtime calls the <i>GetCaptureHandle</i> function, it sets the <b>hResource</b>  and <b>ArrayIndex</b> members of the <a href="display.d3d11_1ddi_getcapturehandledata">D3D11_1DDI_GETCAPTUREHANDLEDATA</a> structure to specify a resource. When this function is called, the driver updates the structure with the kernel mode allocation handle associated with the specified resource, as well as the size of the resource data and its offset within an allocated block of memory.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3d11_1ddi_getcapturehandledata">D3D11_1DDI_GETCAPTUREHANDLEDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCAPTUREHANDLE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

