---
UID: NS.ISCSIFND._ISCSI_DISCOVEREDTARGET
title: _ISCSI_DiscoveredTarget
author: windows-driver-content
description: The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device.
old-location: storage\iscsi_discoveredtarget.htm
old-project: storage
ms.assetid: 0b4a7375-1ee2-4829-92bb-01ed610236de
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget, ISCSI_DiscoveredTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_DiscoveredTarget
req.alt-loc: iscsifnd.h
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

# _ISCSI_DiscoveredTarget structure



## -description
The ISCSI_DiscoveredTarget structure contains information that is related to a discovered target device. 



## -syntax

````
typedef struct _ISCSI_DiscoveredTarget {
  ULONG                             TargetPortalGroupCount;
  WCHAR                             TargetName[223 + 1];
  WCHAR                             TargetAlias[255 + 1];
  ISCSI_DiscoveredTargetPortalGroup TargetDiscoveredPortalGroups[1];
} ISCSI_DiscoveredTarget, *PISCSI_DiscoveredTarget;
````


## -struct-fields

### -field TargetPortalGroupCount

The number of portal groups that are associated with the target.


### -field TargetName

A name for the target that uniquely identifies the target anywhere in the world. For information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group. 


### -field TargetAlias

The human-readable name or description that is assigned to the target device by its host operating system. You can use this name in user interfaces, but it is not unique, you should not use it in authentication decisions. 


### -field TargetDiscoveredPortalGroups

A variable-length array of <a href="storage.iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a> structures that contains information about the portal groups that the initiator can use to connect to the target.


## -remarks
The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTarget structure when it compiles the <a href="storage.iscsi_discoveredtarget_wmi_class">ISCSI_DiscoveredTarget WMI Class</a> in <i>Discover.mof</i>. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsifnd.h (include Iscsifnd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.iscsi_discoveredtarget_wmi_class">ISCSI_DiscoveredTarget WMI Class</a>
</dt>
<dt>
<a href="storage.iscsi_discoveredtarget2">ISCSI_DiscoveredTarget2</a>
</dt>
<dt>
<a href="storage.iscsi_discoveredtargetportalgroup">ISCSI_DiscoveredTargetPortalGroup</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTarget structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

