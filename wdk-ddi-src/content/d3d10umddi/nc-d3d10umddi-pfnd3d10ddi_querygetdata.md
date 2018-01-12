---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYGETDATA
title: PFND3D10DDI_QUERYGETDATA
author: windows-driver-content
description: The QueryGetData function polls for the state of a query operation.
old-location: display\querygetdata.htm
old-project: display
ms.assetid: 78ee9813-e23e-4d46-acc4-f2fa88559b03
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: QueryGetData
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

# PFND3D10DDI_QUERYGETDATA callback



## -description
The <i>QueryGetData</i> function polls for the state of a query operation. 



## -prototype

````
PFND3D10DDI_QUERYGETDATA QueryGetData;

VOID APIENTRY QueryGetData(
  _In_  D3D10DDI_HDEVICE hDevice,
  _In_  D3D10DDI_HQUERY  hQuery,
  _Out_ VOID             *pData,
  _Out_ UINT             DataSize,
  _In_  UINT             Flags
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param hQuery [in]

A handle to the query object to poll.
     


### -param pData [out]

A pointer to a region of memory that receives the data from a query operation. The user-mode display driver can set <i>pData</i> to <b>NULL</b> and set the <i>DataSize</i> parameter to zero. If <i>pData</i> is <b>NULL</b>, <i>QueryGetData</i> can indicate the state of the query operation (for example, whether the query operation is finished). 


### -param DataSize [out]


      The size, in bytes, of the query data that the <i>pData</i> parameter points to. The user-mode display driver can set <i>DataSize</i> to zero and set <i>pData</i> to <b>NULL</b>. If <i>DataSize</i> is zero, <i>QueryGetData</i> can indicate the state of the query operation (for example, through return codes). 
     


### -param Flags [in]

A bitwise OR of values. Currently, the D3D10_DDI_GET_DATA_DO_NOT_FLUSH (0x01L) value from the D3D10_DDI_GET_DATA_FLAG enumeration type is the only supported value. 


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.


## -remarks
After the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a> function to transition a query operation to the "issued" state, the runtime can call <i>QueryGetData</i> to determine if the query operation is still in the "issued" state (DXGI_DDI_ERR_WASSTILLDRAWING) or has transitioned to the "signaled" state (S_OK). If the query operation is in the "signaled" state, <i>QueryGetData</i> can return the query data in the <i>pData</i> parameter; otherwise, <i>pData</i> is unchanged. The driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to indicate the state of the query operation. 

The runtime cannot call <i>QueryGetData</i> with a predicate that was created with D3D10_QUERY_MISCFLAG_PREDICATEHINT through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function. 

If a query operation handles work that still resides in partial command buffers, by default, the driver should terminate and submit the partial command buffers. However, the driver should not terminate and submit the buffers if the runtime specified the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the <i>Flags</i> parameter. If the runtime passed the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the <i>Flags</i> parameter and if the query operation handles work that still resides in partial command buffers, the driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to set only the DXGI_DDI_ERR_WASSTILLDRAWING error code.

When the runtime calls <i>QueryGetData</i> to check for query completion, the driver can pass DXGI_DDI_ERR_WASSTILLDRAWING in a call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to indicate that the query is not finished yet. The driver can also pass D3DDDIERR_DEVICEREMOVED in a call to <i>pfnSetErrorCb</i>. The Direct3D runtime will determine that any other errors are critical. 


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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounter.md">CheckCounter</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_QUERYGETDATA callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

