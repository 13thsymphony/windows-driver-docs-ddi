---
UID: NS.iscsimgt._PingIPAddress_IN
title: PingIPAddress_IN
author: windows-driver-content
description: The PingIPAddress_IN structure holds the input data for the PingIPAddress method.
old-location: storage\pingipaddress_in.htm
old-project: storage
ms.assetid: 2dec9594-727e-44e6-8be8-2416ea77e447
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PingIPAddress_IN, PingIPAddress_IN, *PPingIPAddress_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PingIPAddress_IN
req.alt-loc: iscsimgt.h
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
---

# PingIPAddress_IN structure



## -description
<p>The PingIPAddress_IN structure holds the input data for the PingIPAddress method.</p>


## -syntax

````
typedef struct _PingIPAddress_IN {
  ULONG            RequestCount;
  ULONG            RequestSize;
  ULONG            Timeout;
  ISCSI_IP_Address Address;
} PingIPAddress_IN, *PPingIPAddress_IN;
````


## -struct-fields
<dl>

### -field <b>RequestCount</b>

<dd>
<p>The number of ping requests to be sent to the specified IP address.</p>
</dd>

### -field <b>RequestSize</b>

<dd>
<p>The size of each request (in bytes) to be sent.</p>
</dd>

### -field <b>Timeout</b>

<dd>
<p>The timeout (in milliseconds) for each ping request.</p>
</dd>

### -field <b>Address</b>

<dd>
<p>The IP address to which the ping request must be sent. The IP address is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure.</p>
</dd>
</dl>

## -remarks
<p>We recommend that you implement this class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsimgt.h (include Iscsimgt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PingIPAddress_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
