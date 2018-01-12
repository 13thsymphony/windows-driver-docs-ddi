---
UID: NF:ntifs.FsRtlFindExtraCreateParameter
title: FsRtlFindExtraCreateParameter function
author: windows-driver-content
description: The FsRtlFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.
old-location: ifsk\fsrtlfindextracreateparameter.htm
old-project: ifsk
ms.assetid: e72958d0-b7ff-45b6-bdd2-f894d5b44cf4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlFindExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFindExtraCreateParameter routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlFindExtraCreateParameter
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
req.typenames: TOKEN_TYPE
---

# FsRtlFindExtraCreateParameter function



## -description
The <b>FsRtlFindExtraCreateParameter</b> routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found.



## -syntax

````
NTSTATUS FsRtlFindExtraCreateParameter(
  _In_      PECP_LIST EcpList,
  _In_      LPCGUID   EcpType,
  _Out_opt_ PVOID     *EcpContext,
  _Out_opt_ ULONG     *EcpContextSize
);
````


## -parameters

### -param EcpList [in]

Pointer to the ECP list structure that <b>FsRtlFindExtraCreateParameter</b> uses to search for the ECP context structure, supplied by the <i>EcpType</i> parameter.


### -param EcpType [in]

Pointer to a GUID that uniquely identifies the ECP context structure.  This GUID value is used by the <b>FsRtlFindExtraCreateParamter</b> routine to determine if the ECP context structure exists in the ECP list, supplied by the <i>EcpList</i> parameter.


### -param EcpContext [out, optional]

Optional parameter that receives a pointer to the found ECP context structure.  If the ECP context structure is not found in the ECP list, <i>EcpContext</i> is set to <b>NULL</b>.  If <i>EcpContext</i> is set to <b>NULL</b> by the caller, the return value of <b>FsRtlFindExtraCreateParamter</b> can be used to determine if the ECP context structure is in the ECP list.


### -param EcpContextSize [out, optional]

Optional parameter that receives the size, in bytes, of the found ECP context structure.  If the ECP context structure is not found, <i>EcpContextSize</i> is set to zero.


## -returns
<b>FsRtlFindExtraCreateParameter</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><b>FsRtlFindExtraCreateParameter </b>found the specified ECP context structure in the specified ECP list.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl><b>FsRtlFindExtraCreateParameter</b> didn't find the specified ECP context structure  in the specified ECP list.

 


## -remarks


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
The FsRtlFindExtraCreateParameter routine is available starting with Windows Vista. 

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt><b>FltAllocateExtraCreateParameterFromLookasideList</b></dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFindExtraCreateParameter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

