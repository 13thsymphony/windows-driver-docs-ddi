---
UID: NS:ndiswwan._NDIS_WWAN_SET_PRESHUTDOWN_STATE
title: "_NDIS_WWAN_SET_PRESHUTDOWN_STATE"
author: windows-driver-content
description: The NDIS_WWAN_SET_PRESHUTDOWN_STATE structure represents the command to notify the modem to finish all operations and prepare to shut down.
old-location: netvista\ndis_wwan_set_preshutdown_state.htm
old-project: netvista
ms.assetid: B1DC847C-B596-452D-B96E-3B78C6F995B2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_wwan_set_preshutdown_state, NDIS_WWAN_SET_PRESHUTDOWN_STATE, PNDIS_WWAN_SET_PRESHUTDOWN_STATE, *PNDIS_WWAN_SET_PRESHUTDOWN_STATE, ndiswwan/PNDIS_WWAN_SET_PRESHUTDOWN_STATE, NDIS_WWAN_SET_PRESHUTDOWN_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PRESHUTDOWN_STATE structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_SET_PRESHUTDOWN_STATE, _NDIS_WWAN_SET_PRESHUTDOWN_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 10, version 1511.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndiswwan.h
apiname:
-	NDIS_WWAN_SET_PRESHUTDOWN_STATE
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_SET_PRESHUTDOWN_STATE, NDIS_WWAN_SET_PRESHUTDOWN_STATE"
---

# _NDIS_WWAN_SET_PRESHUTDOWN_STATE structure
The NDIS_WWAN_SET_PRESHUTDOWN_STATE structure represents the command to notify the modem to finish all operations and prepare to shut down.

## Syntax
````
typedef struct _NDIS_WWAN_SET_PRESHUTDOWN_STATE {
  NDIS_OBJECT_HEADER Header;
} NDIS_WWAN_SET_PRESHUTDOWN_STATE, *PNDIS_WWAN_SET_PRESHUTDOWN_STATE;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SET_PRESHUTDOWN_STATE
     structure. 

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
 NDIS_WWAN_SET_PRESHUTDOWN_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PRESHUTDOWN_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with  Windows 10, version 1511. Available starting with  Windows 10, version 1511. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt593239">OID_WWAN_PRESHUTDOWN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_PRESHUTDOWN_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>