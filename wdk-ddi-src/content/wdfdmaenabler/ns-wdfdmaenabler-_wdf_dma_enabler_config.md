---
UID: NS:wdfdmaenabler._WDF_DMA_ENABLER_CONFIG
title: "_WDF_DMA_ENABLER_CONFIG"
author: windows-driver-content
description: The WDF_DMA_ENABLER_CONFIG structure supplies characteristics for a DMA enabler object.
old-location: wdf\wdf_dma_enabler_config.htm
old-project: wdf
ms.assetid: 60702ce0-c15b-49ad-b983-af68086710b2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_DMA_ENABLER_CONFIG, DFDmaObjectRef_854b91a3-b389-47a9-bc88-d4796025f73e.xml, PWDF_DMA_ENABLER_CONFIG, PWDF_DMA_ENABLER_CONFIG structure pointer, WDF_DMA_ENABLER_CONFIG, WDF_DMA_ENABLER_CONFIG structure, _WDF_DMA_ENABLER_CONFIG, kmdf.wdf_dma_enabler_config, wdf.wdf_dma_enabler_config, wdfdmaenabler/PWDF_DMA_ENABLER_CONFIG, wdfdmaenabler/WDF_DMA_ENABLER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdmaenabler.h
api_name:
-	WDF_DMA_ENABLER_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_DMA_ENABLER_CONFIG, *PWDF_DMA_ENABLER_CONFIG
req.product: Windows 10 or later.
---

# _WDF_DMA_ENABLER_CONFIG structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_ENABLER_CONFIG</b> structure supplies characteristics for a DMA enabler object.

## Syntax
````
typedef struct _WDF_DMA_ENABLER_CONFIG {
  ULONG                                    Size;
  WDF_DMA_PROFILE                          Profile;
  size_t                                   MaximumLength;
  PFN_WDF_DMA_ENABLER_FILL                 EvtDmaEnablerFill;
  PFN_WDF_DMA_ENABLER_FLUSH                EvtDmaEnablerFlush;
  PFN_WDF_DMA_ENABLER_DISABLE              EvtDmaEnablerDisable;
  PFN_WDF_DMA_ENABLER_ENABLE               EvtDmaEnablerEnable;
  PFN_WDF_DMA_ENABLER_SELFMANAGED_IO_START EvtDmaEnablerSelfManagedIoStart;
  PFN_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP  EvtDmaEnablerSelfManagedIoStop;
  ULONG                                    AddressWidthOverride;
  ULONG                                    WdmDmaVersionOverride;
  ULONG                                    Flags;
} WDF_DMA_ENABLER_CONFIG, *PWDF_DMA_ENABLER_CONFIG;
````

## Members


`Size`

The size, in bytes, of this structure.

`Profile`

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_profile.md">WDF_DMA_PROFILE</a>-typed value, which identifies the type of bus-master DMA operation that will be associated with the DMA enabler object.

`MaximumLength`

The default maximum size, in bytes, that the device can handle in a single <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a>. (Drivers can override this default value for individual <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transactions</a> by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength.md">WdfDmaTransactionSetMaximumLength</a>.) If your driver must run on versions of Microsoft Windows operating systems that support a maximum of 16 <a href="https://msdn.microsoft.com/library/windows/hardware/ff554406">map registers</a>, <b>MaximumLength</b> must be less than 65,536.

`EvtDmaEnablerFill`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_fill.md">EvtDmaEnablerFill</a> event callback function, or <b>NULL</b>.

`EvtDmaEnablerFlush`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_flush.md">EvtDmaEnablerFlush</a> event callback function, or <b>NULL</b>.

`EvtDmaEnablerDisable`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_disable.md">EvtDmaEnablerDisable</a> event callback function, or <b>NULL</b>.

`EvtDmaEnablerEnable`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_enable.md">EvtDmaEnablerEnable</a> event callback function, or <b>NULL</b>.

`EvtDmaEnablerSelfManagedIoStart`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start.md">EvtDmaEnablerSelfManagedIoStart</a> event callback function, or <b>NULL</b>.

`EvtDmaEnablerSelfManagedIoStop`

A pointer to the driver's <a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop.md">EvtDmaEnablerSelfManagedIoStop</a> event callback function, or <b>NULL</b>.

`AddressWidthOverride`

Set to zero to accept the address width specified in <b>Profile</b>. A driver can override the <b>Profile</b>  address width by setting this member to a value between 24  and 63. If your driver specifies a system-mode DMA profile, <b>AddressWidthOverride</b> must be zero. If your driver specifies a 32-bit DMA profile, <b>AddressWidthOverride</b> cannot be greater than 32. The <b>AddressWidthOverride</b> member is available in version 1.11 and later versions of KMDF. See more information in <b>Remarks</b>.

`WdmDmaVersionOverride`

Set to zero to accept the default DMA version. To request DMA version 3, set to 3. The <b>WdmDmaVersionOverride</b> member is available in version 1.11 and in later versions of KMDF. DMA version 3 is available starting in Windows 8.

`Flags`

A bitwise OR of one or more values from the <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_enabler_config_flags.md">WDF_DMA_ENABLER_CONFIG_FLAGS</a> enumeration. The <b>Flags</b> member is available in version 1.11 and in later versions of KMDF.

## Remarks
The <b>WDF_DMA_ENABLER_CONFIG</b> structure is used as an input parameter to the <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a> method.

Drivers must call <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_enabler_config_init.md">WDF_DMA_ENABLER_CONFIG_INIT</a> to initialize the <b>WDF_DMA_ENABLER_CONFIG</b> structure.

In Windows 8 and later, when the driver provides a nonzero value for <b>AddressWidthOverride</b>, the framework requests DMA version 3 and passes the <b>AddressWidthOverride</b> value through to the HAL.

On Windows 7 and Windows Vista, when the driver provides a nonzero value for <b>AddressWidthOverride</b>, the framework uses either 32-bit or 24-bit DMA. For example, if the driver specifies a 64-bit profile and provides an <b>AddressWidthOverride</b> of 32, the framework uses 32-bit DMA.  If the driver specifies a 32-bit profile and provides an <b>AddressWidthOverride</b> of 24, the framework uses 24-bit DMA.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdmaenabler.h (include Wdf.h) |

## See Also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_flush.md">EvtDmaEnablerFlush</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop.md">EvtDmaEnablerSelfManagedIoStop</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_enable.md">EvtDmaEnablerEnable</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_fill.md">EvtDmaEnablerFill</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start.md">EvtDmaEnablerSelfManagedIoStart</a>



<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_enabler_config_init.md">WDF_DMA_ENABLER_CONFIG_INIT</a>



<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_disable.md">EvtDmaEnablerDisable</a>



<a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_profile.md">WDF_DMA_PROFILE</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetmaximumlength.md">WdfDmaTransactionSetMaximumLength</a>