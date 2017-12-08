---
UID: NF.ntifs.FsRtlGetEcpListFromIrp
title: FsRtlGetEcpListFromIrp function
author: windows-driver-content
description: The FsRtlGetEcpListFromIrp routine returns a pointer to an extra create parameter (ECP) context structure list that is associated with a given IRP_MJ_CREATE operation.
old-location: ifsk\fsrtlgetecplistfromirp.htm
old-project: ifsk
ms.assetid: 9e225f00-f830-488f-8bf0-666290dc40b0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlGetEcpListFromIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlGetEcpListFromIrp
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

# FsRtlGetEcpListFromIrp function



## -description
The <b>FsRtlGetEcpListFromIrp </b>routine returns a pointer to an extra create parameter (ECP) context structure list that is associated with a given IRP_MJ_CREATE operation.


## -syntax

````
NTSTATUS FsRtlGetEcpListFromIrp(
  _In_  PIRP      Irp,
  _Out_ PECP_LIST *EcpList
);
````


## -parameters

### -param Irp [in]

A pointer to the IRP for an IRP_MJ_CREATE operation from which the ECP context structure list is to be extracted.

### -param EcpList [out]

Receives a pointer to the ECP context structure list that is associated with the IRP.

## -returns
<b>FsRtlGetEcpListFromIrp</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The given IRP was not an IRP-based IRP_MJ_CREATE operation. In this case, <i>EcpList</i> is undefined. 

 

## -remarks
To attach an ECP context structure list to an IRP, use the <a href="ifsk.fsrtlsetecplistintoirp">FsRtlSetEcpListIntoIrp</a> routine.

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
Available in Windows Vista and later versions of the Windows operating systems.
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
<a href="ifsk.fsrtlsetecplistintoirp">FsRtlSetEcpListIntoIrp</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetEcpListFromIrp routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
