---
UID: NF:ntifs.FsRtlMupGetProviderInfoFromFileObject
title: FsRtlMupGetProviderInfoFromFileObject function
author: windows-driver-content
description: The FsRtlMupGetProviderInfoFromFileObject routine gets information about a network redirector that is registered with the multiple UNC provider (MUP) from a file object for a file that is located on a remote file system.
old-location: ifsk\fsrtlmupgetproviderinfofromfileobject.htm
old-project: ifsk
ms.assetid: 3f4d8c5c-3a83-4027-8d9e-5ff7db4a6853
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlMupGetProviderInfoFromFileObject, FsRtlMupGetProviderInfoFromFileObject routine [Installable File System Drivers], fsrtlref_7ad681c5-3f7c-42d1-8644-7cd677101413.xml, ifsk.fsrtlmupgetproviderinfofromfileobject, ntifs/FsRtlMupGetProviderInfoFromFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlMupGetProviderInfoFromFileObject function is available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlMupGetProviderInfoFromFileObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlMupGetProviderInfoFromFileObject function
The <b>FsRtlMupGetProviderInfoFromFileObject</b> routine gets information about a network redirector that is registered with the multiple UNC provider (MUP) from a file object for a file that is located on a remote file system.

## Syntax

````
NTSTATUS FsRtlMupGetProviderInfoFromFileObject(
  _In_    PFILE_OBJECT pFileObject,
  _In_    ULONG        Level,
  _Out_   PVOID        pBuffer,
  _Inout_ PULONG       pBufferSize
);
````

## Parameters

`pFileObject`

A pointer to a file object of a file that is located on a remote file system.

`Level`

The level of information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine. For more information about the possible values for this parameter, see the Remarks section.

`pBuffer`

A pointer to a buffer that receives the information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine. For more information about the format of the data that is returned in this buffer, see the Remarks section.

`pBufferSize`

A pointer to a ULONG-typed variable that contains the size, in bytes, of the buffer that is pointed to by the <i>pBuffer</i> parameter. If the routine succeeds, this variable receives the size, in bytes, of data that is returned in the buffer.


## Return Value

The <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns one of the following NTSTATUS values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The information about the network redirector was successfully returned in the buffer that is pointed to by the <i>pBuffer </i>parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters was <b>NULL</b> or contained an invalid value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The file object that is pointed to by the <i>pFileObject </i>parameter does not correspond to a completely opened remote file system file object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer that is pointed to by the <i>pBuffer</i> parameter is too small to return any data. In this situation, the variable that is pointed to by the <i>pBufferSize</i> parameter receives the required size, in bytes, of the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer that is pointed to by the <i>pBuffer</i> parameter is too small to return all of the data. Only the data that would fit in the buffer was returned. In this situation, the variable that is pointed to by the <i>pBufferSize</i> parameter receives the required size, in bytes, of the buffer.

</td>
</tr>
</table>

## Remarks

A file system filter driver can call the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine to get information about a network redirector from a file object for a file that is located on a remote file system. The amount of information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine depends on the value of the <i>Level</i> parameter. If the <i>Level </i>parameter is set to 1, the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns a FSRTL_MUP_PROVIDER_INFO_LEVEL_1 structure in the buffer that is pointed to by the <i>pBuffer </i>parameter. The FSRTL_MUP_PROVIDER_INFO_LEVEL_1 structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _FSRTL_MUP_PROVIDER_INFO_LEVEL_1 {
  ULONG32  ProviderId;
} FSRTL_MUP_PROVIDER_INFO_LEVEL_1, *PFSRTL_MUP_PROVIDER_INFO_LEVEL_1;</pre>
</td>
</tr>
</table></span></div>


If the <i>Level </i>parameter is set to 2, the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns a FSRTL_MUP_PROVIDER_INFO_LEVEL_2 structure in the buffer that is pointed to by the <i>pBuffer </i>parameter. The FSRTL_MUP_PROVIDER_INFO_LEVEL_2 structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _FSRTL_MUP_PROVIDER_INFO_LEVEL_2 {
  ULONG32  ProviderId;
  UNICODE_STRING  ProviderName;
} FSRTL_MUP_PROVIDER_INFO_LEVEL_2, *PFSRTL_MUP_PROVIDER_INFO_LEVEL_2;</pre>
</td>
</tr>
</table></span></div>


A file system filter driver can quickly compare the value of the provider identifier to the value of other provider identifiers without needing to do a string comparison.

The value of the UNC provider identifier for a particular network redirector remains the same if the network redirector is unloaded from the system and then reloaded back into the system.

To get the UNC provider identifier of a network redirector from the device name of the network redirector, a file system filter driver can call the <a href="..\ntifs\nf-ntifs-fsrtlmupgetprovideridfromname.md">FsRtlMupGetProviderIdFromName</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FsRtlMupGetProviderInfoFromFileObject function is available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-fsrtlmupgetprovideridfromname.md">FsRtlMupGetProviderIdFromName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMupGetProviderInfoFromFileObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>