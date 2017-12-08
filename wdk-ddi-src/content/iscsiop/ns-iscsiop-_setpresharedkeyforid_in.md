---
UID: NS.ISCSIOP._SETPRESHAREDKEYFORID_IN
title: _SetPresharedKeyForId_IN
author: windows-driver-content
description: The SetPresharedKeyForId_IN structure holds the input data for the SetPresharedKeyForId method.
old-location: storage\setpresharedkeyforid_in.htm
old-project: storage
ms.assetid: f941bc28-f906-4399-be54-09e2bc12e443
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SetPresharedKeyForId_IN, SetPresharedKeyForId_IN, *PSetPresharedKeyForId_IN
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
req.alt-api: SetPresharedKeyForId_IN
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

# _SetPresharedKeyForId_IN structure



## -description
The SetPresharedKeyForId_IN structure holds the input data for the <a href="storage.setpresharedkeyforid">SetPresharedKeyForId</a> method.


## -syntax

````
typedef struct _SetPresharedKeyForId_IN {
  ULONG     PortNumber;
  ULONGLONG SecurityFlags;
  UCHAR     IdType;
  ULONG     IdSize;
  ULONG     KeySize;
  UCHAR     Id[1];
} SetPresharedKeyForId_IN, *PSetPresharedKeyForId_IN;
````


## -struct-fields

### -field PortNumber

The number of the port that the initiator uses the preshared key with. A value of 0xffffffff indicates all ports.

### -field SecurityFlags

A bitwise OR of flags that indicate the security requirements of a target.  For a list of possible values for this member, see <a href="storage.security_flag_qualifiers">SECURITY_FLAG_QUALIFIERS</a>.

### -field IdType

The type of identifier to associate with the preshared key. The initiator puts this identifier (ID) in the Internet key exchange (IKE) identification payload to identify itself to the target. The following table describes the possible identification payload types.
<table>
<tr>
<th>Identification payload type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ID_IPV4_ADDR
</td>
<td>
The initiator identifies itself to the target during the key exchange with a single 4-byte version 4 IP address.
</td>
</tr>
<tr>
<td>
ID_FQDN
</td>
<td>
The initiator identifies itself to the target during the key exchange with a fully qualified domain name string (for example, "website.com"). 
</td>
</tr>
<tr>
<td>
ID_USER_FQDN
</td>
<td>
The initiator identifies itself to the target during the key exchange with a fully qualified user name string (for example, "sample@example.com"). 
</td>
</tr>
<tr>
<td>
ID_IPV6_ADDR
</td>
<td>
The initiator identifies itself to the target during the key exchange with a single 16-byte version 6 IP address.
</td>
</tr>
</table>
 

### -field IdSize

The size, in bytes, of the identifier in <b>Id</b><i>.</i>

### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>

### -field Id

The ID to associate with the key. The initiator uses this ID to identify itself to the target during key exchange.

## -remarks
You must implement this method.

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
<a href="storage.security_flag_qualifiers">SECURITY_FLAG_QUALIFIERS</a>
</dt>
<dt>
<a href="storage.setpresharedkeyforid">SetPresharedKeyForId</a>
</dt>
<dt>
<a href="storage.setpresharedkeyforid_out">SetPresharedKeyForId_OUT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetPresharedKeyForId_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
