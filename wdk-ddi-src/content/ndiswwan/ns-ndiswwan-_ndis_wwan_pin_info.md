---
UID: NS:ndiswwan._NDIS_WWAN_PIN_INFO
title: "_NDIS_WWAN_PIN_INFO"
author: windows-driver-content
description: The NDIS_WWAN_PIN_INFO structure represents the type and PIN-entry state of Personal Identification Number (PIN) information required by the MB device.
old-location: netvista\ndis_wwan_pin_info.htm
old-project: netvista
ms.assetid: 432e1d25-b7f4-4897-99dc-27ea14c851e2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNDIS_WWAN_PIN_INFO, NDIS_WWAN_PIN_INFO, NDIS_WWAN_PIN_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PIN_INFO, PNDIS_WWAN_PIN_INFO structure pointer [Network Drivers Starting with Windows Vista], WwanRef_9095fdd7-5593-439c-897a-1def216d3374.xml, _NDIS_WWAN_PIN_INFO, ndiswwan/NDIS_WWAN_PIN_INFO, ndiswwan/PNDIS_WWAN_PIN_INFO, netvista.ndis_wwan_pin_info"
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
-	NDIS_WWAN_PIN_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_PIN_INFO, *PNDIS_WWAN_PIN_INFO
---

# _NDIS_WWAN_PIN_INFO structure
The NDIS_WWAN_PIN_INFO structure represents the type and PIN-entry state of Personal Identification
  Number (PIN) information required by the MB device.

## Syntax
````
typedef struct _NDIS_WWAN_PIN_INFO {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_PIN_INFO      PinInfo;
} NDIS_WWAN_PIN_INFO, *PNDIS_WWAN_PIN_INFO;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_PIN_INFO structure. The
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
NDIS_WWAN_PIN_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PIN_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`PinInfo`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_pin_info.md">WWAN_PIN_INFO</a> object that represents the type
     and PIN-entry state of Personal Identification Number (PIN) information required by the device.

`uStatus`

The status of the PIN info operation. The following table shows the possible values for this
     member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
Pin info operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
Pin info operation failed because the SIM card is not inserted.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Pin info operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        after the ready-state of the device changes to 
        <b>WwanReadyStateInitialized</b>.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BAD_SIM

</td>
<td>
The operation failed because a bad SIM card was detected.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_DISABLED

</td>
<td>
The operation failed because the PIN is disabled.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The operation failed because a PIN must be entered to proceed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because a 
        <i>set</i> on a corresponding PIN type is not supported by the device.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_pin_info.md">WWAN_PIN_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PIN_INFO structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>