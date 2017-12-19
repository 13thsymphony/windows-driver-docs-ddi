---
UID: NS.NTDDNDIS._NDIS_PROCESSOR_INFO_EX
title: _NDIS_PROCESSOR_INFO_EX
author: windows-driver-content
description: The NDIS_PROCESSOR_INFO_EX structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info_ex.htm
old-project: NetVista
ms.assetid: e4f28f30-32bc-4bbc-8e95-f87dfe80229d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_PROCESSOR_INFO_EX, *PNDIS_PROCESSOR_INFO_EX, PNDIS_PROCESSOR_INFO_EX, NDIS_PROCESSOR_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PROCESSOR_INFO_EX
req.alt-loc: ntddndis.h
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

# _NDIS_PROCESSOR_INFO_EX structure



## -description
The <b>NDIS_PROCESSOR_INFO_EX</b> structure specifies information about a processor in the local
  computer.



## -syntax

````
typedef struct _NDIS_PROCESSOR_INFO_EX {
  PROCESSOR_NUMBER ProcNum;
  ULONG            SocketId;
  ULONG            CoreId;
  ULONG            HyperThreadId;
  USHORT           NodeId;
  USHORT           NodeDistance;
} NDIS_PROCESSOR_INFO_EX, *PNDIS_PROCESSOR_INFO_EX;
````


## -struct-fields

### -field ProcNum

The processor number that is assigned to the processor.


### -field SocketId

The socket identifier for the processor. This is the number that is assigned to the motherboard
     socket on the local computer. That is, it is a physical processor identifier. The possible values for
     this member are zero to the number of sockets on the motherboard minus one.


### -field CoreId

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerSocket</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus one.


### -field HyperThreadId

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingProcsPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus
     one.


### -field NodeId

The node identifier of the processor. This is the number of the NUMA node to which the processor
     belongs. This range of possible values is zero to the number of NUMA nodes on the local computer minus
     one.


### -field NodeDistance

The node distance of the processor. If the handle at the 
     <i>NdisHandle</i> parameter that the caller passed to the 
     <a href="netvista.ndisgetprocessorinformationex">
     NdisGetProcessorInformationEx</a> function is not <b>NULL</b> and is a miniport adapter handle, this member
     contains the distance of the corresponding NIC from this processor's NUMA node. Otherwise, this member
     is zero for miniport drivers or USHORT_MAX (0xffff) for other drivers.


## -remarks
The NDIS_PROCESSOR_INFO_EX structure is used in the 
    <a href="netvista.ndis_system_processor_info_ex">
    NDIS_SYSTEM_PROCESSOR_INFO_EX</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_processor_info">NDIS_PROCESSOR_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_system_processor_info_ex">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>
</dt>
<dt>
<a href="netvista.ndisgetprocessorinformationex">
   NdisGetProcessorInformationEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_PROCESSOR_INFO_EX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

