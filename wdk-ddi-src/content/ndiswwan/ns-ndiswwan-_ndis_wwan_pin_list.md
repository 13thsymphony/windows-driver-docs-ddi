---
UID: NS:ndiswwan._NDIS_WWAN_PIN_LIST
title: "_NDIS_WWAN_PIN_LIST"
author: windows-driver-content
description: The NDIS_WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs).
old-location: netvista\ndis_wwan_pin_list.htm
old-project: netvista
ms.assetid: 1d3c1084-8f51-4c8a-813e-6700d60c3dab
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_NDIS_WWAN_PIN_LIST, netvista.ndis_wwan_pin_list, NDIS_WWAN_PIN_LIST structure [Network Drivers Starting with Windows Vista], NDIS_WWAN_PIN_LIST, ndiswwan/PNDIS_WWAN_PIN_LIST, ndiswwan/NDIS_WWAN_PIN_LIST, *PNDIS_WWAN_PIN_LIST, WwanRef_783d82e8-71ad-488c-be54-4bd316b949d7.xml, PNDIS_WWAN_PIN_LIST, PNDIS_WWAN_PIN_LIST structure pointer [Network Drivers Starting with Windows Vista]"
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
-	NDIS_WWAN_PIN_LIST
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_PIN_LIST, *PNDIS_WWAN_PIN_LIST
---

# _NDIS_WWAN_PIN_LIST structure
The NDIS_WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers
  (PINs).

## Syntax
````
typedef struct _NDIS_WWAN_PIN_LIST {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_PIN_LIST      PinList;
} NDIS_WWAN_PIN_LIST, *PNDIS_WWAN_PIN_LIST;
````

## Members


`Header`

The header with type, revision, and size information about the NDIS_WWAN_PIN_LIST structure. The
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
NDIS_WWAN_PIN_LIST_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PIN_LIST)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`PinList`

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_pin_list.md">WWAN_PIN_LIST</a> object that represents a list
     of descriptions of Personal Identification Numbers (PINs).

`uStatus`

The status of the PIN list operation. The following table shows the possible values for this.
     

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
The PIN list operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The PIN list operation failed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PIN_REQUIRED

</td>
<td>
The PIN list operation failed because a PIN must be entered before this operation can proceed.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_SIM_NOT_INSERTED

</td>
<td>
The PIN list operation failed because the SIM card is not inserted.

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
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | ndiswwan.h (include Ndiswwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_pin_list.md">WWAN_PIN_LIST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_PIN_LIST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>