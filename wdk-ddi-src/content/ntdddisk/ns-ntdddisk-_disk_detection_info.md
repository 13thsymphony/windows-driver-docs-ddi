---
UID: NS.NTDDDISK._DISK_DETECTION_INFO
title: _DISK_DETECTION_INFO
author: windows-driver-content
description: The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.
old-location: storage\disk_detection_info.htm
old-project: storage
ms.assetid: 67a508cf-79c4-4c86-9ad3-fa7cca99cf5f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DISK_DETECTION_INFO, PDISK_DETECTION_INFO, *PDISK_DETECTION_INFO, DISK_DETECTION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DISK_DETECTION_INFO
req.alt-loc: ntdddisk.h
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

# _DISK_DETECTION_INFO structure



## -description
The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.



## -syntax

````
typedef struct _DISK_DETECTION_INFO {
  ULONG          SizeOfDetectInfo;
  DETECTION_TYPE DetectionType;
  union {
    struct {
      DISK_INT13_INFO    Int13;
      DISK_EX_INT13_INFO ExInt13;
    };
  };
} DISK_DETECTION_INFO, *PDISK_DETECTION_INFO;
````


## -struct-fields

### -field SizeOfDetectInfo

Contains the quantity, in bytes, of retrieved detect information.


### -field DetectionType

Indicates one of three possible detection types:

<ol>
<li>
<b>DetectNone</b>

</li>
<li>
<b>DetectInt13</b>

</li>
<li>
<b>DetectExInt13</b>

</li>
</ol>
See the structure <a href="storage.detection_type">DETECTION_TYPE</a> for further information.


### -field ( unnamed struct )

Contains the quantity, in bytes, of retrieved detect information.


### -field Int13

Contains <a href="storage.disk_int13_info">DISK_INT13_INFO</a> structure with the disk parameters for INT 13 type partitions. This member is used if <b>DetectionType </b>== <b>DetectInt13</b>.


### -field ExInt13

Contains a <a href="storage.disk_ex_int13_info">DISK_EX_INT13_INFO</a> structure with the disk parameters for extended INT 13 type partitions. This member is used if <b>DetectionType</b> == <b>DetectExInt13</b>.

</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h, Ntddk.h, or Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.disk_geometry_ex">DISK_GEOMETRY_EX</a>
</dt>
<dt>
<a href="storage.disk_int13_info">DISK_INT13_INFO</a>
</dt>
<dt>
<a href="storage.disk_ex_int13_info">DISK_EX_INT13_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_DETECTION_INFO structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

