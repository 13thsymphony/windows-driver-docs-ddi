---
UID: NF.ntifs.FsRtlAllocateExtraCreateParameterList
title: FsRtlAllocateExtraCreateParameterList
author: windows-driver-content
description: The FsRtlAllocateExtraCreateParameterList routine allocates paged pool memory for an ECP_LIST structure and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 93888920-73b2-41e4-8d49-e5235ee93307
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FsRtlAllocateExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlAllocateExtraCreateParameterList routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlAllocateExtraCreateParameterList
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
req.iface: 
---

# FsRtlAllocateExtraCreateParameterList function



## -description
<p>The <b>FsRtlAllocateExtraCreateParameterList</b> routine allocates paged pool memory for an <a href="ifsk.ecp_list">ECP_LIST</a> structure and generates a pointer to that structure.</p>


## -syntax

````
NTSTATUS FsRtlAllocateExtraCreateParameterList(
  _In_  FSRTL_ALLOCATE_ECPLIST_FLAGS Flags,
  _Out_ PECP_LIST                    *EcpList
);
````


## -parameters
<dl>

### -param <i>Flags</i> [in]

<dd>
<p>Defines pool allocation options.  If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is combined with the <i>Flags</i> parameter by using a bitwise OR operation, any pool allocated by <b>FsRtlAllocateExtraCreateParameterList</b>  will be charged against the current process' memory quota.</p>
</dd>

### -param <i>EcpList</i> [out]

<dd>
<p>Receives a pointer to an initialized ECP list structure.  If <b>FsRtlAllocateExtraCreateParameterList</b>  failed to allocate sufficient pool, <i>*EcpList</i> will be <b>NULL</b> and <b>FsRtlAllocateExtraCreateParameterList</b>  will return status code STATUS_INSUFFICIENT_RESOURCES.</p>
</dd>
</dl>

## -returns
<p><b>FsRtlAllocateExtraCreateParameterList</b> can return one of the following values:</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p><b>FsRtlAllocateExtraCreateParameterList</b> was unable to allocate sufficient memory for an ECP list structure.  In this case, <i>*EcpList</i> will be <b>NULL</b>.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The memory for the <a href="ifsk.ecp_list">ECP_LIST</a> structure was successfully allocated and initialized.  In this case, a pointer to the initialized list structure is returned in the <i>EcpList</i> parameter.</p>

<p> </p>

## -remarks
<p>Whether the operating system automatically frees memory that <b>FsRtlAllocateExtraCreateParameterList</b> allocates depends on when <b>FsRtlAllocateExtraCreateParameterList</b> is called, as shown in the following situations:</p>

<p>A caller can invoke <b>FsRtlAllocateExtraCreateParameterList</b> to allocate the ECP_LIST and add one or more ECP context structures before the caller invokes the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine. In this situation, the operating system does not free any of the ECP context structures. Therefore, the caller can make multiple calls to <b>IoCreateFileEx</b> with the same ECP set. When the caller is done with the ECP_LIST, the caller must call the <a href="..\ntifs\nf-ntifs-fsrtlfreeextracreateparameterlist.md">FsRtlFreeExtraCreateParameterList</a> routine to free the ECP_LIST.</p>

<p>While a file system or file system filter driver processes an <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a> request, the file system or file system filter driver can call <a href="..\ntifs\nf-ntifs-fsrtlinsertextracreateparameter.md">FsRtlInsertExtraCreateParameter</a> to attach an ECP to an existing ECP_LIST. If the ECP_LIST does not exist, the caller must call <b>FsRtlAllocateExtraCreateParameterList</b> to create the ECP_LIST. In this situation, the ECP_LIST and the ECP context structure are automatically cleaned up by the I/O manager when the create operation completes. This allows a file system's or filter driver's ECP to be properly propagated across the processing of reparse points. This process might require multiple IRP_MJ_CREATE requests to be generated. </p>

<p>If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is used with the <i>Flags</i> parameter, a pageable pool is allocated. Otherwise, a pageable pool is allocated by using an internal lookaside list.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>The FsRtlAllocateExtraCreateParameterList routine is available starting with Windows Vista. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ecp_list">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>
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
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAllocateExtraCreateParameterList routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
