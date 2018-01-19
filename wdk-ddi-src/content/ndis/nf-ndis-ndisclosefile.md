---
UID : NF:ndis.NdisCloseFile
title : NdisCloseFile function
author : windows-driver-content
description : The NdisCloseFile function releases a handle returned by the NdisOpenFile function and frees the memory allocated to hold the file contents when it was opened.
old-location : netvista\ndisclosefile.htm
old-project : netvista
ms.assetid : a12f7597-cfe7-466f-a5b5-aafd885d5adf
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisCloseFile
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCloseFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisCloseFile (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisCloseFile
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCloseFile function
The 
  <b>NdisCloseFile</b> function releases a handle returned by the 
  <a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a> function and frees the memory
  allocated to hold the file contents when it was opened.

## Syntax

````
VOID NdisCloseFile(
  _In_ NDIS_HANDLE FileHandle
);
````

## Parameters

`FileHandle`

The handle that was returned in a preceding call to the 
     <a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a> function.


## Return Value

None

## Remarks

For miniport drivers, calls to this function are valid only during initialization. If the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
    calls the 
    <a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a> function, it must call 
    <b>NdisCloseFile</b> before it returns control.

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
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismapfile.md">NdisMapFile</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisunmapfile.md">NdisUnmapFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCloseFile function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>