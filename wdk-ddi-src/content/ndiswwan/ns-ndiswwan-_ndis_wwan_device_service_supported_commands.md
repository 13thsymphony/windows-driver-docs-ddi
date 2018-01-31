---
UID : NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
title : "_NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS"
author : windows-driver-content
description : The NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.
old-location : netvista\ndis_wwan_device_service_supported_commands.htm
old-project : netvista
ms.assetid : 5F619FBF-4152-447E-B228-D4147687E929
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, netvista.ndis_wwan_device_service_supported_commands, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndiswwan.h
req.include-header : Ndiswwan.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
---

# _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure
The NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.

## Syntax
````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS {
  NDIS_OBJECT_HEADER                     Header;
  WWAN_STATUS                            uStatus;
  WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS SupportedCommands;
} NDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PNDIS_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS;
````

## Members


`Header`

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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`SupportedCommands`

A formatted WWAN_LIST_HEADER object that represents the list of command supported on a device services.

This member points to the list of the command ID (ULONG) by using the WWAN_LIST_HEADER structure.

`uStatus`

The status of the device services command enumeration operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndiswwan.h (include Ndiswwan.h) |