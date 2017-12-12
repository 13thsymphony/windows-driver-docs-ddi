---
UID: NF.ndis.NdisMapFile
title: NdisMapFile function
author: windows-driver-content
description: The NdisMapFile function maps an already open file into a caller-accessible buffer if the file is currently unmapped.
old-location: netvista\ndismapfile.htm
old-project: netvista
ms.assetid: 965bb4c7-826d-425b-b10d-2d5a29ca0f91
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisMapFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMapFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMapFile (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMapFile
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMapFile function



## -description
The 
  <b>NdisMapFile</b> function maps an already open file into a caller-accessible buffer if the file is
  currently unmapped.



## -syntax

````
VOID NdisMapFile(
  _Out_ PNDIS_STATUS Status,
  _Out_ PVOID *      MappedBuffer,
  _In_  NDIS_HANDLE  FileHandle
);
````


## -parameters

### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the mapping
     operation, which can be one of the following:
     




### -param NDIS_STATUS_SUCCESS

The caller has exclusive access to the file contents until the 
       <a href="netvista.ndisunmapfile">NdisUnmapFile</a> function is called.


### -param NDIS_STATUS_ALREADY_MAPPED

The caller cannot access the file contents at this time.

</dd>
</dl>

### -param MappedBuffer [out]

A pointer to a caller-supplied variable in which this function returns the base virtual address of
     the mapped file contents or <b>NULL</b>.


### -param FileHandle [in]

The handle that was returned by a preceding call to the 
     <a href="netvista.ndisopenfile">NdisOpenFile</a> function.


## -returns
None


## -remarks
<b>NdisMapFile</b> associates (maps) a virtual address range with an opened file so the driver can access
    the file contents. 
    <b>NdisMapFile</b> allows only one mapping of a particular file to be outstanding at any time.
    Consequently, a successful caller is given exclusive access to the file data until 
    <b>NdisUnmapFile</b> or the 
    <a href="netvista.ndisclosefile">NdisCloseFile</a> function is called.

A miniport driver can map and unmap such an open file as necessary, using alternating calls to 
    <b>NdisMapFile</b> and 
    <a href="netvista.ndisunmapfile">NdisUnmapFile</a>. A call to 
    <b>NdisCloseFile</b> releases the 
    <i>FileHandle</i> and deallocates the buffer containing the file contents.

A miniport driver can call 
    <b>NdisMapFile</b> only during initialization.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff552308">NdisMapFile (NDIS 5.1)</a>) in Windows
   Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMapFile (NDIS 5.1)</b>) in Windows
   XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndisclosefile">NdisCloseFile</a>
</dt>
<dt>
<a href="netvista.ndisopenfile">NdisOpenFile</a>
</dt>
<dt>
<a href="netvista.ndisunmapfile">NdisUnmapFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMapFile function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

