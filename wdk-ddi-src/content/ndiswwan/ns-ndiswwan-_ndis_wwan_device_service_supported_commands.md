---
UID: NS.NDISWWAN._NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
title: _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.
old-location: netvista\ndis_wwan_device_service_supported_commands.htm
old-project: netvista
ms.assetid: 5F619FBF-4152-447E-B228-D4147687E929
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
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

# _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure



## -description
The NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.



## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS {
  NDIS_OBJECT_HEADER                     Header;
  WWAN_STATUS                            uStatus;
  WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS SupportedCommands;
} NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
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
NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device services command enumeration operation.


### -field SupportedCommands

 A formatted WWAN_LIST_HEADER object that represents the list of command supported on a device services.

This member points to the list of the command ID (ULONG) by using the WWAN_LIST_HEADER structure.


## -remarks


## -requirements
<table>
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