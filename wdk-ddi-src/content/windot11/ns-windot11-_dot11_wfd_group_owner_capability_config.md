---
UID: NS:windot11._DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
title: "_DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG"
author: windows-driver-content
description: the DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure is included with a OID_DOT11_WFD_GROUP_OWNER_CAPABILITY request. The structure contains capability settings for a Peer-to-Peer Group Owner (P2P GO).
old-location: netvista\_dot11_wfd_group_owner_capability_config.htm
old-project: netvista
ms.assetid: 6114799B-D0AC-421A-9F02-EED9A4391C03
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure pointer [Network Drivers Starting with Windows Vista], windot11/DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, windot11/PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, netvista._dot11_wfd_group_owner_capability_config, _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure [Network Drivers Starting with Windows Vista], *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Windot11.h
apiname:
-	DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG"
req.product: Windows 10 or later.
---

# _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>the <b>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG</b> structure is included with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451799">OID_DOT11_WFD_GROUP_OWNER_CAPABILITY</a> request. The structure contains capability settings for a Peer-to-Peer Group Owner (P2P GO).

## Syntax
````
typedef struct _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG {
  NDIS_OBJECT_HEADER Header;
  BOOLEAN            bPersistentGroupEnabled;
  BOOLEAN            bIntraBSSDistributionSupported;
  BOOLEAN            bCrossConnectionSupported;
  BOOLEAN            bPersistentReconnectSupported;
  BOOLEAN            bGroupFormationEnabled;
  ULONG              uMaximumGroupLimit;
}  DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG;
````

## Members


`bCrossConnectionSupported`

If TRUE, the miniport must set the Cross Connection bit of the Group Capability bitmask. Otherwise, the Cross Connection bit must be cleared. The default value of this member is FALSE.

`bGroupFormationEnabled`

If TRUE, the miniport must set the Group Formation bit of the Group Capability bitmask. Otherwise, the Group Formation bit must be cleared. The default value of this member is FALSE.

`bIntraBSSDistributionSupported`

If TRUE, the miniport must set the Intra-BSS Distribution bit of the Group Capability bitmask. Otherwise, the Intra-BSS Distribution bit must be cleared. The default value of this member is FALSE.

`bPersistentGroupEnabled`

If TRUE, the miniport must set the Persistent P2P Group bit of the Group Capability bitmask. Otherwise, the Persistent P2P Group bit must be cleared. The default value of this member is FALSE.

`bPersistentReconnectSupported`

If TRUE, the miniport must set the Persistent Reconnect bit of the Group Capability bitmask. Otherwise, the Persistent Reconnect bit must be cleared. The default value of this member is FALSE.

`Header`

Specifies the type, revision and size of the <b>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_OWNER_CAPABILITY_CONFIG_1</td>
</tr>
</table>

`uMaximumGroupLimit`

Maximum number of P2P Clients the GO should allow. Once this limit is reached, the miniport should reject the addition of any new Clients and should set the Group Limit bit in the Group Capability bitmask. The default value for this member is same as the value reported in the  <b>uGORoleClientTableSize</b> member of <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 Versions:\_Supported in Windows 8 |
| **Header** | windot11.h (include Windot11.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451799">OID_DOT11_WFD_GROUP_OWNER_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20 DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>