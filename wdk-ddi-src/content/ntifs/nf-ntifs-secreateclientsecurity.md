---
UID: NF:ntifs.SeCreateClientSecurity
title: SeCreateClientSecurity function
author: windows-driver-content
description: The SeCreateClientSecurity routine initializes a security client context structure with the information needed to call SeImpersonateClientEx.
old-location: ifsk\secreateclientsecurity.htm
old-project: ifsk
ms.assetid: 10aadf41-79c4-46d6-a5ae-e8b3b5f338f0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeCreateClientSecurity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeCreateClientSecurity
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# SeCreateClientSecurity function



## -description
The <b>SeCreateClientSecurity</b> routine initializes a security client context structure with the information needed to call <b>SeImpersonateClientEx</b>.



## -syntax

````
NTSTATUS SeCreateClientSecurity(
  _In_  PETHREAD                     ClientThread,
  _In_  PSECURITY_QUALITY_OF_SERVICE ClientSecurityQos,
  _In_  BOOLEAN                      ServerIsRemote,
  _Out_ PSECURITY_CLIENT_CONTEXT     ClientContext
);
````


## -parameters

### -param ClientThread [in]

Pointer to the thread of the client to be impersonated.


### -param ClientSecurityQos [in]

Pointer to a caller-allocated SECURITY_QUALITY_OF_SERVICE structure indicating what form of impersonation is to be performed.


### -param ServerIsRemote [in]

Set to <b>TRUE</b> if the server of the client's request is remote.


### -param ClientContext [out]

Pointer to a caller-allocated SECURITY_CLIENT_CONTEXT structure to be initialized.


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The security client context was successfully initialized.
<dl>
<dt><b>STATUS_BAD_IMPERSONATION_LEVEL</b></dt>
</dl>The client to be impersonated is currently impersonating a client of its own, and one of the following is true:

The client's effective token cannot be passed on for use by another server, because its impersonation level is <b>SecurityAnonymous</b> or <b>SecurityIdentification</b>. 

<i>ServerIsRemote</i> is <b>TRUE</b>, and the client thread is impersonating its client at other than <b>SecurityDelegation</b> level.

 


## -remarks
<b>SeCreateClientSecurity</b> initializes a client security context block to represent a client's security context.

If the <b>ContextTrackingMode</b> member of <i>ClientSecurityQos</i> is set to SECURITY_DYNAMIC_TRACKING and <i>ServerIsRemote</i> is set to <b>FALSE</b>, <b>SeCreateClientSecurity</b> uses a reference to the client's effective token. Otherwise, <b>SeCreateClientSecurity</b> creates a copy of the client's token.

Each call to <b>SeCreateClientSecurity</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-sedeleteclientsecurity.md">SeDeleteClientSecurity</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seimpersonateclientex.md">SeImpersonateClientEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeCreateClientSecurity routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

