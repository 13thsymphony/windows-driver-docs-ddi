---
UID: NS.iscsifnd._ISCSI_DiscoveredTargetPortalGroup
title: ISCSI_DiscoveredTargetPortalGroup
author: windows-driver-content
description: The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.
old-location: storage\iscsi_discoveredtargetportalgroup.htm
old-project: storage
ms.assetid: 5c90dbc2-f42a-4c04-8c77-0ef3a712416c
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ISCSI_DiscoveredTargetPortalGroup, ISCSI_DiscoveredTargetPortalGroup, *PISCSI_DiscoveredTargetPortalGroup
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
req.alt-api: ISCSI_DiscoveredTargetPortalGroup
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
req.iface: 
---

# ISCSI_DiscoveredTargetPortalGroup structure



## -description
<p>The ISCSI_DiscoveredTargetPortalGroup structure contains information about a discovered target portal group.</p>


## -syntax

````
typedef struct _ISCSI_DiscoveredTargetPortalGroup {
  ULONG                        PortalCount;
  ISCSI_DiscoveredTargetPortal Portals[1];
} ISCSI_DiscoveredTargetPortalGroup, *PISCSI_DiscoveredTargetPortalGroup;
````


## -struct-fields
<dl>

### -field <b>PortalCount</b>

<dd>
<p>The number of portals in the group. </p>
</dd>

### -field <b>Portals</b>

<dd>
<p>An array of <a href="..\iscsifnd\ns-iscsifnd--iscsi-discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a> structures, which describe target portals. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortalGroup structure when it compiles the <a href="storage.iscsi_discoveredtargetportalgroup_wmi_class">ISCSI_DiscoveredTargetPortalGroup WMI Class</a> in <i>Discover.mof</i>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\iscsifnd\ns-iscsifnd--iscsi-discoveredtargetportal.md">ISCSI_DiscoveredTargetPortal</a>
</dt>
<dt>
<a href="..\iscsifnd\ns-iscsifnd--iscsi-discoveredtargetportalgroup2.md">ISCSI_DiscoveredTargetPortalGroup2</a>
</dt>
<dt>
<a href="storage.iscsi_discoveredtargetportalgroup_wmi_class">ISCSI_DiscoveredTargetPortalGroup WMI Class</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTargetPortalGroup structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
