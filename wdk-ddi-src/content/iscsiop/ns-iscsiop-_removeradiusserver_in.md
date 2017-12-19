---
UID: NS.ISCSIOP._REMOVERADIUSSERVER_IN
title: _RemoveRADIUSServer_IN
author: windows-driver-content
description: The RemoveRADIUSServer_IN structure holds the input data for the user-mode RemoveRADIUSServer method, which is used to remove a RADIUS server entry.
old-location: storage\removeradiusserver_in.htm
old-project: storage
ms.assetid: 600916e1-37c2-4766-93d9-b7d32a542542
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _RemoveRADIUSServer_IN, RemoveRADIUSServer_IN, PRemoveRADIUSServer_IN, *PRemoveRADIUSServer_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemoveRADIUSServer_IN
req.alt-loc: iscsiop.h
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

# _RemoveRADIUSServer_IN structure



## -description
The RemoveRADIUSServer_IN structure holds the input data for the user-mode <b>RemoveRADIUSServer</b> method, which is used to remove a RADIUS server entry.



## -syntax

````
typedef struct _RemoveRADIUSServer_IN {
  ISCSI_IP_Address RADIUSIPAddress;
} RemoveRADIUSServer_IN, *PRemoveRADIUSServer_IN;
````


## -struct-fields

### -field RADIUSIPAddress

A <a href="storage.iscsi_ip_address">ISCSI_IP_Address</a> structure that specifies the address of the RADIUS server to remove.


## -remarks
It is optional that you implement this method.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.iscsi_ip_address">ISCSI_IP_Address</a>
</dt>
<dt>
<a href="storage.removepersistentlogin_out">RemovePersistentLogin_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveRADIUSServer_IN structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

