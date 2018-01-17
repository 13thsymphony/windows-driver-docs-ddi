---
UID: NS:ndiswwan._NDIS_WWAN_GET_SLOT_INFO
title: _NDIS_WWAN_GET_SLOT_INFO
author: windows-driver-content
description: The NDIS_WWAN_GET_SLOT_INFO structure represents the status of a slot in the modem of the MB device.
old-location: netvista\ndis_wwan_get_slot_info_status.htm
old-project: netvista
ms.assetid: 214AFAD3-B211-4D66-8CFC-58F8EB407B83
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_GET_SLOT_INFO, NDIS_WWAN_GET_SLOT_INFO, *PNDIS_WWAN_GET_SLOT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_GET_SLOT_INFO
req.alt-loc: ndiswwan.h
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
req.typenames: NDIS_WWAN_GET_SLOT_INFO, *PNDIS_WWAN_GET_SLOT_INFO
---

# _NDIS_WWAN_GET_SLOT_INFO structure



## -description
The <b>NDIS_WWAN_GET_SLOT_INFO</b> structure represents the status of a slot in the modem of the MB device.



## -syntax

````
typedef struct _NDIS_WWAN_GET_SLOT_INFO {
  NDIS_OBJECT_HEADER Header;
  WWAN_GET_SLOT_INFO SlotInfoStatus;
} NDIS_WWAN_GET_SLOT_INFO, *PNDIS_WWAN_GET_SLOT_INFO;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_GET_SLOT_INFO</b> structure.
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
NDIS_WWAN_GET_SLOT_INFO_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_GET_SLOT_INFO)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field SlotInfoStatus

A formatted <a href="..\wwan\ns-wwan-_wwan_get_slot_info.md">WWAN_GET_SLOT_INFO</a> structure which contains the slot index to specify which slot's status the query request is for.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_get_slot_info.md">WWAN_GET_SLOT_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_GET_SLOT_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

