---
UID: NS.D3DKMDDI._DXGKARG_QUERYADAPTERINFO
title: _DXGKARG_QUERYADAPTERINFO
author: windows-driver-content
description: The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.
old-location: display\dxgkarg_queryadapterinfo.htm
old-project: display
ms.assetid: 5992c846-93de-4f95-839a-81f14db709f7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_QUERYADAPTERINFO, DXGKARG_QUERYADAPTERINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_QUERYADAPTERINFO
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
---

# _DXGKARG_QUERYADAPTERINFO structure



## -description
The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.



## -syntax

````
typedef struct _DXGKARG_QUERYADAPTERINFO {
  DXGK_QUERYADAPTERINFOTYPE Type;
  VOID                      *pInputData;
  UINT                      InputDataSize;
  VOID                      *pOutputData;
  UINT                      OutputDataSize;
} DXGKARG_QUERYADAPTERINFO;
````


## -struct-fields

### -field Type

[in] A <a href="display.dxgk_queryadapterinfotype">DXGK_QUERYADAPTERINFOTYPE</a>-typed value that indicates the type of information to retrieve.


### -field pInputData

[in] A pointer to input information for the query. 

When <b>Type</b> specifies DXGKQAITYPE_UMDRIVERPRIVATE, <b>pInputData</b> points to a proprietary buffer that contains information about the query. When <b>Type</b> specifies DXGKQAITYPE_QUERYSEGMENT, <b>pInputData</b> points to a <a href="display.dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a> structure. When <b>Type</b> specifies <b>DXGKQAITYPE_POWERCOMPONENTINFO</b>, <b>pInputData</b> points to an input buffer that contains the power component index.

An input buffer is not required when <b>Type</b> specifies the DXGKQAITYPE_DRIVERCAPS value.


### -field InputDataSize

[in] The size, in bytes, of the input data that <b>pInputData</b> points to.


### -field pOutputData

[out] A pointer to an output buffer that the display miniport driver fills with the required information.

<table>
<tr>
<th>Value of <b>Type</b></th>
<th>Contents of output buffer pointed to by <b>pOutputData</b></th>
</tr>
<tr>
<td><b>DXGKQAITYPE_UMDRIVERPRIVATE</b></td>
<td>Proprietary buffer</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_DRIVERCAPS</b></td>
<td>Populated <a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT</b></td>
<td>Populated <a href="display.dxgk_querysegmentout">DXGK_QUERYSEGMENTOUT</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT3</b></td>
<td>Populated <a href="display.dxgk_querysegmentout3">DXGK_QUERYSEGMENTOUT3</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_NUMPOWERCOMPONENTS</b></td>
<td>A UINT value that specifies the number of power components used by the display miniport driver</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_POWERCOMPONENTINFO</b></td>
<td>Populated <a href="display.dxgk_power_runtime_component">DXGK_POWER_RUNTIME_COMPONENT</a> structure that provides information about the <i>n</i>th power component, where <i>n</i> is the component index specified by  <b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function</td>
</tr>
</table>
 


### -field OutputDataSize

[in] The size, in bytes, of the output data that <b>pOutputData</b> points to.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn268634">DXGK_POWER_P_COMPONENT</a>
</dt>
<dt>
<a href="display.dxgk_power_runtime_component">DXGK_POWER_RUNTIME_COMPONENT</a>
</dt>
<dt>
<a href="display.dxgk_queryadapterinfotype">DXGK_QUERYADAPTERINFOTYPE</a>
</dt>
<dt>
<a href="display.dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a>
</dt>
<dt>
<a href="display.dxgk_querysegmentout">DXGK_QUERYSEGMENTOUT</a>
</dt>
<dt>
<a href="display.dxgk_querysegmentout3">DXGK_QUERYSEGMENTOUT3</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYADAPTERINFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

