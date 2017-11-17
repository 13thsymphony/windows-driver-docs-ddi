---
UID: NS.storport._STOR_RICH_DEVICE_DESCRIPTION
title: STOR_RICH_DEVICE_DESCRIPTION
author: windows-driver-content
description: The STOR_RICH_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA (direct memory access) adapter.
old-location: storage\stor_rich_device_description.htm
ms.assetid: 765A420C-F406-4A46-BDCC-26A451549F8D
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_RICH_DEVICE_DESCRIPTION
req.alt-loc: Storport.h
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
ms.keywords: STOR_RICH_DEVICE_DESCRIPTION, STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION
req.iface: 
req.product: Windows 10 or later.
---

# STOR_RICH_DEVICE_DESCRIPTION structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <b>STOR_RICH_DEVICE_DESCRIPTION</b> structure describes the attributes of the <b> physical device </b> for which a driver is requesting a DMA (direct memory access) adapter.</p>


## -syntax

````
typedef struct _STOR_RICH_DEVICE_DESCRIPTION {
  ULONG Version;
  ULONG Size;
  Char  VendorId[STOR_VENDOR_ID_LENGTH +1];
  Char  ModelNumber[STOR_MODEL_NUMBER_LENGTH + 1];
  Char  FirmwareRevision[STOR_FIRMWARE_REVISION_LENGTH + 1];
} STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION;
````


## -struct-fields
<dl>

### -field <b>Version</b>

<dd>
<p>The version of the structure. Must be STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION.</p>
</dd>

### -field <b>Size</b>

<dd>
<p>The size of the structure. </p>
</dd>

### -field <b>VendorId</b>

<dd>
<p>A string representing the device’s vendor ID. May be an empty string if ModelNumber is provided.

</p>
</dd>

### -field <b>ModelNumber</b>

<dd>
<p>A string representing the device’s model.



</p>
</dd>

### -field <b>FirmwareRevision</b>

<dd>
<p>A string representing the device’s currently active firmware revision.
</p>
</dd>
</dl>

## -remarks
<p>Miniport can choose to support this UnitControl if the device reports longer Model or Firmware information than defined in SCSI.</p>

<p>This is invoked during the Unit enumeration process or the device description update process. ScsiUnitRichDescription is a caller-allocated version of this structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1607</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh920398">HwStorUnitControl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20STOR_RICH_DEVICE_DESCRIPTION structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
