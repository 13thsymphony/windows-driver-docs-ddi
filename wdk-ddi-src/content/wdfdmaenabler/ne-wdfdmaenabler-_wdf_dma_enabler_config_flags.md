---
UID: NE.wdfdmaenabler._WDF_DMA_ENABLER_CONFIG_FLAGS
title: _WDF_DMA_ENABLER_CONFIG_FLAGS
author: windows-driver-content
description: The WDF_DMA_ENABLER_CONFIG_FLAGS enumeration type defines flags that are used in a driver's WDF_DMA_ENABLER_CONFIG structure.
old-location: wdf\wdf_dma_enabler_config_flags.htm
old-project: wdf
ms.assetid: 8F8C97B2-5C77-4AD0-9434-22108111F5A8
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_DMA_ENABLER_CONFIG_FLAGS, WDF_DMA_ENABLER_CONFIG_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WDF_DMA_ENABLER_CONFIG_FLAGS
req.alt-loc: wdfdmaenabler.h
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
req.product: Windows 10 or later.
---

# _WDF_DMA_ENABLER_CONFIG_FLAGS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_ENABLER_CONFIG_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure.



## -syntax

````
typedef enum _WDF_DMA_ENABLER_CONFIG_FLAGS { 
  WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION  = 1,
  WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER  = 2
} WDF_DMA_ENABLER_CONFIG_FLAGS;
````


## -enum-fields

### -field WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION


           The WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION flag applies only  to the following DMA profiles:

<ul>
<li>WdfDmaProfileScatterGather</li>
<li>WdfDmaProfileScatterGather64</li>
<li>WdfDmaProfileScatterGatherDuplex </li>
<li>WdfDmaProfileScatterGather64Duplex</li>
</ul>
 
      By default, when <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is not set and the <a href="wdf.wdf_dma_profile">WDF_DMA_PROFILE</a> is one of those in the previous list, WDF  
      creates a lookaside list of scatter/gather lists that is  used by this DMA adapter's transaction 
      objects. The list entries are initialized to allow the maximum specified  
      transfer length. When the transaction is executed, WDF calls the <a href="kernel.buildscattergatherlist">BuildScatterGatherList</a> entry function. Forward progress drivers 
      must not set this flag and must use one of the four profiles shown previously.

 When <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is set and the <a href="wdf.wdf_dma_profile">WDF_DMA_PROFILE</a> is one of those in the previous list, WDF does not create a lookaside list. When the transaction is executed, WDF calls  <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>.

Setting <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> can result in reduced memory usage, particularly when the maximum transfer length is large. However, setting this flag may cause failure to perform DMA operations in low memory conditions. To guarantee forward progress when <b>WDF_DMA_ENABLER_CONFIG_NO_SGLIST_PREALLOCATION</b> is set, a driver might use a separate DMA enabler, or bounce transfers through a common buffer.


### -field WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER

The <b>WDF_DMA_ENABLER_CONFIG_REQUIRE_SINGLE_TRANSFER</b> flag is available starting in version 1.19 of KMDF.  This flag also requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

This flag applies to all DMA profiles. When it is set, WDF does not fragment any WDFDMATRANSACTION created with this enabler into multiple DMA transfers. If this is not possible, attempts to initialize or execute the transaction fail. This option is intended for devices that need to receive all data in a single DMA operation.

Drivers also have the option of specifying this on a per-transaction level with <a href="wdf.wdfdmatransactionsetsingletransferrequirement">WdfDmaTransactionSetSingleTransferRequirement</a>.

For more info, see <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/using-single-transfer-dma">Using Single Transfer DMA</a>.


## -remarks
You can specify a valid bitwise OR of the values on this page for the <b>Flags</b> member of the <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.11

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
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_dma_profile">WDF_DMA_PROFILE</a>
</dt>
<dt>
<a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionsetsingletransferrequirement">WdfDmaTransactionSetSingleTransferRequirement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_ENABLER_CONFIG_FLAGS enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

