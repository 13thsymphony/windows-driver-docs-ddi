---
UID : NF:d3dkmthk.D3DKMTDestroyAllocation2
title : D3DKMTDestroyAllocation2 function
author : windows-driver-content
description : The D3DKMTDestroyAllocation2 function releases a resource, a list of allocations, or both.
old-location : display\d3dkmtdestroyallocation2.htm
old-project : display
ms.assetid : C66CD2FB-AD45-4666-ACD4-6555ED681935
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTDestroyAllocation2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMTDestroyAllocation2
req.alt-loc : GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : GDI32.lib
req.dll : GDI32.dll
req.irql : 
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyAllocation2 function
The <b>D3DKMTDestroyAllocation2</b> function releases a resource, a list of allocations, or both.

## Syntax

````
NTSTATUS APIENTRY D3DKMTDestroyAllocation2(
  _In_ const D3DKMT_DESTROYALLOCATION2 *pData
);
````

## Parameters

`D3DKMT_DESTROYALLOCATION2`




## Return Value

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroyallocation.md">D3DKMTDestroyAllocation</a> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Allocations were successfully released.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyallocation2.md">D3DKMT_DESTROYALLOCATION2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyAllocation2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>