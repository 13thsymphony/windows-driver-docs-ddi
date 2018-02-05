---
UID : NE:wdfdmaenabler._WDF_DMA_PROFILE
title : "_WDF_DMA_PROFILE"
author : windows-driver-content
description : The WDF_DMA_PROFILE enumeration identifies the types of bus-master or system-mode DMA operations that devices can support.
old-location : wdf\wdf_dma_profile.htm
old-project : wdf
ms.assetid : a2672bca-5c2e-423d-9ba0-fad610170e88
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDmaProfileSystemDuplex, DFDmaObjectRef_24cd95b0-ec51-4af4-a507-04f9a91276cf.xml, wdf.wdf_dma_profile, WdfDmaProfileInvalid, wdfdmaenabler/WdfDmaProfilePacket, wdfdmaenabler/WdfDmaProfileScatterGather64Duplex, wdfdmaenabler/WdfDmaProfileScatterGather64, WdfDmaProfileScatterGather64, wdfdmaenabler/WdfDmaProfileScatterGatherDuplex, WDF_DMA_PROFILE, wdfdmaenabler/WDF_DMA_PROFILE, WdfDmaProfileScatterGather, _WDF_DMA_PROFILE, WDF_DMA_PROFILE enumeration, wdfdmaenabler/WdfDmaProfileInvalid, kmdf.wdf_dma_profile, WdfDmaProfilePacket64, WdfDmaProfileScatterGather64Duplex, wdfdmaenabler/WdfDmaProfileSystemDuplex, WdfDmaProfileScatterGatherDuplex, wdfdmaenabler/WdfDmaProfilePacket64, wdfdmaenabler/WdfDmaProfileScatterGather, wdfdmaenabler/WdfDmaProfileSystem, WdfDmaProfilePacket, WdfDmaProfileSystem
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfdmaenabler.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DMA_PROFILE
req.product : Windows 10 or later.
---

# _WDF_DMA_PROFILE Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_PROFILE</b> enumeration identifies the types of bus-master or system-mode DMA operations that devices can support.

## Syntax
````
typedef enum _WDF_DMA_PROFILE { 
  WdfDmaProfileInvalid                = 0,
  WdfDmaProfilePacket                 = 1,
  WdfDmaProfileScatterGather          = 2,
  WdfDmaProfilePacket64               = 3,
  WdfDmaProfileScatterGather64        = 4,
  WdfDmaProfileScatterGatherDuplex    = 5,
  WdfDmaProfileScatterGather64Duplex  = 6,
  WdfDmaProfileSystem                 = 7,
  WdfDmaProfileSystemDuplex           = 8
} WDF_DMA_PROFILE;
````

## Constants

<table>

<tr>
<td>WdfDmaProfileInvalid</td>
<td>For internal use only.</td>
</tr>

<tr>
<td>WdfDmaProfilePacket</td>
<td>The device supports single-packet DMA operations, using 32-bit addressing.</td>
</tr>

<tr>
<td>WdfDmaProfilePacket64</td>
<td>The device supports single-packet DMA operations, using 64-bit addressing.</td>
</tr>

<tr>
<td>WdfDmaProfileScatterGather</td>
<td>The device supports packet-based, scatter/gather DMA operations, using 32-bit addressing.</td>
</tr>

<tr>
<td>WdfDmaProfileScatterGather64</td>
<td>The device supports packet-based, scatter/gather DMA operations, using 64-bit addressing.</td>
</tr>

<tr>
<td>WdfDmaProfileScatterGather64Duplex</td>
<td>The device supports packet-based, scatter/gather DMA operations, using 64-bit addressing. The device also supports duplex operation.</td>
</tr>

<tr>
<td>WdfDmaProfileScatterGatherDuplex</td>
<td>The device supports packet-based, scatter/gather DMA operations, using 32-bit addressing. The device also supports duplex operation.</td>
</tr>

<tr>
<td>WdfDmaProfileSystem</td>
<td>The device supports system-mode DMA operations. This value is available in version 1.11 and later versions of KMDF running on Windows 8 or later versions of Windows.</td>
</tr>

<tr>
<td>WdfDmaProfileSystemDuplex</td>
<td>The device supports system-mode DMA operations. The device also supports duplex operation. This value is available in version 1.11 and later versions of KMDF running on Windows 8 or later versions of Windows.</td>
</tr>
</table>

## Remarks

<b>WDF_DMA_PROFILE</b>-typed values are used within the driver's <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure. The driver supplies <b>WDF_DMA_ENABLER_CONFIG</b> when it calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

If the driver selects one of the system-mode DMA profiles, the framework requests the DMA version 3 interface from WDM.  System-mode DMA is available starting in Windows 8. For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

Kernel-Mode Driver Framework (KMDF) miniport drivers such as NDIS miniport drivers can request the system-mode DMA profiles. For information about how to write a framework-based miniport driver, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Creating Framework-based Miniport Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdmaenabler.h (include Wdf.h) |

## See Also

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_PROFILE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>