---
UID: NS.NTDDSTOR._STORAGE_HW_FIRMWARE_DOWNLOAD
title: _STORAGE_HW_FIRMWARE_DOWNLOAD
author: windows-driver-content
description: This structure contains a firmware image payload to be downloaded to the target.
old-location: storage\storage_hw_firmware_download.htm
old-project: storage
ms.assetid: EFF4688D-E5B2-4F4C-837D-D536F9244AB6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_HW_FIRMWARE_DOWNLOAD, STORAGE_HW_FIRMWARE_DOWNLOAD, *PSTORAGE_HW_FIRMWARE_DOWNLOAD, PSTORAGE_HW_FIRMWARE_DOWNLOAD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_HW_FIRMWARE_DOWNLOAD
req.alt-loc: ntddstor.h
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
---

# _STORAGE_HW_FIRMWARE_DOWNLOAD structure



## -description
This structure contains a firmware image payload to be downloaded to the target.



## -syntax

````
typedef struct _STORAGE_HW_FIRMWARE_DOWNLOAD {
  ULONG     Version;
  ULONG     Size;
  ULONG     Flags;
  UCHAR     Slot;
  UCHAR     Reserved[3];
  ULONGLONG Offset;
  ULONGLONG BufferSize;
  UCHAR     ImageBuffer[ANYSIZE_ARRAY];
} STORAGE_HW_FIRMWARE_DOWNLOAD, *PSTORAGE_HW_FIRMWARE_DOWNLOAD;
````


## -struct-fields

### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_DOWNLOAD).


### -field Size

The size of this structure and the download image buffer.


### -field Flags

Flags associated with this download. The following are valid flags that this member can hold.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>STORAGE_HW_FIRMWARE_REQUEST_FLAG_CONTROLLER</td>
<td>Indicates that the target of the request is a controller or adapter, different than the device handle or object itself (e.g. NVMe SSD or HBA).</td>
</tr>
<tr>
<td>STORAGE_HW_FIRMWARE_REQUEST_FLAG_LAST_SEGMENT </td>
<td>Indicates that the current firmware image segment is the last one. </td>
</tr>
</table>
 


### -field Slot

The slot number that the firmware image will be downloaded to.


### -field Reserved

Reserved for future use.


### -field Offset

The offset in this buffer of where the Image file begins. This should be aligned to ImagePayloadAlignment from <a href="storage.storage_hw_firmware_info">STORAGE_HW_FIRMWARE_INFO</a>.


### -field BufferSize

The buffer size of the ImageBuffer. This should be a multiple of ImagePayloadAlignment from <a href="storage.storage_hw_firmware_info">STORAGE_HW_FIRMWARE_INFO</a>.


### -field ImageBuffer

The firmware image file.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>