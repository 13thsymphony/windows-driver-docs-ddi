---
UID: NF.srb.ScsiPortGetPhysicalAddress
title: ScsiPortGetPhysicalAddress
author: windows-driver-content
description: The ScsiPortGetPhysicalAddress routine converts a given virtual address range to a physical address range for a DMA operation.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportgetphysicaladdress.htm
old-project: storage
ms.assetid: 4a0d0b10-9773-40d7-962c-cf2acffcee47
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiPortGetPhysicalAddress
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
req.alt-api: ScsiPortGetPhysicalAddress
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

# ScsiPortGetPhysicalAddress function



## -description
<p>The <b>ScsiPortGetPhysicalAddress</b> routine converts a given virtual address range to a physical address range for a DMA operation.</p>


## -syntax

````
SCSI_PHYSICAL_ADDRESS ScsiPortGetPhysicalAddress(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _In_  PVOID               VirtualAddress,
  _Out_ ULONG               *Length
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param <i>Srb</i> [in]

<dd>
<p>Pointer to the SCSI request block if the <i>VirtualAddress</i> to be converted comes from that SRB's <b>DataBuffer</b> member or, possibly, from the <b>SenseInfoBuffer</b>. Otherwise, this parameter must be <b>NULL</b>.</p>
</dd>

### -param <i>VirtualAddress</i> [in]

<dd>
<p>Pointer to the base virtual address to be converted. If this virtual address falls within the range for an SRB-supplied <b>DataBuffer</b>, the caller also must provide the <i>Srb</i> pointer.</p>
</dd>

### -param <i>Length</i> [out]

<dd>
<p>Returns the number of bytes mapped, starting at the returned physical address.</p>
</dd>
</dl>

## -returns
<p><b>ScsiPortGetPhysicalAddress</b> returns the corresponding physical address for a given <i>VirtualAddress</i>. If the given address cannot be converted, it returns <b>NULL</b>.</p>

## -remarks
<p>Miniport drivers of bus-master HBAs call <b>ScsiPortGetPhysicalAddress</b> to get mapped physical address ranges to be used during DMA operations. For example, <b>ScsiPortGetPhysicalAddress</b> can be used to build a scatter/gather list for data transfers that span pages. Note that the <i>Length</i> returned can be greater than the size of the <b>DataBuffer</b> in a given SRB.</p>

<p>If a non-<b>NULL</b><i>Srb</i> is passed, the <i>VirtualAddress</i> either must be within the range of the <b>DataBuffer</b> of the SRB or must be a pointer from the <b>SenseInfoBuffer</b>. Otherwise, the given <i>VirtualAddress</i> must be in the miniport driver's uncached extension, the <b>SrbExtension</b>, or the<b> SenseInfoBuffer</b>.</p>

<p>A miniport driver can call <b>ScsiPortGetPhysicalAddress</b> to translate an extension address only if that miniport driver's <b>DriverEntry</b> routine set <b>NeedPhysicalAddresses</b> to <b>TRUE</b> in the HW_INITIALIZATION_DATA when it called <b>ScsiPortInitialize</b>.</p>

<p>Due to constraints on some buses, such as ISA, the address returned by this routine is not guaranteed to match the address returned by an analogous outside routine (such as <b>MmGetPhysicalAddress</b>). A miniport driver should call only <b>ScsiPort</b><i>Xxx</i> routines to be portable.</p>

<p><b>ScsiPortGetPhysicalAddress</b> uses <b>SCSI_PHYSICAL_ADDRESS</b> to represent physical addresses.</p>

<p>The <b>SCSI_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that SCSI miniport drivers use to represent either a physical addresses or a bus-relative address. </p>

<p>Miniport drivers of bus-master HBAs call <b>ScsiPortGetPhysicalAddress</b> to get mapped physical address ranges to be used during DMA operations. For example, <b>ScsiPortGetPhysicalAddress</b> can be used to build a scatter/gather list for data transfers that span pages. Note that the <i>Length</i> returned can be greater than the size of the <b>DataBuffer</b> in a given SRB.</p>

<p>If a non-<b>NULL</b><i>Srb</i> is passed, the <i>VirtualAddress</i> either must be within the range of the <b>DataBuffer</b> of the SRB or must be a pointer from the <b>SenseInfoBuffer</b>. Otherwise, the given <i>VirtualAddress</i> must be in the miniport driver's uncached extension, the <b>SrbExtension</b>, or the<b> SenseInfoBuffer</b>.</p>

<p>A miniport driver can call <b>ScsiPortGetPhysicalAddress</b> to translate an extension address only if that miniport driver's <b>DriverEntry</b> routine set <b>NeedPhysicalAddresses</b> to <b>TRUE</b> in the HW_INITIALIZATION_DATA when it called <b>ScsiPortInitialize</b>.</p>

<p>Due to constraints on some buses, such as ISA, the address returned by this routine is not guaranteed to match the address returned by an analogous outside routine (such as <b>MmGetPhysicalAddress</b>). A miniport driver should call only <b>ScsiPort</b><i>Xxx</i> routines to be portable.</p>

<p><b>ScsiPortGetPhysicalAddress</b> uses <b>SCSI_PHYSICAL_ADDRESS</b> to represent physical addresses.</p>

<p>The <b>SCSI_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that SCSI miniport drivers use to represent either a physical addresses or a bus-relative address. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557456">HW_INITIALIZATION_DATA (SCSI)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552654">DriverEntry of SCSI Miniport Driver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564639">ScsiPortGetUncachedExtension</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564643">ScsiPortGetVirtualAddress</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortGetPhysicalAddress routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
