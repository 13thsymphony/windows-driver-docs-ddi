---
UID : NF:ndis.NdisGetCurrentProcessorCpuUsage
title : NdisGetCurrentProcessorCpuUsage function
author : windows-driver-content
description : The NdisGetCurrentProcessorCpuUsage function returns the average amount of activity on the current processor since boot as a percentage.Note  This function is deprecated.
old-location : netvista\ndisgetcurrentprocessorcpuusage.htm
old-project : netvista
ms.assetid : 03f1559c-83a7-478c-a616-ebe6002cb724
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis_sysinfo_ref_64c35a8c-5776-4902-b062-0685a16f5453.xml, ndis/NdisGetCurrentProcessorCpuUsage, NdisGetCurrentProcessorCpuUsage function [Network Drivers Starting with Windows Vista], netvista.ndisgetcurrentprocessorcpuusage, NdisGetCurrentProcessorCpuUsage
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Deprecated for NDIS 6.0 and later drivers in Windows Vista and later. Deprecated for NDIS 5.1 drivers (see       NdisGetCurrentProcessorCpuUsage (NDIS 5.1)) in Windows XP and later.
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
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetCurrentProcessorCpuUsage function
The 
  <b>NdisGetCurrentProcessorCpuUsage</b> function returns the  average amount of activity on the current processor since boot as a
  percentage.
<div class="alert"><b>Note</b>  This function is deprecated. Do not use it in your driver.</div><div> </div>

## Syntax

````
VOID NdisGetCurrentProcessorCpuUsage(
  _Out_ PULONG pCpuUsage
);
````

## Parameters

`pCpuUsage`

A pointer to a caller-supplied variable that receives the average usage of the current processor since boot, expressed as a percentage.


## Return Value

None

## Remarks

The <b>NdisGetCurrentProcessorCpuUsage</b> function returns the average amount of activity on the current processor since the last boot, not the current usage level. This information is not particularly useful. Therefore, we recommend that you don't use <b>NdisGetCurrentProcessorCpuUsage</b> in your driver.

As an alternative, you can use <a href="..\ndis\nf-ndis-ndisgetcurrentprocessorcounts.md">NdisGetCurrentProcessorCounts</a> to see whether the processor is currently loaded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndisgetcurrentprocessorcounts.md">NdisGetCurrentProcessorCounts</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetCurrentProcessorCpuUsage function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>