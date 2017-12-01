---
UID: NF.storport.StorPortValidateRange
title: StorPortValidateRange
author: windows-driver-content
description: The StorPortValidateRange routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems.
old-location: storage\storportvalidaterange.htm
old-project: storage
ms.assetid: 505d6986-c59d-46b3-8437-29fc6a808ccd
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortValidateRange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortValidateRange
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: StorPortDeprecated
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# StorPortValidateRange function



## -description
<p>The <b>StorPortValidateRange</b> routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems. </p>


## -syntax

````
STORPORT_API BOOLEAN StorPortValidateRange(
  _In_ PVOID                 HwDeviceExtension,
  _In_ INTERFACE_TYPE        BusType,
  _In_ ULONG                 SystemToBusNumber,
  _In_ STOR_PHYSICAL_ADDRESS IoAddress,
  _In_ ULONG                 NumberOfBytes,
  _In_ BOOLEAN               InIoSpace
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param <i>BusType</i> [in]

<dd>
<p>Contains a value of type <a href="storage.storage_bus_type">STORAGE_BUS_TYPE</a> that indicates the bus type. </p>
</dd>

### -param <i>SystemToBusNumber</i> [in]

<dd>
<p>Contains an integer identifying a system bus.</p>
</dd>

### -param <i>IoAddress</i> [in]

<dd>
<p>Contains the beginning address of the range of addresses to be validated. </p>
</dd>

### -param <i>NumberOfBytes</i> [in]

<dd>
<p>Contains the length in bytes of the range of addresses to be validated. </p>
</dd>

### -param <i>InIoSpace</i> [in]

<dd>
<p>Indicates, when <b>TRUE</b>, that the address range is in I/O space. If <b>FALSE</b>, the address is in memory space. </p>
</dd>
</dl>

## -returns
<p><b>StorPortValidateRange</b> returns <b>TRUE</b> if a specified range of addresses is not claimed by another driver. This routine returns <b>FALSE</b> if another driver has claimed the address range. </p>

## -remarks
<p>For compatibility with older versions of Windows, this routine always returns <b>TRUE</b>.</p>

<p> Miniport drivers are given valid I/O ranges in the <b>AccessRanges</b> member of the <a href="..\strmini\ns-strmini--port-configuration-information~r1.md">PORT_CONFIGURATION_INFORMATION</a> structure when the Storport driver calls the miniport's <a href="storage.hwstorfindadapter">HwStorFindAdapter</a> callback routine.</p>

<p><b>StorPortValidateRange</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent bus-relative addresses.</p>

<p>The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.storport_storportdeprecated">StorPortDeprecated</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortValidateRange routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
