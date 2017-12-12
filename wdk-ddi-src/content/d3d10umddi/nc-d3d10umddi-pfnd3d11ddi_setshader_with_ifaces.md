---
UID: NC.d3d10umddi.PFND3D11DDI_SETSHADER_WITH_IFACES
title: PFND3D11DDI_SETSHADER_WITH_IFACES
author: windows-driver-content
description: The CsSetShaderWithIfaces function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces.
old-location: display\cssetshaderwithifaces.htm
old-project: display
ms.assetid: 2e7170e8-2b77-45a7-9ff5-834452c13ddf
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShaderWithIfaces is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CsSetShaderWithIfaces
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
---

# PFND3D11DDI_SETSHADER_WITH_IFACES callback



## -description
The <b>CsSetShaderWithIfaces</b> function sets the compute shader code along with a group of interfaces so that all of the subsequent dispatching operations use that code and those interfaces. 



## -prototype

````
PFND3D11DDI_SETSHADER_WITH_IFACES CsSetShaderWithIfaces;

VOID APIENTRY CsSetShaderWithIfaces(
  _In_       D3D10DDI_HDEVICE        hDevice,
  _In_       D3D10DDI_HSHADER        hShader,
  _In_       UINT                    NumClassInstances,
  _In_ const UINT                    *pIfaces,
  _In_ const D3D11DDIARG_POINTERDATA *pPointerData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hShader [in]

 A handle to the compute shader code object. 


### -param NumClassInstances [in]

 The number of class instances for implementations of the interfaces. 


### -param pIfaces [in]

 An array of function table identifiers. Each identifier corresponds to a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 


### -param pPointerData [in]

 An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_pointerdata.md">D3D11DDIARG_POINTERDATA</a> structures. Each structure describes the location of the data that is referenced by a class instance that is assigned to an interface implementation. The number of elements in the array is specified by the <i>NumClassInstances</i> parameter. 


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.


## -remarks
Each class instance for an interface implementation has the following pieces of information:  

Code that is associated with that class instance

A location for the data that is used by that class instance

The <i>NumClassInstances</i> parameter specifies the number of interfaces that must be assigned values at run time. For each interface, each element of the <b>pIfaces</b> array provides a function table identifier, and each element of the <b>pPointerData</b> array provides the data locations for a class instance that is assigned to the interface. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.


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
CsSetShaderWithIfaces is supported beginning with the Windows 7 operating system. 

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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs~r1.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_pointerdata.md">D3D11DDIARG_POINTERDATA</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_SETSHADER_WITH_IFACES callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

