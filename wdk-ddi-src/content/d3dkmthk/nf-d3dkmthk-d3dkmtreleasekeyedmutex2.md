---
UID : NF:d3dkmthk.D3DKMTReleaseKeyedMutex2
title : D3DKMTReleaseKeyedMutex2 function
author : windows-driver-content
description : Releases a keyed mutex object that includes private data.
old-location : display\d3dkmtreleasekeyedmutex2.htm
old-project : display
ms.assetid : e5df165c-3d85-42b9-affe-3dcc7c46aa0b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTReleaseKeyedMutex2
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
req.alt-api : D3DKMTReleaseKeyedMutex2
req.alt-loc : Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Gdi32.lib
req.dll : Gdi32.dll
req.irql : 
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTReleaseKeyedMutex2 function
Releases a keyed mutex object that includes private data.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTReleaseKeyedMutex2(
  _Inout_ D3DKMT_RELEASEKEYEDMUTEX2 *pData
);
````

## Parameters

This function has no parameters.

## Return Value

Returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The keyed mutex object was successfully released. 
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex2.md">D3DKMTReleaseKeyedMutex2</a> could not complete because of insufficient memory.

 

This function might also return other NTSTATUS values.

## Remarks

<b>D3DKMTReleaseKeyedMutex2</b> behaves like 
  the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex.md">D3DKMTReleaseKeyedMutex</a> function but lets 
  the caller specify private data to associate with the keyed mutex.

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
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_releasekeyedmutex2.md">D3DKMT_RELEASEKEYEDMUTEX2</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex.md">D3DKMTReleaseKeyedMutex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTReleaseKeyedMutex2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>