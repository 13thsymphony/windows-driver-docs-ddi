---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_CAPS
title: _NDIS_WWAN_DEVICE_CAPS
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_CAPS structure represents the capabilities of the MB device.
old-location: netvista\ndis_wwan_device_caps.htm
old-project: netvista
ms.assetid: 8a0e1e46-8bb1-4292-bd33-17ed4cc33c60
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDIS_WWAN_DEVICE_CAPS, *PNDIS_WWAN_DEVICE_CAPS, NDIS_WWAN_DEVICE_CAPS
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
req.alt-api: NDIS_WWAN_DEVICE_CAPS
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
req.typenames: *PNDIS_WWAN_DEVICE_CAPS, NDIS_WWAN_DEVICE_CAPS
---

# _NDIS_WWAN_DEVICE_CAPS structure



## -description
The NDIS_WWAN_DEVICE_CAPS structure represents the capabilities of the MB device.



## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_CAPS {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_DEVICE_CAPS   DeviceCaps;
} NDIS_WWAN_DEVICE_CAPS, *PNDIS_WWAN_DEVICE_CAPS;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_CAPS structure.
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
Windows 8 miniport drivers that follow the NDIS 6.30 specification should set this to NDIS_WWAN_DEVICE_CAPS_REVISION_2. Windows 7 miniport drivers that follow the NDIS 6.20 specification should set this to NDIS_WWAN_DEVICE_CAPS_REVISION_1.

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_CAPS)

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  You must specify NDIS_WWAN_DEVICE_CAPS_REVISION_2 in <b>Revision</b> to use the Windows 8 members of <a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>.</div>
<div> </div>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device capabilities query. The following table shows the possible values for
     this member.
     

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
The operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_FAILURE

</td>
<td>
The operation failed to retrieve the capabilities for the device.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
The operation failed because the device is in the process of initializing. Retry the operation
        when the ready-state is not 
        <b>WwanReadyStateOff</b>.

</td>
</tr>
</table>
 


### -field DeviceCaps

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a> object that represents
     the capabilities of the MB device.


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
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_CAPS structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

