---
UID: NS:ndiswwan._NDIS_WWAN_SET_PROVISIONED_CONTEXT
title: "_NDIS_WWAN_SET_PROVISIONED_CONTEXT"
author: windows-driver-content
description: The NDIS_WWAN_SET_PROVISIONED_CONTEXT structure represents the command to set the provisioned context state of the MB device.
old-location: netvista\ndis_wwan_set_provisioned_context.htm
old-project: netvista
ms.assetid: c0f77100-ffd0-4fef-80b0-fc399ef96aee
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanRef_0f679f5b-26a4-4069-b4d7-65835090f56f.xml, ndiswwan/PNDIS_WWAN_SET_PROVISIONED_CONTEXT, NDIS_WWAN_SET_PROVISIONED_CONTEXT, PNDIS_WWAN_SET_PROVISIONED_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_PROVISIONED_CONTEXT, netvista.ndis_wwan_set_provisioned_context, *PNDIS_WWAN_SET_PROVISIONED_CONTEXT, ndiswwan/NDIS_WWAN_SET_PROVISIONED_CONTEXT, NDIS_WWAN_SET_PROVISIONED_CONTEXT structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PROVISIONED_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	NDIS_WWAN_SET_PROVISIONED_CONTEXT
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PROVISIONED_CONTEXT, *PNDIS_WWAN_SET_PROVISIONED_CONTEXT
---

# _NDIS_WWAN_SET_PROVISIONED_CONTEXT structure
The NDIS_WWAN_SET_PROVISIONED_CONTEXT structure represents the command to set the provisioned context
  state of the MB device.

## Syntax
````
typedef struct _NDIS_WWAN_SET_PROVISIONED_CONTEXT {
  NDIS_OBJECT_HEADER Header;
  WWAN_SET_CONTEXT   ProvisionedContext;
} NDIS_WWAN_SET_PROVISIONED_CONTEXT, *PNDIS_WWAN_SET_PROVISIONED_CONTEXT;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SET_PROVISIONED_CONTEXT
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
NDIS_WWAN_SET_PROVISIONED_CONTEXT_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PROVISIONED_CONTEXT)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`ProvisionedContext`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_set_context.md">WWAN_SET_CONTEXT</a> object that represents a
     provisioned context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\wwan\ns-wwan-_wwan_context.md">WWAN_CONTEXT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_PROVISIONED_CONTEXT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>