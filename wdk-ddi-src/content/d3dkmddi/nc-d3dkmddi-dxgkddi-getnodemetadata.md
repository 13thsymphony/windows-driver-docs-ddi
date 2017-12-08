---
UID: NC.d3dkmddi.DXGKDDI_GETNODEMETADATA
title: DXGKDDI_GETNODEMETADATA
author: windows-driver-content
description: From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.
old-location: display\dxgkddigetnodemetadata.htm
old-project: display
ms.assetid: ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiGetNodeMetadata
req.alt-loc: D3dkmddi.h
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
req.iface: 
---

# DXGKDDI_GETNODEMETADATA callback



## -description
<p>From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.</p>


## -prototype

````
DXGKDDI_GETNODEMETADATA DxgkDdiGetNodeMetadata;

NTSTATUS APIENTRY DxgkDdiGetNodeMetadata(
  _In_  const HANDLE                  hAdapter,
  _In_        UINT                    NodeOrdinal,
  _Out_       DXGKARG_GETNODEMETADATA *pGetNodeMetadata
)
{ ... }
````


## -parameters
<dl>

### -param hAdapter [in]

<dd>
<p>[in] A handle that identifies a display adapter. The DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a> function.</p>
</dd>

### -param NodeOrdinal [in]

<dd>
<p>An index of a node for which engine information will be obtained. This node is within the physical adapter defined by the <i>hAdapter</i> parameter.</p>
</dd>

### -param pGetNodeMetadata [out]

<dd>
<p>A pointer to a <a href="display.dxgkarg_getnodemetadata">DXGKARG_GETNODEMETADATA</a> structure that contains the engine type and friendly name of the engine specified by the <i>NodeOrdinal</i> parameter.</p>
</dd>
</dl>

## -returns
<p>
      Returns one of the following values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi-getnodemetadata.md">DxgkDdiGetNodeMetadata</a> successfully retrieved the engine information.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The caller-provided <i>hAdapter</i> or <i>pGetNodeMetadata</i> parameters are invalid, or the caller-provided value of <i>NodeOrdinal</i> is greater than or equal to the number of nodes on the adapter.</p>

<p> </p>

<p>If the <i>hAdapter</i> and <i>pGetNodeMetadata</i> parameters are valid, and <i>NodeOrdinal</i> has a value in the range of 0 to (number of nodes - 1), all calls to this function must be successful.</p>

## -remarks
<p>For more information on how to implement this function, see <a href="https://msdn.microsoft.com/822FEB3E-A39D-4B33-BD9D-F3166EF99AF8">Enumerating GPU engine capabilities</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_getnodemetadata">DXGKARG_GETNODEMETADATA</a>
</dt>
<dt>
<a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_GETNODEMETADATA callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
