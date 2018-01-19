---
UID : NS:ntddndis._NDIS_SWITCH_PORT_ARRAY
title : _NDIS_SWITCH_PORT_ARRAY
author : windows-driver-content
description : The NDIS_SWITCH_PORT_ARRAY structure specifies an array of port configuration parameters. Each element in the array specifies the parameters for a Hyper-V extensible switch port. Each element is formatted as an NDIS_SWITCH_PORT_PARAMETERS structure.
old-location : netvista\ndis_switch_port_array.htm
old-project : netvista
ms.assetid : f753694a-f31b-4bb5-8388-bc20d12cb423
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_SWITCH_PORT_ARRAY, NDIS_SWITCH_PORT_ARRAY, *PNDIS_SWITCH_PORT_ARRAY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h, Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_SWITCH_PORT_ARRAY
req.alt-loc : ntddndis.h
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
req.typenames : NDIS_SWITCH_PORT_ARRAY, *PNDIS_SWITCH_PORT_ARRAY
---

# _NDIS_SWITCH_PORT_ARRAY structure
The <b>NDIS_SWITCH_PORT_ARRAY</b> structure specifies an array of port configuration parameters. Each element in the array specifies the parameters for a Hyper-V extensible switch port. Each element is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> structure.

## Syntax
````
typedef struct _NDIS_SWITCH_PORT_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  USHORT             FirstElementOffset;
  ULONG              NumElements;
  ULONG              ElementSize;
} NDIS_SWITCH_PORT_ARRAY, *PNDIS_SWITCH_PORT_ARRAY;
````

## Members

        
            `ElementSize`

            A ULONG value that specifies the size, in bytes, of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> elements that follows the <b>NDIS_SWITCH_PORT_ARRAY</b> structure.
        
            `FirstElementOffset`

            A USHORT value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>
        
            `Flags`

            A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.
        
            `Header`

            The type, revision, and size of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:
        
            `NumElements`

            A ULONG value that specifies the number of <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> elements that follow the <b>NDIS_SWITCH_PORT_ARRAY</b> structure.

    ## Remarks
        The <b>NDIS_SWITCH_PORT_ARRAY</b> structure is returned in OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a>. An array of <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> structures follow the <b>NDIS_SWITCH_PORT_ARRAY</b> structure in the information buffer that is associated with these OID query requests. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access individual <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> elements inside an <b>NDIS_SWITCH_PORT_ARRAY</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598223">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a> macro.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h, Fwpsk.h) |

    ## See Also

        <dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598223">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598271">OID_SWITCH_PORT_ARRAY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_ARRAY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>