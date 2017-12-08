---
UID: NF.fltkernel.FltGetNextExtraCreateParameter
title: FltGetNextExtraCreateParameter function
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
---

# FltGetNextExtraCreateParameter function



## -description
The <b>FltGetNextExtraCreateParameter</b> routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list.


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

### -param Filter [in]

Opaque filter pointer to the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpList [in]

Pointer to the ECP list to examine.

### -param CurrentEcpContext [in, optional]

Optional pointer to an ECP in the given ECP list.  If present, <b>FltGetNextExtraCreateParameter</b> returns the ECP after the <i>CurrentEcpContext</i> ECP.  If <i>CurrentEcpContext</i> is <b>NULL</b>, <b>FltGetNextExtraCreateParameter</b> returns the first ECP in the list.

### -param NextEcpType [out, optional]

Optional parameter that receives a pointer to the GUID of the returned ECP.

### -param NextEcpContext [out, optional]

Optional parameter that receives a pointer to the returned ECP.

### -param NextEcpContextSize [out, optional]

Optional parameter that receives the size, in bytes, of the returned ECP.

## -returns
<b>FltGetNextExtraCreateParameter</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>An ECP was found in the <i>EcpList</i> ECP list.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The <i>EcpList</i> ECP list is empty or <i>CurrentEcpContext</i> is the last ECP in the list that is, there is no next ECP list element).  Additionally, <i>NextEcpContext</i> is set to <b>NULL</b> and <i>NextEcpContextSize</i> is set to zero.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>EcpList</i> parameter is <b>NULL</b>.

 

## -remarks
This routine is available starting with Windows Vista. 

The<b>FltGetNextExtraCreateParameter</b> routine processes an ECP list in a non-circular manner.  That is, if the ECP pointed to by the <i>CurrentEcpContext</i> parameter is the last ECP element in the ECP list, there is no "next" ECP in the list and the routine returns STATUS_NOT_FOUND.

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
This routine is available starting with Windows Vista. 
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
DLL
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
<a href="ifsk.fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>
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
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetNextExtraCreateParameter routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
