---
UID : NE:wdfchildlist._WDF_RETRIEVE_CHILD_FLAGS
title : _WDF_RETRIEVE_CHILD_FLAGS
author : windows-driver-content
description : The WDF_RETRIEVE_CHILD_FLAGS enumeration defines flags that a driver can set before calling WdfChildListBeginIteration.
old-location : wdf\wdf_retrieve_child_flags.htm
old-project : wdf
ms.assetid : 43294943-cc73-45d4-8e0b-e7d29420bb7e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_RETRIEVE_CHILD_FLAGS, WDF_RETRIEVE_CHILD_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfchildlist.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WDF_RETRIEVE_CHILD_FLAGS
req.alt-loc : wdfchildlist.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : WDF_RETRIEVE_CHILD_FLAGS
req.product : Windows 10 or later.
---

# _WDF_RETRIEVE_CHILD_FLAGS Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_RETRIEVE_CHILD_FLAGS</b> enumeration defines flags that a driver can set before calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.

## Syntax
````
typedef enum _WDF_RETRIEVE_CHILD_FLAGS { 
  WdfRetrieveUnspecified      = 0x0000,
  WdfRetrievePresentChildren  = 0x0001,
  WdfRetrieveMissingChildren  = 0x0002,
  WdfRetrievePendingChildren  = 0x0004,
  WdfRetrieveAddedChildren    = (WdfRetrievePresentChildren | WdfRetrievePendingChildren),
  WdfRetrieveAllChildren      = (WdfRetrievePresentChildren | WdfRetrievePendingChildren | WdfRetrieveMissingChildren)
} WDF_RETRIEVE_CHILD_FLAGS;
````

## Constants

<table>

<tr>
<td>WdfRetrieveAddedChildren</td>
<td>Calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are present or pending.</td>
</tr>

<tr>
<td>WdfRetrieveAllChildren</td>
<td>Calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are present, pending, or missing.</td>
</tr>

<tr>
<td>WdfRetrieveMissingChildren</td>
<td>Calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are marked as missing.</td>
</tr>

<tr>
<td>WdfRetrievePendingChildren</td>
<td>Calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> will retrieve child devices that the driver has reported as present, but for which a framework device object has not been created (because the framework has not called the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> callback function).</td>
</tr>

<tr>
<td>WdfRetrievePresentChildren</td>
<td>Calls to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> will retrieve child devices for which a framework device object exists.</td>
</tr>

<tr>
<td>WdfRetrieveUnspecified</td>
<td>Reserved for internal use only.</td>
</tr>
</table>

## Remarks

Before calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>, your driver must set <b>WDF_RETRIEVE_CHILD_FLAGS</b>-typed flags in a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfchildlist.h (include Wdf.h) |

## See Also

<dl>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>
</dt>
<dt>
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_RETRIEVE_CHILD_FLAGS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>