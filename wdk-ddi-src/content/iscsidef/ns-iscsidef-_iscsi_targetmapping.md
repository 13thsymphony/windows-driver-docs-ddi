---
UID: NS.ISCSIDEF._ISCSI_TARGETMAPPING
title: _ISCSI_TargetMapping
author: windows-driver-content
description: The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers.
old-location: storage\iscsi_targetmapping.htm
old-project: storage
ms.assetid: 9b8c5024-5d37-4f85-be00-1a60dd9ab323
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _ISCSI_TargetMapping, ISCSI_TargetMapping, *PISCSI_TargetMapping, PISCSI_TargetMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_TargetMapping
req.alt-loc: iscsidef.h
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

# _ISCSI_TargetMapping structure



## -description
The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers. 



## -syntax

````
typedef struct _ISCSI_TargetMapping {
  ULONG         OSBus;
  ULONG         OSTarget;
  ULONGLONG     UniqueSessionId;
  ULONG         LUNCount;
  WCHAR         TargetName[223 + 1];
  BOOLEAN       FromPersistentLogin;
  ULONGLONG     Reserved;
  ISCSI_LUNList LUNList[1];
} ISCSI_TargetMapping, *PISCSI_TargetMapping;
````


## -struct-fields

### -field OSBus

The SCSI bus number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can associate any SCSI bus number with the target. 


### -field OSTarget

The SCSI target number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can pick any number to identify the remote target device.


### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="storage.logintotarget">LoginToTarget</a> and <a href="storage.addconnectiontosession">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field LUNCount

The number of LUNs that are associated with the remote target device.


### -field TargetName

A wide character string that indicates the target name. 


### -field FromPersistentLogin

A Boolean value that indicates whether the logon session is persistent. If this member is <b>TRUE</b>, the logon session is persistent and the system creates it automatically when the computer boots up. If this member is <b>FALSE</b>, the logon session is not persistent.


### -field Reserved

Reserved for Microsoft use only.


### -field LUNList

A <a href="storage.iscsi_lunlist">ISCSI_LUNList</a> structure that holds a list of LUNs that are associated with the target device.


## -remarks
A 64-bit iSCSI LUN by itself does not uniquely identify the logical unit that it represents. However, the combination of an iSCSI LUN and the name of the target that the logical unit belongs to does provide a unique identification for that logical unit that is valid anywhere in the network. 

Management applications can use the ISCSI_TargetMapping structure to specify a local LUN number that can be assigned to the target LUN that the operating system finds during device enumerations.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsidef.h (include Iscsidef.h)</dt>
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
<a href="storage.iscsi_lunlist">ISCSI_LUNList</a>
</dt>
<dt>
<a href="storage.iscsi_targetmapping_wmi_class">ISCSI_TargetMapping WMI Class</a>
</dt>
<dt>
<a href="storage.logintotarget">LoginToTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_TargetMapping structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

