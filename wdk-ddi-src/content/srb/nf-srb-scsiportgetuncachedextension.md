---
UID: NF.srb.ScsiPortGetUncachedExtension
title: ScsiPortGetUncachedExtension
author: windows-driver-content
description: The ScsiPortGetUncachedExtension routine allocates memory that can be used by both the CPU and a bus-master HBA for DMA or for shared data.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportgetuncachedextension.htm
old-project: storage
ms.assetid: d32da7d9-7f26-4c99-8c10-3b9e1a7c9c22
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiPortGetUncachedExtension
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
req.alt-api: ScsiPortGetUncachedExtension
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

# ScsiPortGetUncachedExtension function



## -description
<p>The <b>ScsiPortGetUncachedExtension</b> routine allocates memory that can be used by both the CPU and a bus-master HBA for DMA or for shared data.</p>


## -syntax

````
PVOID ScsiPortGetUncachedExtension(
  _In_ PVOID                           HwDeviceExtension,
  _In_ PPORT_CONFIGURATION_INFORMATION ConfigInfo,
  _In_ ULONG                           NumberOfBytes
);
````


## -parameters
<dl>

### -param HwDeviceExtension [in]

<dd>
<p>Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="..\srb\nf-srb-scsiportinitialize.md">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param ConfigInfo [in]

<dd>
<p>Specifies information about the HBA's DMA capabilities. The following members must be filled in: <b>DmaChannel</b> or <b>DmaPort</b>, <b>DmaWidth</b>, <b>DmaSpeed</b>, <b>MaximumTransferLength</b>, <b>ScatterGather</b>, <b>Master</b> set to <b>TRUE</b>, <b>NumberOfPhysicalBreaks</b>, <b>AdapterInterfaceType</b>, <b>Dma32BitAddresses</b>, <b>SystemIoBusNumber</b>, <b>AutoRequestSense</b>, and <b>SrbExtensionSize.</b></p>
<p>Members that are not pertinent to the HBA, such as <b>DmaChannel</b> for an EISA bus-master adapter, must be left as is.</p>
</dd>

### -param NumberOfBytes [in]

<dd>
<p>Indicates the size in bytes of the uncached extension to be allocated. Drivers in Windows XP and earlier operating systems must not allocate more than 100 kilobytes of uncached extension, and if they participate in I/O operations on the hibernation file or the crash dump file, they must limit the amount of uncached extension that they allocate to under 32 kilobytes. </p>
</dd>
</dl>

## -returns
<p><b>ScsiPortGetUncachedExtension</b> returns a virtual address pointer to the uncached extension. If it cannot allocate the requested memory, it returns <b>NULL</b>.</p>

## -remarks
<p><b>ScsiPortGetUncachedExtension</b> can be called only from miniport driver's <a href="storage.hwscsifindadapter">HwScsiFindAdapter</a> routine and only for a bus-master HBA. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.</p>

<p>Because high-end machines have caches and large memories, any memory to be shared between an HBA and the CPU must be specially allocated. Mailboxes or I/O request queues in system memory are examples of this type of shared memory.</p>

<p>A miniport driver must set <b>SrbExtensionSize.</b> before calling <b>ScsiPortGetUncachedExtension</b> to change the size of its per-request storage based on <b>NumberOfPhysicalBreaks</b>.</p>

<p>The <a href="storage.hwscsifindadapter">HwScsiFindAdapter</a> routine can call <b>ScsiPortGetUncachedExtension</b> only once for each bus-master HBA the miniport driver supports.</p>

<p>To obtain the physical address for the uncached extension that the HBA can use, call <a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a>.</p>

<p>The ScsiPort driver will free the memory allocated by <b>ScsiPortGetUncachedExtension</b> when the adapter device is stopped.</p>

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
<a href="storage.port_configuration_information__scsi_">PORT_CONFIGURATION_INFORMATION (SCSI)</a>
</dt>
<dt>
<a href="storage.hwscsifindadapter">HwScsiFindAdapter</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortGetUncachedExtension routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
