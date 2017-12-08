---
UID: NS.NTDDSTOR._STORAGE_BUS_RESET_REQUEST
title: _STORAGE_BUS_RESET_REQUEST
author: windows-driver-content
description: The STORAGE_BUS_RESET_REQUEST structure is used in conjunction with the IOCTL_STORAGE_RESET_BUS request to specify the path of the bus to be reset.
old-location: storage\storage_bus_reset_request.htm
old-project: storage
ms.assetid: d2f2d2cc-e96b-475c-96eb-d58244a05788
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STORAGE_BUS_RESET_REQUEST, STORAGE_BUS_RESET_REQUEST, *PSTORAGE_BUS_RESET_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_BUS_RESET_REQUEST
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

# _STORAGE_BUS_RESET_REQUEST structure



## -description
The STORAGE_BUS_RESET_REQUEST structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_reset_bus.md">IOCTL_STORAGE_RESET_BUS</a> request to specify the path of the bus to be reset.


## -syntax

````
typedef struct _STORAGE_BUS_RESET_REQUEST {
  UCHAR PathId;
} STORAGE_BUS_RESET_REQUEST, *PSTORAGE_BUS_RESET_REQUEST;
````


## -struct-fields

### -field PathId

Indicates the number of the bus to be reset. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_reset_bus.md">IOCTL_STORAGE_RESET_BUS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_BUS_RESET_REQUEST structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
