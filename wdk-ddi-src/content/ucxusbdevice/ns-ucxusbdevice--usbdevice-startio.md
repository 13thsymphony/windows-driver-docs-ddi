---
UID: NS.ucxusbdevice._USBDEVICE_STARTIO
title: USBDEVICE_STARTIO
author: windows-driver-content
description: Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer.
old-location: buses\_usbdevice_startio.htm
old-project: usbref
ms.assetid: 6FE2962A-90A3-44C6-9A2E-CCEBCE8C1417
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USBDEVICE_STARTIO, USBDEVICE_STARTIO, *PUSBDEVICE_STARTIO
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
req.alt-api: USBDEVICE_STARTIO
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
req.iface: 
req.product: Windows 10 or later.
---

# USBDEVICE_STARTIO structure



## -description
<p>Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer. </p>


## -syntax

````
typedef struct _USBDEVICE_STARTIO {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_STARTIO, *P_USBDEVICE_STARTIO;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>A <a href="..\ucxusbdevice\ns-ucxusbdevice--usbdevice-mgmt-header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ucxusbdevice\ns-ucxusbdevice--usbdevice-abortio.md">USBDEVICE_ABORTIO</a>
</dt>
<dt>
<a href="..\ucxusbdevice\ns-ucxusbdevice--usbdevice-purgeio.md">USBDEVICE_PURGEIO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_STARTIO structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
