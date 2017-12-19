---
UID: NF.fltkernel.FltAllocateExtraCreateParameterList
title: FltAllocateExtraCreateParameterList function
author: windows-driver-content
description: The FltAllocateExtraCreateParameterList routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure.
old-location: ifsk\fltallocateextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 0130e35f-a6a8-4fa9-9922-1d1d0f43cb2a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltAllocateExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltAllocateExtraCreateParameterList
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltAllocateExtraCreateParameterList function



## -description
The <b>FltAllocateExtraCreateParameterList</b> routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure.



## -syntax

````
NTSTATUS FltAllocateExtraCreateParameterList(
  _In_  PFLT_FILTER                  Filter,
  _In_  FSRTL_ALLOCATE_ECPLIST_FLAGS Flags,
  _Out_ PECP_LIST                    *EcpList
);
````


## -parameters

### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param Flags [in]

Defines pool allocation options.  If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is combined with the <i>Flags</i> parameter by using a bitwise OR operation, any pool allocated by the routine will be charged against the current process' memory quota.


### -param EcpList [out]

Receives a pointer to an initialized ECP list structure.  If the routine failed to allocate sufficient pool, <i>*EcpList</i> will be <b>NULL</b> and the routine will return status code STATUS_INSUFFICIENT_RESOURCES.


## -returns
<b>FltAllocateExtraCreateParameterList</b> can return one of the following values:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltAllocateExtraCreateParameterList</b> was unable to allocate sufficient memory for an ECP list structure.  In this case, <i>*EcpList</i> will be <b>NULL</b>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The ECP list structure was successfully allocated and initialized.  In this case, a pointer to the initialized list structure is returned in the <i>*EcpList</i> parameter.

 


## -remarks
This routine is available starting with Windows Vista. 

Whether the operating system automatically frees memory that <b>FltAllocateExtraCreateParameterList</b> allocates depends on when <b>FltAllocateExtraCreateParameterList</b> is called, as shown in the following situations:

A caller can invoke <b>FltAllocateExtraCreateParameterList</b> to allocate the ECP_LIST and add one or more ECP context structures before the caller invokes the <a href="ifsk.fltcreatefileex2">FltCreateFileEx2</a> routine. In this situation, the operating system does not free any of the ECP context structures. Therefore, the caller can make multiple calls to <b>FltCreateFileEx2</b> with the same ECP set. When the caller is done with the ECP_LIST, the caller must call the <a href="ifsk.fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a> routine to free the ECP_LIST.

While a file system filter driver processes an <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a> request, the file system filter driver can call <a href="ifsk.fltinsertextracreateparameter">FltInsertExtraCreateParameter</a> to attach an ECP to an existing ECP_LIST. If the ECP_LIST does not exist, the caller must call <b>FltAllocateExtraCreateParameterList</b> to create the ECP_LIST. In this situation, the ECP_LIST and the ECP context structure are automatically cleaned up by the I/O manager when the create operation completes. This allows a filter driver's ECP to be properly propagated across the processing of reparse points. This process might require multiple IRP_MJ_CREATE requests to be generated.

If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is used with the <i>Flags</i> parameter, as described above, a normal pageable pool is allocated. Otherwise, a pageable pool is allocated by using an internal lookaside list.


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
This routine is available starting with Windows Vista. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
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
<a href="ifsk.ecp_list">ECP_LIST</a>
</dt>
<dt>
<a href="ifsk.fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>
</dt>
<dt>
<a href="ifsk.fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="ifsk.fltcreatefileex2">FltCreateFileEx2</a>
</dt>
<dt>
<a href="ifsk.fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="ifsk.fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>
</dt>
<dt>
<a href="ifsk.fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="ifsk.fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>
</dt>
<dt>
<a href="ifsk.fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="ifsk.fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>
</dt>
<dt>
<a href="ifsk.iocreatefileex">IoCreateFileEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAllocateExtraCreateParameterList routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

