---
UID: NS.iscsimgt._ISCSI_RedirectPortalInfo
title: ISCSI_RedirectPortalInfo
author: windows-driver-content
description: This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations.
old-location: storage\iscsi_redirectportalinfo.htm
old-project: storage
ms.assetid: 90d9c5e9-4bdf-4c7a-b5ac-54e1f94818bf
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ISCSI_RedirectPortalInfo, ISCSI_RedirectPortalInfo, *PISCSI_RedirectPortalInfo
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
req.alt-api: ISCSI_RedirectPortalInfo
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

# ISCSI_RedirectPortalInfo structure



## -description
<p>This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations. If a target portal is not available for login, the initiator can "hop" through the list of target portals that it discovered and that can be used for login operations. That is, the initiator will continue to try the list of portals that are available until it finds one that can be used for login, so it can then log in to the available target portal.</p>


## -syntax

````
typedef struct _ISCSI_RedirectPortalInfo {
  ULONGLONG        UniqueConnectionId;
  ISCSI_IP_Address OriginalIPAddr;
  ULONG            OriginalPort;
  ISCSI_IP_Address RedirectedIPAddr;
  ULONG            RedirectedPort;
  UCHAR            Redirected;
  UCHAR            TemporaryRedirect;
} ISCSI_RedirectPortalInfo, *PISCSI_RedirectPortalInfo;
````


## -struct-fields
<dl>

### -field <b>UniqueConnectionId</b>

<dd>
<p>The connection identifier (ID) that the operating system and application software use to uniquely identify the connection. The <a href="storage.logintotarget">LoginToTarget</a> and <a href="storage.addconnectiontosession">AddConnectionToSession</a> methods both return this value in the UniqueConnectionId parameter. This value is not to be confused with the connection ID (CID).</p>
</dd>

### -field <b>OriginalIPAddr</b>

<dd>
<p>This is the original IP address given during login from which redirection is to be set, and the IP address is provided via the ISCSI_IP_Address structure.</p>
</dd>

### -field <b>OriginalPort</b>

<dd>
<p>This is the original portals socket number given during login.</p>
</dd>

### -field <b>RedirectedIPAddr</b>

<dd>
<p>This is the IP address to which traffic needs to be redirected. The IP address is provided via the ISCSI_IP_Address structure.</p>
</dd>

### -field <b>RedirectedPort</b>

<dd>
<p>This is the socket number for the redirected target portal.</p>
</dd>

### -field <b>Redirected</b>

<dd>
<p>This indicates whether the login is redirected. If this value is <b>TRUE</b>, RedirectedIPAddr and RedirectedPort are valid.</p>
</dd>

### -field <b>TemporaryRedirect</b>

<dd>
<p>This value is <b>true</b> if redirection is temporary.</p>
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
<dt>Iscsimgt.h (include Iscsimgt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.addconnectiontosession">AddConnectionToSession</a>
</dt>
<dt>
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_RedirectPortalInfo structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
