---
UID: NS.NDISWWAN._NDIS_WWAN_DEVICE_CAPS_EX
title: _NDIS_WWAN_DEVICE_CAPS_EX
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_CAPS_EX structure represents the capabilities of the MB device.
old-location: netvista\ndis_wwan_device_caps_ex.htm
old-project: NetVista
ms.assetid: FC801FA3-699F-4EE5-BED9-35CA696A5E52
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_DEVICE_CAPS_EX, *PNDIS_WWAN_DEVICE_CAPS_EX, PNDIS_WWAN_DEVICE_CAPS_EX, NDIS_WWAN_DEVICE_CAPS_EX
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
req.alt-api: NDIS_WWAN_DEVICE_CAPS_EX
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

# _NDIS_WWAN_DEVICE_CAPS_EX structure



## -description
The <b>NDIS_WWAN_DEVICE_CAPS_EX</b> structure represents the capabilities of the MB device. <b>NDIS_WWAN_DEVICE_CAPS_EX</b> extends the capability of the existing <b>NDIS_WWAN_DEVICE_CAPS</b> structure by changing its <b>WWAN_DEVICE_CAPS</b> structure to a <b>WWAN_DEVICE_CAPS_EX</b> structure.



## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_CAPS_EX {
  NDIS_OBJECT_HEADER  Header;
  WWAN_STATUS         uStatus;
  WWAN_DEVICE_CAPS_EX DeviceCapsEx;
} NDIS_WWAN_DEVICE_CAPS_EX, *PNDIS_WWAN_DEVICE_CAPS_EX;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_DEVICE_CAPS_EX</b> structure.
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
NDIS_WWAN_DEVICE_CAPS_EX_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_CAPS_EX)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of system capability. The following table shows the possible values for
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
WWAN_STATUS_BUSY

</td>
<td>
The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation.

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
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The operation failed because the device does not support this OID.

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
 


### -field DeviceCapsEx

A formatted 
     <a href="netvista.wwan_device_caps_ex">WWAN_DEVICE_CAPS_EX</a> structure that has an <b>ExecutorIndex</b> member and Microsoft service extension member added to the existing <a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 10, version 1703

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
<a href="netvista.wwan_device_caps_ex">WWAN_DEVICE_CAPS_EX</a>
</dt>
<dt>
<a href="netvista.oid_wwan_device_caps_ex">OID_WWAN_DEVICE_CAPS_EX</a>
</dt>
<dt>
<a href="netvista.ndis_wwan_device_caps">NDIS_WWAN_DEVICE_CAPS</a>
</dt>
<dt>
<a href="netvista.wwan_device_caps">WWAN_DEVICE_CAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_WWAN_DEVICE_CAPS_EX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

