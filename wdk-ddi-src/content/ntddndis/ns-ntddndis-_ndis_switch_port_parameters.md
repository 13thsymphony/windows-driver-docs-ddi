---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PARAMETERS
title: "_NDIS_SWITCH_PORT_PARAMETERS"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PARAMETERS structure contains the configuration data for a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_parameters.htm
old-project: netvista
ms.assetid: E68A9018-1E79-4DA6-8C7A-434A2468169F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PARAMETERS, NDIS_SWITCH_PORT_PARAMETERS, NDIS_SWITCH_PORT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PARAMETERS, PNDIS_SWITCH_PORT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PARAMETERS, netvista.ndis_switch_port_parameters, ntddndis/NDIS_SWITCH_PORT_PARAMETERS, ntddndis/PNDIS_SWITCH_PORT_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PARAMETERS, *PNDIS_SWITCH_PORT_PARAMETERS
---

# _NDIS_SWITCH_PORT_PARAMETERS structure
The <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure contains the configuration data for a Hyper-V extensible switch port.

## Syntax
````
typedef struct _NDIS_SWITCH_PORT_PARAMETERS {
  NDIS_OBJECT_HEADER            Header;
  ULONG                         Flags;
  NDIS_SWITCH_PORT_ID           PortId;
  NDIS_SWITCH_PORT_NAME         PortName;
  NDIS_SWITCH_PORT_FRIENDLYNAME PortFriendlyName;
  NDIS_SWITCH_PORT_TYPE         PortType;
  BOOLEAN                       IsValidationPort;
  NDIS_SWITCH_PORT_PARAMETERS   PortState;
} NDIS_SWITCH_PORT_PARAMETERS, *PNDIS_SWITCH_PORT_PARAMETERS;
````

## Members


`Flags`

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

`Header`

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:  





#### NDIS_SWITCH_PORT_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_PARAMETERS_REVISION_1.

`IsValidationPort`

If TRUE, indicates a port that is temporarily created for test and validation purposes before a VM network adapter connection is established. For more information about this port type, see <a href="https://msdn.microsoft.com/67556275-EF02-4996-A3A2-E9D5D6FCD1AF">Validation Ports</a>.

`PortFriendlyName`

An NDIS_SWITCH_PORT_FRIENDLYNAME value that specifies the user-friendly description of the extensible switch port.

`PortId`

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port.

`PortName`

An NDIS_SWITCH_PORT_NAME value that specifies the unique internal name of the extensible switch port. 

The internal port name is used by WMI-based policy management applications. For more information, see <a href="https://msdn.microsoft.com/F58A4BC0-C5C6-440D-BEA3-2224F7051BA5">Managing Hyper-V Extensible Switch Policies</a>.

`PortState`

An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_state.md">NDIS_SWITCH_PORT_STATE</a> value that specifies the current state of the port.

`PortType`

An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_type.md">NDIS_SWITCH_PORT_TYPE</a> value that specifies the type of the extensible switch port.

## Remarks
The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>  structure contains a pointer to an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure for the following OID requests:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598272">OID_SWITCH_PORT_CREATE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh846217">OID_SWITCH_PORT_UPDATED</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598279">OID_SWITCH_PORT_TEARDOWN</a>


</li>
</ul>
OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a> return an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_array.md">NDIS_SWITCH_PORT_ARRAY</a> structure that contains an array of elements. Each element is formatted as an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure.

Extensible switch extensions can access the  port property buffer inside an <b>NDIS_SWITCH_PORT_PARAMETERS</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598223">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a> macro.

<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_PORT_NAME</b> and  <b>NDIS_SWITCH_PORT_FRIENDLYNAME</b> data types are type-defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character.

</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h, Fwpsk.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598272">OID_SWITCH_PORT_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598223">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598279">OID_SWITCH_PORT_TEARDOWN</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_type.md">NDIS_SWITCH_PORT_TYPE</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_state.md">NDIS_SWITCH_PORT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_array.md">NDIS_SWITCH_PORT_ARRAY</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>