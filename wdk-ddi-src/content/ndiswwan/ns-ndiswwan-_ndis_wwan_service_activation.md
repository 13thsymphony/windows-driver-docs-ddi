---
UID: NS:ndiswwan._NDIS_WWAN_SERVICE_ACTIVATION
title: "_NDIS_WWAN_SERVICE_ACTIVATION"
author: windows-driver-content
description: The NDIS_WWAN_SERVICE_ACTIVATION structure represents the command that is used to set the service activation state of the MB device in order to obtain access to the provider's network.
old-location: netvista\ndis_wwan_service_activation.htm
old-project: netvista
ms.assetid: 0dbfa56f-a755-402d-b403-a04fc183c031
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_WWAN_SERVICE_ACTIVATION, NDIS_WWAN_SERVICE_ACTIVATION, NDIS_WWAN_SERVICE_ACTIVATION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SERVICE_ACTIVATION, PNDIS_WWAN_SERVICE_ACTIVATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_78a89315-d2f0-460f-9c8b-b6bf92d3b267.xml, _NDIS_WWAN_SERVICE_ACTIVATION, ndiswwan/NDIS_WWAN_SERVICE_ACTIVATION, ndiswwan/PNDIS_WWAN_SERVICE_ACTIVATION, netvista.ndis_wwan_service_activation"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SERVICE_ACTIVATION
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SERVICE_ACTIVATION, *PNDIS_WWAN_SERVICE_ACTIVATION
---

# _NDIS_WWAN_SERVICE_ACTIVATION structure
The NDIS_WWAN_SERVICE_ACTIVATION structure represents the command that is used to set the service
  activation state of the MB device in order to obtain access to the provider's network.

## Syntax
````
typedef struct _NDIS_WWAN_SERVICE_ACTIVATION {
  NDIS_OBJECT_HEADER      Header;
  WWAN_SERVICE_ACTIVATION ServiceActivation;
} NDIS_WWAN_SERVICE_ACTIVATION, *PNDIS_WWAN_SERVICE_ACTIVATION;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SERVICE_ACTIVATION
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
NDIS_WWAN_SERVICE_ACTIVATION _REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SERVICE_ACTIVATION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`ServiceActivation`

A 
     <a href="..\wwan\ns-wwan-_wwan_service_activation.md">WWAN_SERVICE_ACTIVATION</a> structure
     that represents the service activation state of the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_service_activation.md">WWAN_SERVICE_ACTIVATION</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SERVICE_ACTIVATION structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>