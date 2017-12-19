---
UID: NE.iscsiop.PLOGINSESSIONTYPE
title: PLOGINSESSIONTYPE
author: windows-driver-content
description: The LOGINSESSIONTYPE enumeration indicates the type of logon session.
old-location: storage\loginsessiontype.htm
old-project: storage
ms.assetid: 838c2371-c1f3-4415-a624-fab1d8c15d0d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PLOGINSESSIONTYPE, PLOGINSESSIONTYPE, LOGINSESSIONTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LOGINSESSIONTYPE
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

# PLOGINSESSIONTYPE enumeration



## -description
The LOGINSESSIONTYPE enumeration indicates the type of logon session.



## -syntax

````
typedef enum  { 
  ISCSI_LOGINTARGET_DISCOVERY      = 0,
  ISCSI_LOGINTARGET_INFORMATIONAL  = 1,
  ISCSI_LOGINTARGET_DATA           = 2
} LOGINSESSIONTYPE, *PLOGINSESSIONTYPE;
````


## -enum-fields

### -field ISCSI_LOGINTARGET_DISCOVERY

The logon session is for discovery only. Initiators use this type of session to discover targets with the <b>SendTargets</b> command. The initiator must already have access to at least one target IP address and one target port (target portal information).


### -field ISCSI_LOGINTARGET_INFORMATIONAL

The logon session is for informational purposes only. Initiators use this type of session to send SCSI commands that query for information. Management software can use informational sessions to query for information by calling the <b>SendScsiReportLuns</b> and <b>SendScsiReadCapacity</b> user-mode library routines. 

This type of session does not support transmission of user data, and the Plug and Play (PnP) manager does not enumerate target logical units (LUNs) for the storage stack of the initiator node.


### -field ISCSI_LOGINTARGET_DATA

The logon session is full-featured. It reports the target LUNs to the PnP manager on the (local) initiator node for enumeration. After enumerating these LUNs, the operating system can access them for data transfers, just as it would with local LUNs.


## -remarks


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
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20LOGINSESSIONTYPE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

