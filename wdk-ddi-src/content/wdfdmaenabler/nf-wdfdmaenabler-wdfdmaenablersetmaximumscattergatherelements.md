---
UID: NF:wdfdmaenabler.WdfDmaEnablerSetMaximumScatterGatherElements
title: WdfDmaEnablerSetMaximumScatterGatherElements function
author: windows-driver-content
description: The WdfDmaEnablerSetMaximumScatterGatherElements method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object.
old-location: wdf\wdfdmaenablersetmaximumscattergatherelements.htm
old-project: wdf
ms.assetid: fdfcb8bc-bc42-4c34-ae19-b40401bea41e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfDmaEnablerSetMaximumScatterGatherElements
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
req.alt-api: WdfDmaEnablerSetMaximumScatterGatherElements
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
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
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WdfDmaEnablerSetMaximumScatterGatherElements function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerSetMaximumScatterGatherElements</b> method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object. 



## -syntax

````
VOID WdfDmaEnablerSetMaximumScatterGatherElements(
  _In_ WDFDMAENABLER DmaEnabler,
  _In_ size_t        MaximumFragments
);
````


## -parameters

### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


### -param MaximumFragments [in]

The maximum number of scatter/gather elements that the driver and device can support.   


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If your driver calls <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, it must do so within the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function.

If your driver does not call <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, the framework uses a default value of WDF_DMA_ENABLER_UNLIMITED_FRAGMENTS, which means that there is no limit to the number of scatter/gather elements.

For more information about this method, see <a href="https://msdn.microsoft.com/87735776-c371-425b-bc53-0c68375c9562">Enabling DMA Transactions</a>.

The following code example sets the maximum number of scatter/gather elements for a specified DMA enabler object.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdmaenabler.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumscattergatherelements.md">WdfDmaEnablerGetMaximumScatterGatherElements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerSetMaximumScatterGatherElements method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

