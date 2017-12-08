---
UID: NS.UCXUSBDEVICE._USBDEVICE_PURGEIO
title: _USBDEVICE_PURGEIO
author: windows-driver-content
description: The USBDEVICE_PURGEIO structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.
old-location: buses\_usbdevice_purgeio.htm
old-project: usbref
ms.assetid: 5E45A5A0-59EE-4A72-9CCA-DD1C9A406EB5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBDEVICE_PURGEIO, *PUSBDEVICE_PURGEIO, USBDEVICE_PURGEIO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBDEVICE_PURGEIO
req.alt-loc: ucxusbdevice.h
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
req.product: Windows 10 or later.
---

# _USBDEVICE_PURGEIO structure



## -description
The <b>USBDEVICE_PURGEIO</b> structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.


## -syntax

````
typedef struct _USBDEVICE_PURGEIO {
#if 
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_PURGEIO, *P_USBDEVICE_PURGEIO;
````


## -struct-fields

### -field Header

A <a href="buses._usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses._usbdevice_tree_purgeio">USBDEVICE_TREE_PURGEIO</a>
</dt>
<dt>
<a href="buses._usbdevice_abortio">USBDEVICE_ABORTIO</a>
</dt>
<dt>
<a href="buses._usbdevice_startio">USBDEVICE_STARTIO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_PURGEIO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
