---
UID : NS:ndiswwan._NDIS_WWAN_SET_SMS_CONFIGURATION
title : "_NDIS_WWAN_SET_SMS_CONFIGURATION"
author : windows-driver-content
description : The NDIS_WWAN_SET_SMS_CONFIGURATION structure represents the SMS configuration of the MB device.
old-location : netvista\ndis_wwan_set_sms_configuration.htm
old-project : netvista
ms.assetid : aa191c47-4b3b-464a-8a12-db673fca0f20
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndiswwan/PNDIS_WWAN_SET_SMS_CONFIGURATION, PNDIS_WWAN_SET_SMS_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WwanRef_f118e481-c8ed-4b8b-a6f9-ba1e26fc564f.xml, ndiswwan/NDIS_WWAN_SET_SMS_CONFIGURATION, *PNDIS_WWAN_SET_SMS_CONFIGURATION, NDIS_WWAN_SET_SMS_CONFIGURATION structure [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_SMS_CONFIGURATION, netvista.ndis_wwan_set_sms_configuration, PNDIS_WWAN_SET_SMS_CONFIGURATION, NDIS_WWAN_SET_SMS_CONFIGURATION
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
req.typenames : NDIS_WWAN_SET_SMS_CONFIGURATION, *PNDIS_WWAN_SET_SMS_CONFIGURATION
---

# _NDIS_WWAN_SET_SMS_CONFIGURATION structure
The NDIS_WWAN_SET_SMS_CONFIGURATION structure represents the SMS configuration of the MB
  device.

## Syntax
````
typedef struct _NDIS_WWAN_SET_SMS_CONFIGURATION {
  NDIS_OBJECT_HEADER         Header;
  WWAN_SET_SMS_CONFIGURATION SetSmsConfiguration;
} NDIS_WWAN_SET_SMS_CONFIGURATION, *PNDIS_WWAN_SET_SMS_CONFIGURATION;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SET_SMS_CONFIGURATION
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
NDIS_WWAN_SET_SMS_CONFIGURATION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_SMS_CONFIGURATION)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`SetSmsConfiguration`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_set_sms_configuration.md">
     WWAN_SET_SMS_CONFIGURATION</a> object that represents the SMS configuration to set on the
     device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\wwan\ns-wwan-_wwan_set_sms_configuration.md">WWAN_SET_SMS_CONFIGURATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_SMS_CONFIGURATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>