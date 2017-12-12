---
UID: NS.NTDDCDVD._DVD_MANUFACTURER_DESCRIPTOR
title: _DVD_MANUFACTURER_DESCRIPTOR
author: windows-driver-content
description: The DVD_MANUFACTURER_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD manufacturer descriptor.
old-location: storage\dvd_manufacturer_descriptor.htm
old-project: storage
ms.assetid: 19a65a8f-5272-424a-85b3-88074fb9e22f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DVD_MANUFACTURER_DESCRIPTOR, *PDVD_MANUFACTURER_DESCRIPTOR, DVD_MANUFACTURER_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DVD_MANUFACTURER_DESCRIPTOR
req.alt-loc: ntddcdvd.h
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

# _DVD_MANUFACTURER_DESCRIPTOR structure



## -description
The DVD_MANUFACTURER_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD manufacturer descriptor. 



## -syntax

````
typedef struct _DVD_MANUFACTURER_DESCRIPTOR {
  UCHAR ManufacturingInformation[2048];
} DVD_MANUFACTURER_DESCRIPTOR, *PDVD_MANUFACTURER_DESCRIPTOR;
````


## -struct-fields

### -field ManufacturingInformation

Contains an array holding the manufacturing information taken from the DVD media lead-in area. In the case of DVD-R multisession disc, this information is taken from the last border-in area.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_MANUFACTURER_DESCRIPTOR structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

