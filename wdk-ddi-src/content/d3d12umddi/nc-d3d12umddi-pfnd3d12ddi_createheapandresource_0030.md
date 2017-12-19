---
UID: NC.d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
author: windows-driver-content
description: Used to simultaneously create a heap and resource.
old-location: display\pfnd3d12ddi_createheapandresource_0030.htm
old-project: display
ms.assetid: A6D597AA-C72A-46A5-91E8-22B225B380F2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
req.alt-loc: d3d12umddi.h
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

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to simultaneously create a heap and resource.



## -prototype

````
HRESULT  APIENTRY* PFND3D12DDI_CREATEHEAPANDRESOURCE_0030(
                 D3D12DDI_HDEVICE                        d3d12ddi_hdevice,
  _In_opt_ const D3D12DDIARG_CREATEHEAP_0001             *d3d12ddiarg_createheap_0001,
                 D3D12DDI_HHEAP                          d3d12ddi_hheap,
                 D3D12DDI_HRTRESOURCE                    d3d12ddi_hrtresource,
  _In_opt_ const D3D12DDIARG_CREATERESOURCE_0003         *d3d12ddiarg_createresource_0003,
  _In_opt_ const D3D12DDI_CLEAR_VALUES                   *d3d12ddi_clear_values,
                 D3D12DDI_HPROTECTEDRESOURCESESSION_0030 d3d12ddi_hprotectedresourcesession_0030,
                 D3D12DDI_HRESOURCE                      d3d12ddi_hresource
);
````


## -parameters

### -param d3d12ddi_hdevice 

The device being operated on.


### -param d3d12ddiarg_createheap_0001 [in, optional]

Arguments used to create a heap.


### -param d3d12ddi_hheap 

Used to create a heap.


### -param d3d12ddi_hrtresource 

Used to create a resource.


### -param d3d12ddiarg_createresource_0003 [in, optional]

Arguments used to create a resource.


### -param d3d12ddi_clear_values [in, optional]

Used to clear the values of the resource.


### -param d3d12ddi_hprotectedresourcesession_0030 

The protected resource session.


### -param d3d12ddi_hresource 

The hardware resource.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>