---
UID: NC:wdfdmaenabler.PFN_WDFDMAENABLERGETFRAGMENTLENGTH
title: PFN_WDFDMAENABLERGETFRAGMENTLENGTH function
author: windows-driver-content
description: The WdfDmaEnablerGetFragmentLength method returns the maximum transfer length that the operating system supports for a single DMA transfer.
old-location: wdf\wdfdmaenablergetfragmentlength.htm
old-project: wdf
ms.assetid: f7481655-4413-4937-8a0a-99ca07d5b7b0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFDMAENABLERGETFRAGMENTLENGTH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.1
req.umdf-ver: 
req.alt-api: WdfDmaEnablerGetFragmentLength
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
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFDMAENABLERGETFRAGMENTLENGTH function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerGetFragmentLength</b> method returns the maximum transfer length that the operating system supports for a single <a href="wdf.dma_transactions_and_dma_transfers">DMA transfer</a>.



## -syntax

````
size_t WdfDmaEnablerGetFragmentLength(
  _In_ WDFDMAENABLER     DmaEnabler,
  _In_ WDF_DMA_DIRECTION DmaDirection
);
````


## -parameters

### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>. 


### -param DmaDirection [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. For more information, see the following Remarks section.


## -returns
<b>WdfDmaEnablerGetFragmentLength</b> returns the maximum length of a DMA transfer, in bytes, that the operating system can support, or zero if the <i>DmaDirection</i> parameter's value is invalid.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The maximum DMA transfer length that the operating system can support depends on the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554406">map registers</a> that are available. If enough map registers are available, <b>WdfDmaEnablerGetFragmentLength</b> returns the same value that <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumlength.md">WdfDmaEnablerGetMaximumLength</a> returns. Otherwise, the value that <b>WdfDmaEnablerGetFragmentLength</b> returns will be less than the value that <b>WdfDmaEnablerGetMaximumLength</b> returns.

Your driver can determine the number of map registers that are available by using the BYTE_TO_PAGES macro, as follows:

If your driver specified a duplex profile when it called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, the <i>DmaDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the maximum transfer length for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the maximum transfer length for write operations. If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b> for <i>DmaDirection</i>.

Note that if your driver's device supports duplex operation, <b>WdfDmaEnablerGetFragmentLength</b> can return different values for the read and write directions that the <i>DmaDirection</i> parameter specifies. This difference is because the framework creates a separate <a href="https://msdn.microsoft.com/8bc672b4-0f4d-4e0c-9904-c8d0a3f3639c">adapter object</a> for each direction, and the operating system might provide a different number of map registers to each adapter object.

The following code example determines the minimum number of map registers that are necessary to handle a NIC device's read operations, calculates the number of map registers that are available, and reports an error if the number of allocated map registers is insufficient.


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
1.1

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
&lt;=DISPATCH_LEVEL

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
<a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablergetmaximumlength.md">WdfDmaEnablerGetMaximumLength</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerGetFragmentLength method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

