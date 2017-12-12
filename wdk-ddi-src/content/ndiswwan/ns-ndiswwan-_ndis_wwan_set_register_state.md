---
UID: NS.NDISWWAN._NDIS_WWAN_SET_REGISTER_STATE
title: _NDIS_WWAN_SET_REGISTER_STATE
author: windows-driver-content
description: The NDIS_WWAN_SET_REGISTER_STATE structure represents the network provider registration state of the MB device.
old-location: netvista\ndis_wwan_set_register_state.htm
old-project: netvista
ms.assetid: c8d9c2aa-2eb7-43da-ae13-f7209e68e2fd
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_WWAN_SET_REGISTER_STATE, *PNDIS_WWAN_SET_REGISTER_STATE, NDIS_WWAN_SET_REGISTER_STATE
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
req.alt-api: NDIS_WWAN_SET_REGISTER_STATE
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
---

# _NDIS_WWAN_SET_REGISTER_STATE structure



## -description
The NDIS_WWAN_SET_REGISTER_STATE structure represents the network provider registration state of the
  MB device.



## -syntax

````
typedef struct _NDIS_WWAN_SET_REGISTER_STATE {
  NDIS_OBJECT_HEADER      Header;
  WWAN_SET_REGISTER_STATE SetRegisterState;
} NDIS_WWAN_SET_REGISTER_STATE, *PNDIS_WWAN_SET_REGISTER_STATE;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_REGISTER_STATE
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
NDIS_WWAN_SET_REGISTER_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_REGISTER_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field SetRegisterState

A formatted 
     <a href="netvista.wwan_set_register_state">WWAN_SET_REGISTER_STATE</a> object that
     represents the new network selection mode for the device.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.wwan_set_register_state">WWAN_SET_REGISTER_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SET_REGISTER_STATE structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

