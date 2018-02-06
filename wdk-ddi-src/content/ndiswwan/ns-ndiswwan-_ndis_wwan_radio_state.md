---
UID: NS:ndiswwan._NDIS_WWAN_RADIO_STATE
title: "_NDIS_WWAN_RADIO_STATE"
author: windows-driver-content
description: The NDIS_WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power states of the MB device.
old-location: netvista\ndis_wwan_radio_state.htm
old-project: netvista
ms.assetid: 61173af4-5b6f-47e9-b236-6b45bcd83a9f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_WWAN_RADIO_STATE, ndiswwan/PNDIS_WWAN_RADIO_STATE, PNDIS_WWAN_RADIO_STATE, PNDIS_WWAN_RADIO_STATE structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_WWAN_RADIO_STATE, ndiswwan/NDIS_WWAN_RADIO_STATE, _NDIS_WWAN_RADIO_STATE, NDIS_WWAN_RADIO_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_24973f17-426f-492f-ac5e-1f2651dcebd1.xml, netvista.ndis_wwan_radio_state
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
-	NDIS_WWAN_RADIO_STATE
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_RADIO_STATE, NDIS_WWAN_RADIO_STATE"
---

# _NDIS_WWAN_RADIO_STATE structure
The NDIS_WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power
  states of the MB device.

## Syntax
````
typedef struct _NDIS_WWAN_RADIO_STATE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_RADIO_STATE   RadioState;
} NDIS_WWAN_RADIO_STATE, *PNDIS_WWAN_RADIO_STATE;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_RADIO_STATE structure.
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
NDIS_WWAN_RADIO_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_RADIO_STATE)

</td>
</tr>
</table> 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`RadioState`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_radio_state.md">WWAN_RADIO_STATE</a> object that represents
     the hardware-based and software-based radio power states of the device.

`uStatus`

The status of the radio state operation. The following table shows the possible values for this
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
Radio state operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
Radio state operation failed because the device is busy.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
Radio state operation failed.

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
</table>

## Remarks
The miniport driver must set the 
    <b>uStatus</b> member to WWAN_STATUS_SUCCESS for unsolicited events (NDIS_STATUS_INDICATION::RequestId =
    0).

Miniport drivers can set the 
    <b>uStatus</b> member to WWAN_STATUS_SUCCESS if the current radio state is the same as the requested
    state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\wwan\ns-wwan-_wwan_radio_state.md">WWAN_RADIO_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_RADIO_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>