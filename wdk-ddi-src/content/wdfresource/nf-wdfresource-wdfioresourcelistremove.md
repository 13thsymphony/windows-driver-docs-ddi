---
UID : NF:wdfresource.WdfIoResourceListRemove
title : WdfIoResourceListRemove function
author : windows-driver-content
description : The WdfIoResourceListRemove method removes a resource descriptor from a resource requirements list's logical configuration.
old-location : wdf\wdfioresourcelistremove.htm
old-project : wdf
ms.assetid : fc67afc9-7542-4fca-bfc7-4b03b9d39735
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfioresourcelistremove, PFN_WDFIORESOURCELISTREMOVE, WdfIoResourceListRemove method, wdf.wdfioresourcelistremove, WdfIoResourceListRemove, DFResourceObjectRef_c8550890-69b9-493b-83d5-8a160eb85b8a.xml, wdfresource/WdfIoResourceListRemove
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfresource.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product : Windows 10 or later.
---


# WdfIoResourceListRemove function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListRemove</b> method removes a resource descriptor from a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.

## Syntax

````
VOID WdfIoResourceListRemove(
  _In_ WDFIORESLIST ResourceList,
  _In_ ULONG        Index
);
````

## Parameters

`ResourceList`

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.

`Index`

A zero-based value that is used as an index into the logical configuration that <i>ResourceList</i> specifies.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfIoResourceListRemove</b> method removes the resource descriptor that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfIoResourceListRemove</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistremovebydescriptor.md">WdfIoResourceListRemoveByDescriptor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListRemove method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>