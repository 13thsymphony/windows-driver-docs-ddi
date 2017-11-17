---
UID: NS.wsk._WSK_DATAGRAM_INDICATION
title: WSK_DATAGRAM_INDICATION
author: windows-driver-content
description: The WSK_DATAGRAM_INDICATION structure describes a datagram that has been received on a datagram socket.
old-location: netvista\wsk_datagram_indication.htm
ms.assetid: 061db3ca-80ed-419e-8cca-f49d1498b780
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_DATAGRAM_INDICATION
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: WSK_DATAGRAM_INDICATION, WSK_DATAGRAM_INDICATION, *PWSK_DATAGRAM_INDICATION
req.iface: 
req.product: Windows 10 or later.
---

# WSK_DATAGRAM_INDICATION structure



## -description
<p>The WSK_DATAGRAM_INDICATION structure describes a datagram that has been received on a datagram
  socket.</p>


## -syntax

````
typedef struct _WSK_DATAGRAM_INDICATION {
  struct _WSK_DATAGRAM_INDICATION  *Next;
  WSK_BUF                         Buffer;
  PCMSGHDR                        ControlInfo;
  ULONG                           ControlInfoLength;
  PSOCKADDR                       RemoteAddress;
} WSK_DATAGRAM_INDICATION, *PWSK_DATAGRAM_INDICATION;
````


## -struct-fields
<dl>

### -field <b>Next</b>

<dd>
<p>A pointer to the next WSK_DATAGRAM_INDICATION structure in a linked list of
     WSK_DATAGRAM_INDICATION structures. If this member is <b>NULL</b>, this structure is the last
     WSK_DATAGRAM_INDICATION structure in the linked list.</p>
</dd>

### -field <b>Buffer</b>

<dd>
<p>A WSK_BUF structure that describes a datagram that has been received on the socket.</p>
</dd>

### -field <b>ControlInfo</b>

<dd>
<p>The control information that is associated with the received datagram. The control information
     data that is associated with a datagram is made up of one or more control data objects, each of which
     begins with a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a> structure. If there is no control
     information present for the received datagram, this member is <b>NULL</b>.</p>
</dd>

### -field <b>ControlInfoLength</b>

<dd>
<p>The size of the control information that is associated with the received datagram. If this value
     is zero, there is no control information present for the datagram.</p>
</dd>

### -field <b>RemoteAddress</b>

<dd>
<p>A pointer to a buffer that contains the remote transport address from which the received datagram
     originated. The buffer contains the specific SOCKADDR structure type that corresponds to the address
     family that the WSK application specified when it created the datagram socket.</p>
</dd>
</dl>

## -remarks
<p>The WSK subsystem passes a pointer to a WSK_DATAGRAM_INDICATION structure as the 
    <i>DataIndication</i> parameter when it calls a datagram socket's 
    <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
    function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_DATAGRAM_INDICATION structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
