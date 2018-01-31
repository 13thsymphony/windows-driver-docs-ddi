---
UID : NF:hidpi.HidP_GetLinkCollectionNodes
title : HidP_GetLinkCollectionNodes function
author : windows-driver-content
description : The HidP_GetLinkCollectionNodes routine returns a top-level collection's link collection array.
old-location : hid\hidp_getlinkcollectionnodes.htm
old-project : hid
ms.assetid : d829b203-8b7f-4504-a9ac-da1f91b3bbd6
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : hidpi/HidP_GetLinkCollectionNodes, hidfunc_cbcd531f-dc4d-4a27-96bd-bfa3589af9a7.xml, hid.hidp_getlinkcollectionnodes, HidP_GetLinkCollectionNodes, HidP_GetLinkCollectionNodes routine [Human Input Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hidpi.h
req.include-header : Hidpi.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hidparse.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HIDP_REPORT_TYPE
---


# HidP_GetLinkCollectionNodes function
The <b>HidP_GetLinkCollectionNodes</b> routine returns a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection array</a>.

## Syntax

````
NTSTATUS __stdcall HidP_GetLinkCollectionNodes(
  _Out_   PHIDP_LINK_COLLECTION_NODE LinkCollectionNodes,
  _Inout_ PULONG                     LinkCollectionNodesLength,
  _In_    PHIDP_PREPARSED_DATA       PreparsedData
);
````

## Parameters

`LinkCollectionNodes`

Pointer to a caller-allocated array of HIDP_LINK_COLLECTION_NODE structures in which <b>HidP_GetLinkCollectionNodes</b> returns a top-level collection's link collection array.

`LinkCollectionNodesLength`

Specifies, on input, the length, in array elements, of the <i>LinkCollectionNodes</i> buffer. On output, the routine sets <i>LinkCollectionNodesLength</i> to the number of entries in the array that it set.

`PreparsedData`

Pointer to the preparsed data of the top-level collection for which this routine returns a link collection array.


## Return Value

<b>HidP_GetLinkCollectionNodes</b> returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the specified collection's link collection array.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL </b></dt>
</dl>
</td>
<td width="60%">
The <i>LinkCollectionNodes</i> buffer is too small to hold the entire link collection array.

</td>
</tr>
</table>

## Remarks

The required length of the <i>LinkCollectionNodes</i> buffer is specified by the <b>NumberLinkCollectionNodes</b> member of a collection's <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure.

If <b>HidP_GetLinkCollectionNodes</b> returns the status value HIDP_STATUS_BUFFER_TOO_SMALL, it also sets <i>LinkCollectionNodesLength</i> to the length, in array elements, required to hold the link collection nodes information.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hidpi.h (include Hidpi.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

<a href="..\hidpi\ns-hidpi-_hidp_link_collection_node.md">HIDP_LINK_COLLECTION_NODE</a>

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetLinkCollectionNodes routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>