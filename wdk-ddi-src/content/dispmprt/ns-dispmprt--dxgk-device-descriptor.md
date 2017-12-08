---
UID: NS.dispmprt._DXGK_DEVICE_DESCRIPTOR
title: DXGK_DEVICE_DESCRIPTOR
author: windows-driver-content
description: The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).
old-location: display\dxgk_device_descriptor.htm
old-project: display
ms.assetid: b6d89426-54d3-4f90-8687-c60e515b4d62
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_DEVICE_DESCRIPTOR
req.alt-loc: dispmprt.h
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
req.iface: 
---

# DXGK_DEVICE_DESCRIPTOR structure



## -description
<p>The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).</p>


## -syntax

````
typedef struct _DXGK_DEVICE_DESCRIPTOR {
  ULONG DescriptorOffset;
  ULONG DescriptorLength;
  PVOID DescriptorBuffer;
} DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field DescriptorOffset

<dd>
<p>An integer that indicates an offset, in bytes, into the EDID. This member specifies the beginning of the requested data. </p>
</dd>

### -field DescriptorLength

<dd>
<p>An integer that indicates the length, in bytes, of the buffer pointed to by <b>DescriptorBuffer</b>.</p>
</dd>

### -field DescriptorBuffer

<dd>
<p>A pointer to a buffer that receives all or a portion of the monitor's EDID. This buffer is allocated by the display port driver and filled in by the display miniport driver. The display miniport driver must not write more than <b>DescriptorLength</b> bytes to this buffer.</p>
</dd>
</dl>

## -remarks
<p>The display port driver passes a DXGK_DEVICE_DESCRIPTOR structure to <a href="display.dxgkddiquerydevicedescriptor">DxgkDdiQueryDeviceDescriptor</a> to request that the display miniport driver return all or a portion of a monitor's EDID. The desired portion of the EDID is specified by the <b>DescriptorOffset</b> and <b>DescriptorLength</b> members. For example, to request 256 bytes, starting at an offset of 128 bytes into a monitor's EDID, the display port driver would set <b>DescriptorOffset</b> to 128, and <b>DescriptorLength</b> to 256.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiquerychildrelations">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt--dxgk-generic-descriptor.md">DXGK_GENERIC_DESCRIPTOR</a>
</dt>
<dt>
<a href="display.dxgkddiquerydevicedescriptor">DxgkDdiQueryDeviceDescriptor</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
