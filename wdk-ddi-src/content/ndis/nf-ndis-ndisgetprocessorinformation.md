---
UID : NF:ndis.NdisGetProcessorInformation
title : NdisGetProcessorInformation function
author : windows-driver-content
description : The NdisGetProcessorInformation function retrieves information about the CPU topology of the local computer and the set of processors that a miniport driver must use for receive side scaling (RSS).
old-location : netvista\ndisgetprocessorinformation.htm
old-project : netvista
ms.assetid : 2cee5cf4-7dee-49d2-905c-2b9634137ce4
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndisgetprocessorinformation, ndis/NdisGetProcessorInformation, ndis_sysinfo_ref_1479e4eb-4467-48da-bab6-1f60993f5ef2.xml, NdisGetProcessorInformation, NdisGetProcessorInformation function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, ise       NdisGetProcessorInformationEx or       NdisGetRssProcessorInformation instead.
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
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetProcessorInformation function
The 
  <b>NdisGetProcessorInformation</b> function retrieves information about the CPU topology of the local
  computer and the set of processors that a miniport driver must use for receive side scaling (RSS).

## Syntax

````
NDIS_STATUS NdisGetProcessorInformation(
  _Inout_ PNDIS_SYSTEM_PROCESSOR_INFO SystemProcessorInfo
);
````

## Parameters

`SystemProcessorInfo`

A pointer to an 
     <mshelp:link keywords="netvista.ndis_system_processor_info" tabindex="0"><b>
     NDIS_SYSTEM_PROCESSOR_INFO</b></mshelp:link> structure that NDIS fills with the information about the CPU topology
     of the system and the RSS processor set.


## Return Value

<b>NdisGetProcessorInformation</b> can return one of the following status values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The size that was specified in the 
       <b>Header.Size</b> member of the 
       <i>SystemProcessorInfo</i> parameter was too small.

</td>
</tr>
</table>

## Remarks

NDIS drivers call the 
    <b>NdisGetProcessorInformation</b> function to retrieve information about the processors on the local
    computer.

RSS-capable miniport drivers that support MSI-X call 
    <b>NdisGetProcessorInformation</b> in their 
    <mshelp:link keywords="netvista.miniportfilterresourcerequirements" tabindex="0"><i>
    MiniportFilterResourceRequirements</i></mshelp:link> function. Miniport drivers set the interrupt affinity of the
    allocated MSI-X messages to the RSS processors that are specified in the 
    <b>RssProcessors</b> member of the 
    <i>SystemProcessorInfo</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.ndisgetprocessorinformationex" tabindex="0"><b>
   NdisGetProcessorInformationEx</b></mshelp:link>

<mshelp:link keywords="netvista.miniportfilterresourcerequirements" tabindex="0"><i>
   MiniportFilterResourceRequirements</i></mshelp:link>

<mshelp:link keywords="netvista.ndisgetrssprocessorinformation" tabindex="0"><b>
   NdisGetRssProcessorInformation</b></mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetProcessorInformation function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>