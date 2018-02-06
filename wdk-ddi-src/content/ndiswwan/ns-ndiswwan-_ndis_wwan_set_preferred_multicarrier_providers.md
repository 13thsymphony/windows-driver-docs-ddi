---
UID: NS:ndiswwan._NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
title: "_NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS"
author: windows-driver-content
description: The NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multicarrier providers associated with the MB device.
old-location: netvista\ndis_wwan_set_preferred_multicarrier_providers.htm
old-project: netvista
ms.assetid: D57068D9-D671-4E56-ABD0-CD91BD91404D
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, netvista.ndis_wwan_set_preferred_multicarrier_providers, PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, ndiswwan/PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure [Network Drivers Starting with Windows Vista]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS"
---

# _NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure
The NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multicarrier providers associated with the MB device.

## Syntax
````
typedef struct _NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS {
  NDIS_OBJECT_HEADER Header;
  WWAN_LIST_HEADER   PreferredListHeader;
} NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     
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
NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`PreferredListHeader`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents a
     list of preferred multicarrier providers to associate with the MB device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>