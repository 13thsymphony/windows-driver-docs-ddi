---
UID : NC:ndkpi.NDK_FN_RELEASE_LAM
title : NDK_FN_RELEASE_LAM
author : windows-driver-content
description : The NdkReleaseLam (NDK_FN_RELEASE_LAM) function releases an NDK adapter logical address mapping (LAM).
old-location : netvista\ndk_fn_release_lam.htm
old-project : netvista
ms.assetid : 8CEBDCCE-5B71-443D-9DE5-F789E16843D7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndk_fn_release_lam, NdkReleaseLam callback function [Network Drivers Starting with Windows Vista], NdkReleaseLam, NDK_FN_RELEASE_LAM, NDK_FN_RELEASE_LAM, ndkpi/NdkReleaseLam
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndkpi.h
req.include-header : Ndkpi.h
req.target-type : Windows
req.target-min-winverclnt : None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr : Windows Server 2012
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
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---


# NDK_FN_RELEASE_LAM callback function
The <i>NdkReleaseLam</i> (<i>NDK_FN_RELEASE_LAM</i>) function releases an NDK adapter logical address mapping (LAM).

## Syntax

```
NDK_FN_RELEASE_LAM NdkFnReleaseLam;

void NdkFnReleaseLam(
  NDK_ADAPTER *pNdkAdapter,
  NDK_LOGICAL_ADDRESS_MAPPING *pNdkLAM
)
{...}
```

## Parameters

`*pNdkAdapter`



`*pNdkLAM`




## Return Value

None

## Remarks

<i>NdkReleaseLam</i> releases an adapter logical address mapping (LAM). The associated MDL  remains unchanged. That is, the MDL is in the same state it hand when it was  passed to the <i>NdkBuildLam</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>) function. The NDK consumer must not release a LAM until after all of the work requests that use the LAM are completed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_logical_address_mapping.md">NDK_LOGICAL_ADDRESS_MAPPING</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_RELEASE_LAM callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>