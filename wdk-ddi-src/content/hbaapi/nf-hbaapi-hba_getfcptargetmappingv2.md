---
UID : NF:hbaapi.HBA_GetFcpTargetMappingV2
title : HBA_GetFcpTargetMappingV2 function
author : windows-driver-content
description : The HBA_GetFcpTargetMappingV2 routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate on the indicated port.
old-location : storage\hba_getfcptargetmappingv2.htm
old-project : storage
ms.assetid : 970475d7-dd81-4189-bd2b-2a22c4f732dc
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.hba_getfcptargetmappingv2, HBA_GetFcpTargetMappingV2 routine [Storage Devices], hbaapi/HBA_GetFcpTargetMappingV2, fibreHBA_rtns_c0f700bf-da1f-4480-8fa0-8441f924e351.xml, HBA_GetFcpTargetMappingV2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Desktop
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
req.lib : Hbaapi.lib
req.dll : Hbaapi.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HBA_WWNTYPE
---


# HBA_GetFcpTargetMappingV2 function
The <b>HBA_GetFcpTargetMappingV2</b> routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate on the indicated port.

## Syntax

````
HBA_STATUS HBA_API HBA_GetFcpTargetMappingV2(
  _In_    HBA_HANDLE             HbaHandle,
  _In_    HBA_WWN                HbaPortWWN,
  _Inout_ HBA_FCPTARGETMAPPINGV2 *Mapping
);
````

## Parameters

`HbaHandle`

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the target mappings. The HBA returns mappings for the targets that it can enumerate on the port specified by <i>HbaPortWWN</i>.

`HbaPortWWN`

Contains a 64-bit worldwide name (WWN) that uniquely identifies the fibre channel port on which the targets are enumerated. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

`Mapping`

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcptargetmappingv2.md">HBA_FCPTargetMappingV2</a> that contains an array of bindings between operating system and FCP identifiers for a set of target devices. These mappings are maintained by the HBA referenced by <i>HbaHandle</i>. On input, the <b>NumberOfEntries</b> member of HBA_FCPTargetMappingV2 should contain a number of mappings that fit in the output buffer. On output, the <b>NumberOfEntries</b> contains the number of mappings requested, or the full set of mappings, whichever is smaller. The value in <b>NumberOfEntries</b> contains the number of mappings returned even when an error occurred due to insufficient buffer space.


## Return Value

The <b>HBA_GetFcpTargetMappingV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFcpTargetMappingV2</b> returns one of the following qualifiers.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if all mapping were successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_MORE_DATA</b></dt>
</dl>
</td>
<td width="60%">
Returned if the buffer space is insufficient to hold all of the mapping information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>HbaHandle</i> does not contain a port with a name of <i>HbaPortWWN. </i>

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>HbaHandle</i> does not support target mapping.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the mapping information. 

</td>
</tr>
</table>

## Remarks

The difference between the <b>HBA_GetFcpTargetMappingV2</b> routine and the <a href="..\hbaapi\nf-hbaapi-hba_getfcptargetmapping.md">HBA_GetFcpTargetMapping</a> routine is that the mappings returned by <b>HBA_GetFcpTargetMappingV2</b> include a logical unit ID descriptor (LUID) for each logical unit. If the vital product data for a logical unit provides more than one LUID, then the LUID that <b>HBA_GetFcpTargetMappingV2</b> returns depends on the types of LUIDs provided. For a complete explanation of how the LUID is chosen when more than one LUID is available, see the T11 committee's <i>Fibre Channel HBA API </i>specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_fcptargetmappingv2.md">HBA_FCPTargetMappingV2</a>

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

<a href="..\hbaapi\nf-hbaapi-hba_getfcptargetmapping.md">HBA_GetFcpTargetMapping</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFcpTargetMappingV2 routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>