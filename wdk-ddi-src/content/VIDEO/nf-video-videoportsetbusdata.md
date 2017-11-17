---
UID: NF.video.VideoPortSetBusData
title: VideoPortSetBusData
author: windows-driver-content
description: The VideoPortSetBusData function sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
old-location: display\videoportsetbusdata.htm
ms.assetid: 2a9ce391-718e-4be0-9699-7612b63d31f0
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortSetBusData
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
ms.keywords: VideoPortSetBusData
req.iface: 
req.product: Windows 10 or later.
---

# VideoPortSetBusData function



## -description
<p>The <b>VideoPortSetBusData</b> function sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.</p>


## -syntax

````
ULONG VideoPortSetBusData(
       PVOID         HwDeviceExtension,
       BUS_DATA_TYPE BusDataType,
       ULONG         SlotNumber,
  _In_ PVOID         Buffer,
       ULONG         Offset,
       ULONG         Length
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param <i>BusDataType</i> 

<dd>
<p>Specifies the type of bus data to be set. Currently, its value can be one of <b>Cmos</b>, <b>EisaConfiguration</b>, or <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses might be supported in the future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>.
      
     </p>
</dd>

### -param <i>SlotNumber</i> 

<dd>
<p>For a <i>BusDataType</i> value of <b>Cmos</b>, specifies the location of the device on the bus. This parameter should be zero for all other bus types.</p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>.</p>
<p>When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a> information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied.</p>
</dd>

### -param <i>Offset</i> 

<dd>
<p>Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG.</p>
</dd>

### -param <i>Length</i> 

<dd>
<p>Specifies the number of bytes in <i>Buffer</i>.</p>
</dd>
</dl>

## -returns
<p><b>VideoPortSetBusData</b> returns the number of bytes of data successfully set for the given <i>SlotNumber</i>. If the given <i>BusDataType</i> is not valid for the current platform or if the supplied information is invalid, <b>VideoPortSetBusData</b> returns zero.</p>

## -remarks
<p>Miniport drivers of adapters on a PCI bus seldom call <b>VideoPortSetBusData</b>, unless unusual circumstances or the nature of a particular driver's video adapter requires such a call.</p>

<p>For example, a miniport driver might call <b>VideoPortSetBusData</b> to clear a bit in the PCI status register if its adapter signals a target abort during initialization. If a PCI video adapter must be configured with device-specific data, its driver also calls this function. In either case, such a driver is then likely to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> with a <i>RequestedResources</i> pointer to a driver-supplied array of resource descriptors.</p>

<p><b>VideoPortSetBusData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>. </p>

<p>Miniport drivers of adapters on a PCI bus seldom call <b>VideoPortSetBusData</b>, unless unusual circumstances or the nature of a particular driver's video adapter requires such a call.</p>

<p>For example, a miniport driver might call <b>VideoPortSetBusData</b> to clear a bit in the PCI status register if its adapter signals a target abort during initialization. If a PCI video adapter must be configured with device-specific data, its driver also calls this function. In either case, such a driver is then likely to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> with a <i>RequestedResources</i> pointer to a driver-supplied array of resource descriptors.</p>

<p><b>VideoPortSetBusData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558790">PCI_SLOT_NUMBER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSetBusData function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
