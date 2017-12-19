---
UID: NF.ntifs.FsRtlMupGetProviderIdFromName
title: FsRtlMupGetProviderIdFromName function
author: windows-driver-content
description: The FsRtlMupGetProviderIdFromName routine gets the provider identifier of a network redirector that is registered with the multiple UNC provider (MUP) from the device name of the network redirector.
old-location: ifsk\fsrtlmupgetprovideridfromname.htm
old-project: ifsk
ms.assetid: a572398c-1755-4fc6-844b-85059d4d02cb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlMupGetProviderIdFromName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlMupGetProviderIdFromName function is available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlMupGetProviderIdFromName
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# FsRtlMupGetProviderIdFromName function



## -description
The <b>FsRtlMupGetProviderIdFromName</b> routine gets the provider identifier of a network redirector that is registered with the multiple UNC provider (MUP) from the device name of the network redirector.



## -syntax

````
NTSTATUS FsRtlMupGetProviderIdFromName(
  _In_  PUNICODE_STRING pProviderName,
  _Out_ PULONG32        pProviderId
);
````


## -parameters

### -param pProviderName [in]

A pointer to a Unicode string that contains the device name of the network redirector.


### -param pProviderId [out]

A pointer to a ULONG32-typed variable that receives the provider identifier of the network redirector.


## -returns
The <b>FsRtlMupGetProviderIdFromName</b> routine returns one of the following NTSTATUS values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The provider identifier of the network redirector was successfully returned in the variable that is pointed to by the <i>pProviderId </i>parameter.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the parameters is <b>NULL</b>.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The name of the network redirector specified in the <i>pProviderName </i>parameter does not match the name of any of the UNC providers that are registered with the MUP.

 


## -remarks
A file system filter driver can call the <b>FsRtlMupGetProviderIdFromName</b> routine to get the provider identifier of a network redirector from the name of the network redirector. The file system filter driver can quickly compare the value of this identifier to the value of other provider identifiers without needing to do a string comparison.

The value of the provider identifier for a particular network redirector remains the same if the network redirector is unloaded from the system and then reloaded back into the system.

To get the provider identifier of a network redirector from a file object, a file system filter driver can call the <a href="ifsk.fsrtlmupgetproviderinfofromfileobject">FsRtlMupGetProviderInfoFromFileObject</a> routine.


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
The FsRtlMupGetProviderIdFromName function is available in Windows Vista and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsrtlmupgetproviderinfofromfileobject">FsRtlMupGetProviderInfoFromFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMupGetProviderIdFromName routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

