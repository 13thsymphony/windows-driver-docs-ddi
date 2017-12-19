---
UID: NS.ISCSIMGT._MSISCSI_INITIATORNODEFAILUREEVENT
title: _MSiSCSI_InitiatorNodeFailureEvent
author: windows-driver-content
description: The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.
old-location: storage\msiscsi_initiatornodefailureevent.htm
old-project: storage
ms.assetid: 0d761b64-d405-4c19-9fd8-e4bf371515a1
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MSiSCSI_InitiatorNodeFailureEvent, MSiSCSI_InitiatorNodeFailureEvent, *PMSiSCSI_InitiatorNodeFailureEvent, PMSiSCSI_InitiatorNodeFailureEvent
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
req.alt-api: MSiSCSI_InitiatorNodeFailureEvent
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
---

# _MSiSCSI_InitiatorNodeFailureEvent structure



## -description
The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs.



## -syntax

````
typedef struct _MSiSCSI_InitiatorNodeFailureEvent {
  ULONGLONG        FailureTime;
  UCHAR            FailureType;
  WCHAR            TargetFailureName[223 + 1];
  ISCSI_IP_Address TargetFailureAddr;
} MSiSCSI_InitiatorNodeFailureEvent, *PMSiSCSI_InitiatorNodeFailureEvent;
````


## -struct-fields

### -field FailureTime

A timestamp that indicates when the node failure occurred.


### -field FailureType

The type of node failure. This member can have the following integer values, which are defined in a ValueMap in <i>Mgmt.mof</i>.

<table>
<tr>
<th>Value</th>
<th>Failure type</th>
</tr>
<tr>
<td>
LoginOtherFail

</td>
<td>
The logon failed for unspecified reasons. 

</td>
</tr>
<tr>
<td>
LoginAuthFail

</td>
<td>
The logon failed, because the initiator and target do not have compatible authentication algorithms. 

</td>
</tr>
<tr>
<td>
LoginAuthenticateFail

</td>
<td>
The logon failed, because the credentials of the initiator and target do not match and the initiator could not authenticate the target. 

</td>
</tr>
<tr>
<td>
LoginNegotiateFail

</td>
<td>
The logon failed, because the initiator could not successfully negotiate a connection with the target. 

</td>
</tr>
<tr>
<td>
LogoutOthers

</td>
<td>
The logout failed due to other reasons.

</td>
</tr>
</table>
 


### -field TargetFailureName

A wide character string that specifies the name of the target that a logon or logoff failed for.


### -field TargetFailureAddr

A <a href="storage.iscsi_ip_address">ISCSI_IP_Address</a> structure that specifies the IP address of the target that a logon or logoff failed for.


## -remarks
It is optional that you implement this class.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="storage.iscsi_ip_address">ISCSI_IP_Address</a>
</dt>
<dt>
<a href="storage.msiscsi_initiatornodefailureevent_wmi_class">MSiSCSI_InitiatorNodeFailureEvent WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_InitiatorNodeFailureEvent structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
