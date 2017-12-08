---
UID: NS.UCXENDPOINT._DEFAULT_ENDPOINT_UPDATE
title: _DEFAULT_ENDPOINT_UPDATE
author: windows-driver-content
description: Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.
old-location: buses\_default_endpoint_update.htm
old-project: usbref
ms.assetid: 3E85D9AE-F8D3-4763-B1A2-51F95D00422D
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DEFAULT_ENDPOINT_UPDATE, *PDEFAULT_ENDPOINT_UPDATE, DEFAULT_ENDPOINT_UPDATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEFAULT_ENDPOINT_UPDATE
req.alt-loc: ucxendpoint.h
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

# _DEFAULT_ENDPOINT_UPDATE structure



## -description
Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_default_endpoint_update.md">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a> callback function.


## -syntax

````
typedef struct _DEFAULT_ENDPOINT_UPDATE {
#if __cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
  UCXENDPOINT           DefaultEndpoint;
  ULONG                 MaxPacketSize;
} DEFAULT_ENDPOINT_UPDATE, *P_DEFAULT_ENDPOINT_UPDATE;
````


## -struct-fields

### -field Header

A <a href="buses._usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains header information related to the USB device or hub endpoint.

### -field DefaultEndpoint

A handle to the  default endpoint to update.

### -field MaxPacketSize

The maximum packet size of the default endpoint.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxendpoint.h (include Ucxclass.h or Ucxendpoint.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_default_endpoint_update.md">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20DEFAULT_ENDPOINT_UPDATE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
