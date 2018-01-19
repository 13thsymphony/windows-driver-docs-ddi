---
UID : NF:ntddk.KeQueryNodeActiveAffinity
title : KeQueryNodeActiveAffinity function
author : windows-driver-content
description : The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.
old-location : kernel\kequerynodeactiveaffinity.htm
old-project : kernel
ms.assetid : 49d4c9c7-217f-41b7-b870-886dd78e04a9
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : KeQueryNodeActiveAffinity
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KeQueryNodeActiveAffinity
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeQueryNodeActiveAffinity function
The <b>KeQueryNodeActiveAffinity</b> routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture.

## Syntax

````
VOID KeQueryNodeActiveAffinity(
  _In_      USHORT          NodeNumber,
  _Out_opt_ PGROUP_AFFINITY Affinity,
  _Out_opt_ PUSHORT         Count
);
````

## Parameters

`NodeNumber`

The node number. If a multiprocessor system contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1. To obtain the highest node number (<i>n</i>-1) in the system, call the <a href="..\ntddk\nf-ntddk-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine.

`Affinity`

A pointer to a caller-allocated buffer into which the routine writes a <a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a> structure. This structure contains the group number of the group that contains the node that is identified by <i>NodeNumber</i>, and an affinity mask that indicates which logical processors in the node are active. You can set this parameter to <b>NULL</b> if you do not need this information.

`Count`

A pointer to a location into which the routine writes the number of active processors that are represented in the node affinity mask that is pointed to by <i>Affinity</i>. You can set this parameter to <b>NULL</b> if you do not need this information.


## Return Value

None

## Remarks

The caller-allocated buffer that is pointed to by the <i>Affinity</i> parameter must be large enough to contain a <b>GROUP_AFFINITY</b> structure. The <b>Mask</b> member of this structure contains an affinity mask that indicates which processors are active. If a processor is active, the corresponding bit in the mask is one. All other bits are zero.

In a NUMA multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

The number of processors in a node cannot exceed the number of bits in the affinity mask in the structure that is pointed to by <i>Affinity</i>. The affinity mask also determines the maximum number of processors in a group.

If, during system initialization, Windows encounters a NUMA hardware node that contains more logical processors than will fit into a group, Windows splits the node into smaller, logical nodes. Each of these nodes does not exceed the maximum group size. The <i>NodeNumber</i> parameter identifies a logical node. To obtain the maximum number of processors per group, call the <a href="..\ntddk\nf-ntddk-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryNodeActiveAffinity routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>