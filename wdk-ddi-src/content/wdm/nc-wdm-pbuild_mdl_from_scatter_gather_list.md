---
UID: NC.wdm.PBUILD_MDL_FROM_SCATTER_GATHER_LIST
title: PBUILD_MDL_FROM_SCATTER_GATHER_LIST
author: windows-driver-content
description: The BuildMdlFromScatterGatherList routine builds an MDL from a scatter/gather list allocated by the system.Note  This routine is reserved for system use.
old-location: kernel\buildmdlfromscattergatherlist.htm
old-project: kernel
ms.assetid: 2bf190a3-cc42-42b4-b687-cd66021e66c2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BuildMdlFromScatterGatherList
req.alt-loc: wdm.h
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback



## -description
The <b>BuildMdlFromScatterGatherList</b> routine builds an MDL from a scatter/gather list allocated by the system.



## -prototype

````
PBUILD_MDL_FROM_SCATTER_GATHER_LIST BuildMdlFromScatterGatherList;

NTSTATUS BuildMdlFromScatterGatherList(
  _In_  PADAPTER_OBJECT      DmaAdapter,
  _In_  PSCATTER_GATHER_LIST ScatterGather,
  _In_  PMDL                 OriginalMdl,
  _Out_ PMDL                 *TargetMdl
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

Pointer to the <a href="kernel.dma_adapter">DMA_ADAPTER</a> structure returned by <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param ScatterGather [in]

Pointer to the <a href="kernel.scatter_gather_list">SCATTER_GATHER_LIST</a> structure passed to the driver's <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine.


### -param OriginalMdl [in]

Pointer to the original MDL that the driver used to build the scatter/gather list.


### -param TargetMdl [out]

Pointer to a variable the routine uses to return the MDL created to hold the buffer described by the scatter/gather list. The value returned can be the same as <i>OriginalMdl</i>.


## -returns
<b>BuildMdlFromScatterGatherList</b> returns one of the following status codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>OriginalMdl</i> parameter is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is not enough memory available to allocate a new MDL.
<dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl>The system has already created a new MDL for the memory locations in the scatter/gather list. (This only happens if the routine is called twice on the same scatter/gather list.)

 


## -remarks
<b>BuildMdlFromScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="kernel.dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

When a driver creates a scatter/gather list to write to a device, the system can make a copy of the data to be written, and use that copy to perform the DMA operation. Use this routine to access the memory locations in the scatter/gather list, regardless of whether those locations are a copy.


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
Available in Windows XP and later versions of Windows. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_irqldispatch">IrqlDispatch</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_description">DEVICE_DESCRIPTION</a>
</dt>
<dt>
<a href="kernel.dma_adapter">DMA_ADAPTER</a>
</dt>
<dt>
<a href="kernel.dma_operations">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="kernel.scatter_gather_list">SCATTER_GATHER_LIST</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>
</dt>
<dt>
<a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

