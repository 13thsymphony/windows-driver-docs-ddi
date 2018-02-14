---
UID: NF:ndis.NdisUnmapFile
title: NdisUnmapFile function
author: windows-driver-content
description: The NdisUnmapFile function releases a virtual address mapping of a file previously set up with the NdisMapFile function.
old-location: netvista\ndisunmapfile.htm
old-project: netvista
ms.assetid: 20ba1eef-2377-4e17-a2ff-002f1bbe15f0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisUnmapFile, netvista.ndisunmapfile, NdisUnmapFile function [Network Drivers Starting with Windows Vista], ndis_file_ref_5be88800-5866-4969-8534-2d76953bf4de.xml, NdisUnmapFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisUnmapFile
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisUnmapFile function
The
  <b>NdisUnmapFile</b> function releases a virtual address mapping of a file previously set up with the 
  <a href="..\ndis\nf-ndis-ndismapfile.md">NdisMapFile</a> function.

## Syntax

````
VOID NdisUnmapFile(
  _In_ NDIS_HANDLE FileHandle
);
````

## Parameters

`FileHandle`

The handle that was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a> function.


## Return Value

None

## Remarks

To reduce resource usage, a miniport driver should always call 
    <b>NdisUnmapFile</b> when it no longer needs exclusive access to the contents of a file that it opened.
    Such a driver can map and unmap the file as necessary, using alternating calls to 
    <b>NdisMapFile</b> and 
    <b>NdisUnmapFile</b> until it releases the file handle with the 
    <a href="..\ndis\nf-ndis-ndisclosefile.md">NdisCloseFile</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisUnmapFile (NDIS 5.1)) in Windows   XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisclosefile.md">NdisCloseFile</a>



<a href="..\ndis\nf-ndis-ndismapfile.md">NdisMapFile</a>



<a href="..\ndis\nf-ndis-ndisopenfile.md">NdisOpenFile</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUnmapFile function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>