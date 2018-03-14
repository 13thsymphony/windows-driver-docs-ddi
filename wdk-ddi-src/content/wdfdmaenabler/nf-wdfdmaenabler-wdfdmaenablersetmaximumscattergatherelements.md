---
UID: NF:wdfdmaenabler.WdfDmaEnablerSetMaximumScatterGatherElements
title: WdfDmaEnablerSetMaximumScatterGatherElements function
author: windows-driver-content
description: The WdfDmaEnablerSetMaximumScatterGatherElements method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object.
old-location: wdf\wdfdmaenablersetmaximumscattergatherelements.htm
old-project: wdf
ms.assetid: fdfcb8bc-bc42-4c34-ae19-b40401bea41e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_d9f2c46d-5981-4997-96b6-5a9db0dbfd8d.xml, WdfDmaEnablerSetMaximumScatterGatherElements, WdfDmaEnablerSetMaximumScatterGatherElements method, kmdf.wdfdmaenablersetmaximumscattergatherelements, wdf.wdfdmaenablersetmaximumscattergatherelements, wdfdmaenabler/WdfDmaEnablerSetMaximumScatterGatherElements
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
-	WdfDmaEnablerSetMaximumScatterGatherElements
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---


# WdfDmaEnablerSetMaximumScatterGatherElements function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerSetMaximumScatterGatherElements</b> method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object.

## Syntax

````
VOID WdfDmaEnablerSetMaximumScatterGatherElements(
  _In_ WDFDMAENABLER DmaEnabler,
  _In_ size_t        MaximumFragments
);
````

## Parameters

`DmaEnabler`

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

`MaximumFragments`

The maximum number of scatter/gather elements that the driver and device can support.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

If your driver calls <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, it must do so within the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function.

If your driver does not call <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, the framework uses a default value of WDF_DMA_ENABLER_UNLIMITED_FRAGMENTS, which means that there is no limit to the number of scatter/gather elements.

For more information about this method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>.


#### Examples

The following code example sets the maximum number of scatter/gather elements for a specified DMA enabler object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDmaEnablerSetMaximumScatterGatherElements(
                                             DmaEnabler, 
                                             NIC_MAX_PHYS_BUF_COUNT
                                             );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdmaenabler.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumscattergatherelements.md">WdfDmaEnablerGetMaximumScatterGatherElements</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerSetMaximumScatterGatherElements method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>