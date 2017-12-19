---
UID: NC.d3d10umddi.PFND3D10DDI_RESOURCEMAP
title: PFND3D10DDI_RESOURCEMAP
author: windows-driver-content
description: The ResourceMap function maps a subresource of a resource.
old-location: display\resourcemap.htm
old-project: display
ms.assetid: 1310a3f8-02dd-4d35-98ad-4016e57d1eb2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResourceMap
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

# PFND3D10DDI_RESOURCEMAP callback



## -description
The <i>ResourceMap</i> function maps a subresource of a resource.



## -prototype

````
PFND3D10DDI_RESOURCEMAP ResourceMap;

VOID APIENTRY ResourceMap(
  _In_  D3D10DDI_HDEVICE            hDevice,
  _In_  D3D10DDI_HRESOURCE          hResource,
  _In_  UINT                        Subresource,
  _In_  D3D10_DDI_MAP               DDIMap,
  _In_  UINT                        Flags,
  _Out_ D3D10DDI_MAPPED_SUBRESOURCE *pMappedSubResource
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hResource [in]

 A handle to the resource to map.


### -param Subresource [in]

 An index that indicates the subresource to map. 


### -param DDIMap [in]

 A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a>-typed value that indicates the access level to map the subresource to. 


### -param Flags [in]

 A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map_flag.md">D3D10_DDI_MAP_FLAG</a>-typed value that indicates how to map the subresource. 


### -param pMappedSubResource [out]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_mapped_subresource.md">D3D10DDI_MAPPED_SUBRESOURCE</a> structure that receives the information about the mapped subresource.


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section. 


## -remarks
The driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to set the D3DDDIERR_DEVICEREMOVED error code.

Typically, immediately after the runtime receives the D3DDDIERR_DEVICEREMOVED error code, the runtime will no longer call into the user-mode display driver for much (other than for unbinding, destruction, and other cleanup operations).  

Typically, each call to the user-mode display driver's <i>ResourceMap</i> function is accompanied with a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function; however, after the runtime receives the D3DDDIERR_DEVICEREMOVED error code, it will not call <i>ResourceUnmap</i>.

If the runtime passed the D3D10_DDI_MAP_FLAG_DONOTWAIT flag in the <i>Flags</i> parameter, the driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to set the DXGI_DDI_ERR_WASSTILLDRAWING error code.

The driver can implement one pair of <i>ResourceMap</i> and <i>ResourceUnmap</i> functions that can contain <b>switch</b> statements to process various functionalities. That is, the driver can implement one <i>ResourceMap</i>-<i>ResourceUnmap</i> pair and can set the following members of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a> structure to point to this implementation pair:

<b>pfnDynamicIABufferMapDiscard</b>-<b>pfnDynamicIABufferUnmap</b>

<b>pfnDynamicIABufferMapNoOverwrite</b>-<b>pfnDynamicIABufferUnmap</b>

<b>pfnDynamicConstantBufferMapDiscard</b>-<b>pfnDynamicConstantBufferUnmap</b>

<b>pfnDynamicResourceMapDiscard</b>-<b>pfnDynamicResourceUnmap</b>

<b>pfnStagingResourceMap</b>-<b>pfnStagingResourceUnmap</b>

However, to improve performance, the driver can implement separate map-unmap function pairs. The Microsoft Direct3D runtime calls the appropriate map-unmap function pair depending on the resource type (for example, a buffer or texture) and the type of <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a>, <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>, and <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a> values that are specified when the resource is created and mapped.

The following example code shows the values that are set when the Direct3D runtime calls specific map or unmap function:

For Windows Display Driver Model (WDDM) 1.3 and later drivers, the Microsoft Direct3D runtime supplies a restricted set of input values used by this function. For a list of all restricted values, see <a href="https://msdn.microsoft.com/F9AAE489-EC45-4EE6-875E-E084BB3054EE">Direct3D rendering performance improvements</a>.


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map.md">D3D10_DDI_MAP</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_map_flag.md">D3D10_DDI_MAP_FLAG</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_usage.md">D3D10_DDI_RESOURCE_USAGE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_mapped_subresource.md">D3D10DDI_MAPPED_SUBRESOURCE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCEMAP callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

