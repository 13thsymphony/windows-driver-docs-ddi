---
UID: NF:wdfpdo.WdfPdoInitAllowForwardingRequestToParent
title: WdfPdoInitAllowForwardingRequestToParent function
author: windows-driver-content
description: The WdfPdoInitAllowForwardingRequestToParent method enables a driver's ability to call WdfRequestForwardToParentDeviceIoQueue.
old-location: wdf\wdfpdoinitallowforwardingrequesttoparent.htm
old-project: wdf
ms.assetid: fc8e4484-4059-4274-bb61-5d3b2f965b19
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_1c47c0f6-2474-419b-8a6e-1105351ab1d7.xml, WdfPdoInitAllowForwardingRequestToParent, WdfPdoInitAllowForwardingRequestToParent method, kmdf.wdfpdoinitallowforwardingrequesttoparent, wdf.wdfpdoinitallowforwardingrequesttoparent, wdfpdo/WdfPdoInitAllowForwardingRequestToParent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfPdoInitAllowForwardingRequestToParent
product:
- Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---


# WdfPdoInitAllowForwardingRequestToParent function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAllowForwardingRequestToParent</b> method enables a driver's ability to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>.

## Syntax

```
void WdfPdoInitAllowForwardingRequestToParent(
  PWDFDEVICE_INIT DeviceInit
);
```

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## Return Value

None.

## Remarks

If your driver uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a> to requeue I/O requests from a child device's I/O queue to a parent device's I/O queue, the driver must call <b>WdfPdoInitAllowForwardingRequestToParent</b> before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> to create a physical device object (PDO) for the child device. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about <b>WdfPdoInitAllowForwardingRequestToParent</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a>.


#### Examples

The following code example enables a driver's ability to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfPdoInitAllowForwardingRequestToParent(pDeviceInit);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>