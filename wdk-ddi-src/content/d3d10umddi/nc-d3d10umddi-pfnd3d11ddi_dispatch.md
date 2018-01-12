---
UID: NC:d3d10umddi.PFND3D11DDI_DISPATCH
title: PFND3D11DDI_DISPATCH
author: windows-driver-content
description: The Dispatch function executes the compute shader.
old-location: display\dispatch.htm
old-project: display
ms.assetid: 6fbbf05a-efb0-4f24-8811-b87141cf2daa
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Dispatch is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dispatch
req.alt-loc: d3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11DDI_DISPATCH callback



## -description
The <b>Dispatch</b> function executes the compute shader.



## -prototype

````
PFND3D11DDI_DISPATCH Dispatch;

VOID APIENTRY Dispatch(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             ThreadGroupCountX,
  _In_ UINT             ThreadGroupCountY,
  _In_ UINT             ThreadGroupCountZ
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param ThreadGroupCountX [in]

 The size, in thread groups, of the x-dimension of the thread-group grid.  The maximum size is 65535. 


### -param ThreadGroupCountY [in]

 The size, in thread groups, of the y-dimension of the thread-group grid.  The maximum size is 65535. 


### -param ThreadGroupCountZ [in]

 The size, in thread groups, of the z-dimension of the thread-group grid.  The maximum size is 65535. 


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.


## -remarks
The Direct3D runtime calls the driver's <b>Dispatch</b> function on the display device to execute the compute shader.  A compiled compute shader defines the set of instructions to execute per thread and the number of threads to run per group.  The thread-group parameters (<i>ThreadGroupCountX</i>, <i>ThreadGroupCountY</i>, and <i>ThreadGroupCountZ</i>) indicate how many thread groups to execute. Each thread group contains the same number of threads, as defined by the compiled compute shader.  The thread groups are organized in a three-dimensional grid. The total number of thread groups that the compiled compute shader executes is determined by the following calculation:

In particular, if any of the values in the thread-group parameters are 0, the <b>Dispatch</b> function does nothing.  

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>Dispatch</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.


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
Dispatch is supported beginning with the Windows 7 operating system. 

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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_DISPATCH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

