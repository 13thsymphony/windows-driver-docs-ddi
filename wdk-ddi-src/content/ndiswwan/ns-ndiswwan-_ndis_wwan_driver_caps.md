---
UID : NS:ndiswwan._NDIS_WWAN_DRIVER_CAPS
title : "_NDIS_WWAN_DRIVER_CAPS"
author : windows-driver-content
description : The NDIS_WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.
old-location : netvista\ndis_wwan_driver_caps.htm
old-project : netvista
ms.assetid : 413ea129-2c55-4e7f-ad7c-ce99840f7066
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PNDIS_WWAN_DRIVER_CAPS structure pointer [Network Drivers Starting with Windows Vista], ndiswwan/NDIS_WWAN_DRIVER_CAPS, PNDIS_WWAN_DRIVER_CAPS, NDIS_WWAN_DRIVER_CAPS, WwanRef_9c8d6cfb-7f4b-47ac-879b-4c3ada7f9239.xml, NDIS_WWAN_DRIVER_CAPS structure [Network Drivers Starting with Windows Vista], netvista.ndis_wwan_driver_caps, *PNDIS_WWAN_DRIVER_CAPS, ndiswwan/PNDIS_WWAN_DRIVER_CAPS, _NDIS_WWAN_DRIVER_CAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndiswwan.h
req.include-header : Ndiswwan.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_WWAN_DRIVER_CAPS, *PNDIS_WWAN_DRIVER_CAPS
---

# _NDIS_WWAN_DRIVER_CAPS structure
The NDIS_WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.

## Syntax
````
typedef struct _NDIS_WWAN_DRIVER_CAPS {
  NDIS_OBJECT_HEADER Header;
  WWAN_DRIVER_CAPS   DriverCaps;
} NDIS_WWAN_DRIVER_CAPS, *PNDIS_WWAN_DRIVER_CAPS;
````

## Members


`DriverCaps`

A 
     <a href="..\wwan\ns-wwan-_wwan_driver_caps.md">WWAN_DRIVER_CAPS</a> structure that represents
     the capabilities of the miniport driver.

`Header`

The header with type, revision, and size information about the NDIS_WWAN_DRIVER_CAPS structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
  NDIS_WWAN_DRIVER_CAPS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DRIVER_CAPS)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_driver_caps.md">WWAN_DRIVER_CAPS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DRIVER_CAPS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>