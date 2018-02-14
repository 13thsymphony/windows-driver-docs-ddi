---
UID: NC:ndkpi.NDK_FN_GET_CQ_RESULTS
title: NDK_FN_GET_CQ_RESULTS
author: windows-driver-content
description: The NdkGetCqResults (NDK_FN_GET_CQ_RESULTS) function removes completions from an NDK completion queue (CQ) object.
old-location: netvista\ndk_fn_get_cq_results.htm
old-project: netvista
ms.assetid: CDCDCF99-4A81-43FE-8A3D-0726699905BB
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_get_cq_results, NdkGetCqResults callback function [Network Drivers Starting with Windows Vista], NdkGetCqResults, NDK_FN_GET_CQ_RESULTS, NDK_FN_GET_CQ_RESULTS, ndkpi/NdkGetCqResults
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkGetCqResults
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---


# NDK_FN_GET_CQ_RESULTS callback function
The <i>NdkGetCqResults</i> (<i>NDK_FN_GET_CQ_RESULTS</i>) function removes completions from an NDK completion queue (CQ) object.

## Syntax

```
NDK_FN_GET_CQ_RESULTS NdkFnGetCqResults;

ULONG NdkFnGetCqResults(
  NDK_CQ *pNdkCq,
  NDK_RESULT Results[],
  ULONG nResults
)
{...}
```

## Parameters

`*pNdkCq`

A pointer to an NDK completion queue (CQ) object  (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>).

`Results[]`



`nResults`

The size, in elements, of the <i>Results</i> array. That is, the maximum number of completions to remove from the CQ.


## Return Value

The <i>NDK_FN_GET_CQ_RESULTS</i> function returns the number of completions that were removed from the CQ. 

Zero means there were no completions in the CQ.

## Remarks

<i>NdkGetCqResults</i> removes completions from a completion queue (CQ).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>



<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq_dispatch.md">NDK_CQ_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_CQ_RESULTS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>