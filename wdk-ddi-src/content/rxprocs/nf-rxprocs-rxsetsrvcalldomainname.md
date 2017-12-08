---
UID: NF.rxprocs.RxSetSrvCallDomainName
title: RxSetSrvCallDomainName function
author: windows-driver-content
description: RxSetSrvCallDomainName is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure).
old-location: ifsk\rxsetsrvcalldomainname.htm
old-project: ifsk
ms.assetid: 876b3932-780f-4d00-8afc-40960f8fcaaf
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxSetSrvCallDomainName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Mrxfcb.h, Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxSetSrvCallDomainName
req.alt-loc: rxprocs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# RxSetSrvCallDomainName function



## -description
<b>RxSetSrvCallDomainName</b> is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure).


## -syntax

````
NTSTATUS RxSetSrvCallDomainName(
  _In_ PMRX_SRV_CALL   SrvCall,
  _In_ PUNICODE_STRING DomainName
);
````


## -parameters

### -param SrvCall [in]

A pointer to the SRV_CALL structure. 

### -param DomainName [in]

A pointer to a buffer containing a zero-terminated Unicode string that names the domain to which this server belongs. 

## -returns
<b>RxSetSrvCallDomainName</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There were insufficient resources to complete this routine. The memory allocation request failed for nonpaged pool memory to store the new domain name.

 

## -remarks
The domain name may not be known at the beginning of a network redirector request. The <b>RxSetSrvCallDomainName</b> routine allows the domain name to be associated with <i>SrvCall</i> once it is known. This routine would normally be used as part of the creation and initialization of a SRV_CALL structure.

If a domain name is already associated with the <i>SrvCall</i> parameter, then this domain name will be removed and the memory associated with this entry in <i>SrvCall</i> will be freed.

If the <i>DomainName</i> parameter is not a <b>NULL</b> pointer, and the <i>DomainName</i> parameter has a length greater than zero, then <b>RxSetSrvCallDomainName</b> allocates space for the <b>pDomainName</b> member of <i>SrvCall</i> from nonpaged pool with a pool tag of RX_SRVCALL_PARAMS_POOLTAG. The <b>RxSetSrvCallDomainName</b> routine sets the <b>buffer</b>, <b>length</b>, and <b>MaximumLength</b> members of the <b>pDomainName</b> structure. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rxprocs.h (include Mrxfcb.h or Rxprocs.h)</dt>
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
<a href="ifsk.rxcreatesrvcall">RxCreateSrvCall</a>
</dt>
<dt>
<a href="ifsk.rxfinalizesrvcall">RxFinalizeSrvCall</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxSetSrvCallDomainName function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
