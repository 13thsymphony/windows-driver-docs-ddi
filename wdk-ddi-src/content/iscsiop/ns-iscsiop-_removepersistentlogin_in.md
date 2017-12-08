---
UID: NS.ISCSIOP._REMOVEPERSISTENTLOGIN_IN
title: _RemovePersistentLogin_IN
author: windows-driver-content
description: The RemovePersistentLogin_IN structure holds the input data for the RemovePersistentLogin method, which is used to remove persistent login information.
old-location: storage\removepersistentlogin_in.htm
old-project: storage
ms.assetid: 94dc7a87-83a0-419d-914c-008d797fec87
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _RemovePersistentLogin_IN, *PRemovePersistentLogin_IN, RemovePersistentLogin_IN
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
req.alt-api: RemovePersistentLogin_IN
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

# _RemovePersistentLogin_IN structure



## -description
The RemovePersistentLogin_IN structure holds the input data for the <a href="storage.removepersistentlogin">RemovePersistentLogin</a> method, which is used to remove persistent login information.


## -syntax

````
typedef struct _RemovePersistentLogin_IN {
  ULONG              PortNumber;
  WCHAR              TargetName[223 + 1];
  ISCSI_TargetPortal TargetPortal;
} RemovePersistentLogin_IN, *PRemovePersistentLogin_IN;
````


## -struct-fields

### -field PortNumber

The port number from which the initiator established the logon session.

### -field TargetName

The iSCSI target name to be removed from the initiator's list of persistent logon targets.

### -field TargetPortal

A <a href="storage.iscsi_targetportal">ISCSI_TargetPortal</a> structure that specifies the target portal for which the initiator should delete persistent logons. ISCSI_TargetPortal has an <b>Address</b> member of type <a href="storage.iscsi_ip_address">ISCSI_IP_Address</a>. If the <b>Type</b> member of ISCSI_IP_Address is set to ISCSI_IP_ADDRESS_EMPTY, the <a href="storage.removepersistentlogin">RemovePersistentLogin</a> method removes the persistent logons to the target for all portals.

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
<a href="storage.iscsi_ip_address">ISCSI_IP_Address</a>
</dt>
<dt>
<a href="storage.iscsi_targetportal">ISCSI_TargetPortal</a>
</dt>
<dt>
<a href="storage.removepersistentlogin">RemovePersistentLogin</a>
</dt>
<dt>
<a href="storage.removepersistentlogin_out">RemovePersistentLogin_OUT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentLogin_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
