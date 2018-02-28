---
UID: NS:ndiswwan._NDIS_WWAN_SMS_READ
title: "_NDIS_WWAN_SMS_READ"
author: windows-driver-content
description: The NDIS_WWAN_SMS_READ structure represents an SMS message to read.
old-location: netvista\ndis_wwan_sms_read.htm
old-project: netvista
ms.assetid: 2c15c16f-773b-415d-80a1-fd0b3bcf6fbf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_WWAN_SMS_READ, NDIS_WWAN_SMS_READ, NDIS_WWAN_SMS_READ structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SMS_READ, PNDIS_WWAN_SMS_READ structure pointer [Network Drivers Starting with Windows Vista], WwanRef_7264d34b-78a0-4537-a386-bd77d210d7ae.xml, _NDIS_WWAN_SMS_READ, ndiswwan/NDIS_WWAN_SMS_READ, ndiswwan/PNDIS_WWAN_SMS_READ, netvista.ndis_wwan_sms_read"
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
-	NDIS_WWAN_SMS_READ
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SMS_READ, *PNDIS_WWAN_SMS_READ
---

# _NDIS_WWAN_SMS_READ structure
The NDIS_WWAN_SMS_READ structure represents an SMS message to read.

## Syntax
````
typedef struct _NDIS_WWAN_SMS_READ {
  NDIS_OBJECT_HEADER Header;
  WWAN_SMS_READ      SmsRead;
} NDIS_WWAN_SMS_READ, *PNDIS_WWAN_SMS_READ;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_SMS_READ structure. The
     MB Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
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
NDIS_WWAN_SMS_READ_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SMS_READ)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`SmsRead`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_sms_read.md">WWAN_SMS_READ</a> object that represents the
     format and filter of SMS messages to read.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_sms_read.md">WWAN_SMS_READ</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SMS_READ structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>