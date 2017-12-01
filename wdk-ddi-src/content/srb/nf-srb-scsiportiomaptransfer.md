---
UID: NF.srb.ScsiPortIoMapTransfer
title: ScsiPortIoMapTransfer
author: windows-driver-content
description: The ScsiPortIoMapTransfer routine sets up the system DMA controller for a miniport driver to transfer data through a subordinate HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportiomaptransfer.htm
old-project: storage
ms.assetid: 627a2d4c-22c8-48ea-b409-dc246c85a316
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiPortIoMapTransfer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortIoMapTransfer
req.alt-loc: Scsiport.lib,Scsiport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Scsiport.lib
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# ScsiPortIoMapTransfer function



## -description
<p>The <b>ScsiPortIoMapTransfer</b> routine sets up the system DMA controller for a miniport driver to transfer data through a subordinate HBA.</p>


## -syntax

````
VOID ScsiPortIoMapTransfer(
  _In_ PVOID               HwDeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK Srb,
  _In_ PVOID               LogicalAddress,
  _In_ ULONG               Length
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param <i>Srb</i> [in]

<dd>
<p>Pointer to the SCSI request block for the DMA transfer.</p>
</dd>

### -param <i>LogicalAddress</i> [in]

<dd>
<p>Specifies the starting address for the transfer operation. This value can be the base address of a buffer into which or from which data is to be transferred. This value can be an offset within such a buffer.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Specifies the number of bytes to be transferred.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Only miniport drivers of HBAs that use a system DMA controller (subordinate DMA) call <b>ScsiPortIoMapTransfer</b>. This routine must be called before such a miniport driver sets up its HBA to transfer data. The range specified by the <i>LogicalAddress</i> and <i>Length</i> must be within the buffer described by the given SRB.</p>

<p>After the operating system-specific port driver programs the system DMA controller, it calls the miniport driver's <a href="storage.hwscsidmastarted">HwScsiDmaStarted</a> routine. <i>HwScsiDmaStarted</i> should program the HBA to begin the data transfer. Note that an HBA can interrupt between the miniport driver's call to <b>ScsiPortIoMapTransfer</b> and the operating system-specific port driver's call to the miniport driver's <i>HwScsiDmaStarted</i> routine.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Srb.h (include Miniport.h or Scsi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Scsiport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hwscsidmastarted">HwScsiDmaStarted</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportflushdma.md">ScsiPortFlushDma</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortIoMapTransfer routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
