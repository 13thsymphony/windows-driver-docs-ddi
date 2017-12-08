---
UID: NS.NTDDCDRM._CDROM_STREAMING_CONTROL
title: _CDROM_STREAMING_CONTROL
author: windows-driver-content
description: The CDROM_STREAMING_CONTROL structure is used as an input parameter to the IOCTL_CDROM_ENABLE_STREAMING IOCTL.
old-location: storage\cdrom_streaming_control.htm
old-project: storage
ms.assetid: 71D4008C-1F04-408B-93DF-DDE6FD352701
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _CDROM_STREAMING_CONTROL, CDROM_STREAMING_CONTROL, *PCDROM_STREAMING_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_STREAMING_CONTROL
req.alt-loc: Ntddcdrm.h
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

# _CDROM_STREAMING_CONTROL structure



## -description
The <b>CDROM_STREAMING_CONTROL</b> structure is used as an input parameter to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a> IOCTL.


## -syntax

````
typedef struct _CDROM_STREAMING_CONTROL {
  STREAMING_CONTROL_REQUEST_TYPE    RequestType;
} CDROM_STREAMING_CONTROL, *PCDROM_STREAMING_CONTROL;
````


## -struct-fields

### -field RequestType

The <a href="storage.streaming_control_request_type">STREAMING_CONTROL_REQUEST_TYPE</a>   enumeration specifies the type of request.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.streaming_control_request_type">STREAMING_CONTROL_REQUEST_TYPE</a>
</dt>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_STREAMING_CONTROL structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
