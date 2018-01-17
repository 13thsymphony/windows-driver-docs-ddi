---
UID: NF:ndis.NdisGetRssProcessorInformation
title: NdisGetRssProcessorInformation function
author: windows-driver-content
description: The NdisGetRssProcessorInformation function retrieves information about the set of processors that a miniport driver must use for receive side scaling (RSS).
old-location: netvista\ndisgetrssprocessorinformation.htm
old-project: netvista
ms.assetid: 0da022d5-7294-4780-bab8-119ff6385abf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisGetRssProcessorInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetRssProcessorInformation
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisGetRssProcessorInformation function



## -description
The 
  <b>NdisGetRssProcessorInformation</b> function retrieves information about the set of processors that a
  miniport driver must use for receive side scaling (RSS).



## -syntax

````
NDIS_STATUS NdisGetRssProcessorInformation(
  _In_      NDIS_HANDLE              NdisHandle,
  _Out_opt_ PNDIS_RSS_PROCESSOR_INFO RssProcessorInfo,
  _Inout_   PSIZE_T                  Size
);
````


## -parameters

### -param NdisHandle [in]

An NDIS instance handle that was obtained during caller initialization. NDIS drivers can use the
     handles from the following functions:
     

<dl>
<dd>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>


</dd>
<dd>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>


</dd>
</dl>

### -param RssProcessorInfo [out, optional]

A pointer to a caller-allocated buffer where NDIS puts the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567274">NDIS_RSS_PROCESSOR_INFO</a> structure
     and an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567271">NDIS_RSS_PROCESSOR</a> structures that
     contain information about the RSS processor set. The caller provides the length of the buffer in the 
     <i>Size</i> parameter.


### -param Size [in, out]

A pointer to a value that is the size, in bytes, of the buffer that the caller provided. When the
     function returns, this member contains either the amount of data that NDIS put in the buffer or the
     required size of the buffer if the buffer was too short.


## -returns
<b>NdisGetRssProcessorInformation</b> can return one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>The size that was specified in 
       <i>Size</i> parameter was too small. In this case, NDIS provides the required buffer size in the 
       <i>Size</i> parameter.

 


## -remarks
NDIS drivers call the 
    <b>NdisGetRssProcessorInformation</b> function to retrieve information about the receive side scaling
    (RSS) processors on the local computer.

RSS-capable miniport drivers that support MSI-X call 
    <b>NdisGetRssProcessorInformation</b> in their 
    <a href="netvista.miniportfilterresourcerequirements">
    MiniportFilterResourceRequirements</a> function. Miniport drivers set the interrupt affinity of the
    allocated MSI-X messages to the RSS processors that are specified in the 
    <b>RssProcessors</b> member of the 
    <i>RssProcessorInfo</i> parameter.


## -see-also
<dl>
<dt>
<a href="netvista.miniportfilterresourcerequirements">
   MiniportFilterResourceRequirements</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567271">NDIS_RSS_PROCESSOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567274">NDIS_RSS_PROCESSOR_INFO</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetRssProcessorInformation function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

