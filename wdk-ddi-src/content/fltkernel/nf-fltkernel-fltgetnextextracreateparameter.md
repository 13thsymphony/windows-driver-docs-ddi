---
UID: NF.fltkernel.FltGetNextExtraCreateParameter
title: FltGetNextExtraCreateParameter
author: windows-driver-content
description: The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.
old-location: ifsk\fltgetnextextracreateparameter.htm
old-project: ifsk
ms.assetid: 8eae5ac8-9da5-475f-8fbb-5e118bad4e67
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltGetNextExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetNextExtraCreateParameter
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.iface: 
---

# FltGetNextExtraCreateParameter function



## -description
<p>The <b>FltGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.</p>


## -syntax

````
NTSTATUS FltGetNextExtraCreateParameter(
  _In_      PFLT_FILTER Filter,
  _In_      PECP_LIST   EcpList,
  _In_opt_  PVOID       CurrentEcpContext,
  _Out_opt_ LPGUID      NextEcpType,
  _Out_opt_ PVOID       *NextEcpContext,
  _Out_opt_ ULONG       *NextEcpContextSize
);
````


## -parameters
<dl>

### -param Filter [in]

<dd>
<p>Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.</p>
</dd>

### -param EcpList [in]

<dd>
<p>Pointer to the ECP list to examine.</p>
</dd>

### -param CurrentEcpContext [in, optional]

<dd>
<p>Optional pointer to an ECP in the given ECP list.  If present, <b>FltGetNextExtraCreateParameter</b> returns the ECP after the <i>CurrentEcpContext</i> ECP.  If <i>CurrentEcpContext</i> is <b>NULL</b>, <b>FltGetNextExtraCreateParameter</b> returns the first ECP in the list.</p>
</dd>

### -param NextEcpType [out, optional]

<dd>
<p>Optional parameter that receives a pointer to the GUID of the returned ECP.</p>
</dd>

### -param NextEcpContext [out, optional]

<dd>
<p>Optional parameter that receives a pointer to the returned ECP.</p>
</dd>

### -param NextEcpContextSize [out, optional]

<dd>
<p>Optional parameter that receives the size, in bytes, of the returned ECP.</p>
</dd>
</dl>

## -returns
<p><b>FltGetNextExtraCreateParameter</b> returns one of the following NTSTATUS values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>An ECP was found in the <i>EcpList</i> ECP list.</p><dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl><p>The <i>EcpList</i> ECP list is empty or <i>CurrentEcpContext</i> is the last ECP in the list that is, there is no next ECP list element).  Additionally, <i>NextEcpContext</i> is set to <b>NULL</b> and <i>NextEcpContextSize</i> is set to zero.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <i>EcpList</i> parameter is <b>NULL</b>.</p>

<p> </p>

## -remarks
<p>This routine is available starting with Windows Vista. </p>

<p>The<b>FltGetNextExtraCreateParameter</b> routine processes an ECP list in a non-circular manner.  That is, if the ECP pointed to by the <i>CurrentEcpContext</i> parameter is the last ECP element in the ECP list, there is no "next" ECP in the list and the routine returns STATUS_NOT_FOUND.</p>

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
<p>This routine is available starting with Windows Vista. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>
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
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetNextExtraCreateParameter routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
