---
UID: NF.srb.ScsiPortFreeDeviceBase
title: ScsiPortFreeDeviceBase
author: windows-driver-content
description: The ScsiPortFreeDeviceBase routine frees a range of device I/O or memory space addresses previously mapped into the system address space with ScsiPortGetDeviceBase.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportfreedevicebase.htm
old-project: storage
ms.assetid: 391f3b20-175f-4b27-b30f-34ccc43ca650
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ScsiPortFreeDeviceBase
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
req.alt-api: ScsiPortFreeDeviceBase
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

# ScsiPortFreeDeviceBase function



## -description
<p>The <b>ScsiPortFreeDeviceBase</b> routine frees a range of device I/O or memory space addresses previously mapped into the system address space with <b>ScsiPortGetDeviceBase</b>.</p>


## -syntax

````
VOID ScsiPortFreeDeviceBase(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID MappedAddress
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param <i>MappedAddress</i> [in]

<dd>
<p>Pointer to the base address of the range to be freed. This address must be the same as that returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine determines that the driver does not need a particular mapped base address for an adapter, it must release the mapping by calling this routine. For example, when a miniport driver determines there are no supported HBAs on a particular I/O bus, it must call <b>ScsiPortFreeDeviceBase</b> with each mapped address returned by <b>ScsiPortGetDeviceBase</b>, if any calls to this routine were made.</p>

<p><b>ScsiPortFreeDeviceBase</b> can be called only from miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.</p>

<p>If a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine determines that the driver does not need a particular mapped base address for an adapter, it must release the mapping by calling this routine. For example, when a miniport driver determines there are no supported HBAs on a particular I/O bus, it must call <b>ScsiPortFreeDeviceBase</b> with each mapped address returned by <b>ScsiPortGetDeviceBase</b>, if any calls to this routine were made.</p>

<p><b>ScsiPortFreeDeviceBase</b> can be called only from miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortFreeDeviceBase routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
