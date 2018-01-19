---
UID : NF:d3dkmthk.D3DKMTGetSharedResourceAdapterLuid
title : D3DKMTGetSharedResourceAdapterLuid function
author : windows-driver-content
description : Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.
old-location : display\d3dkmtgetsharedresourceadapterluid.htm
old-project : display
ms.assetid : 880bf5bd-eadc-480f-a10c-f6d57f670857
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTGetSharedResourceAdapterLuid
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMTGetSharedResourceAdapterLuid
req.alt-loc : GDI32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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


# D3DKMTGetSharedResourceAdapterLuid function
Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTGetSharedResourceAdapterLuid(
  _Inout_ D3DKMT_GETSHAREDRESOURCEADAPTERLUID *pLuid
);
````

## Parameters

This function has no parameters.

## Return Value

Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The mapping was performed successfully.
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
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid.md">D3DKMT_GETSHAREDRESOURCEADAPTERLUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetSharedResourceAdapterLuid function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>