---
UID: NF.ntifs.PsImpersonateClient
title: PsImpersonateClient function
author: windows-driver-content
description: The PsImpersonateClient routine causes a server thread to impersonate a client.
old-location: ifsk\psimpersonateclient.htm
old-project: ifsk
ms.assetid: 69cc1253-07eb-43cf-abc7-5ad02ecb014d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PsImpersonateClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsImpersonateClient
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
---

# PsImpersonateClient function



## -description
The <b>PsImpersonateClient</b> routine causes a server thread to impersonate a client. 



## -syntax

````
NTSTATUS PsImpersonateClient(
  _Inout_ PETHREAD                     Thread,
  _In_    PACCESS_TOKEN                Token,
  _In_    BOOLEAN                      CopyOnOpen,
  _In_    BOOLEAN                      EffectiveOnly,
  _In_    SECURITY_IMPERSONATION_LEVEL ImpersonationLevel
);
````


## -parameters

### -param Thread [in, out]

Pointer to the server thread that is to impersonate the client. 


### -param Token [in]

Pointer to the token to be assigned as the impersonation token. This token can be a primary token or an impersonation token. Set to <b>NULL</b> to end the impersonation. 


### -param CopyOnOpen [in]

Specifies whether the token can be opened directly. Set to <b>TRUE</b> to specify that the token cannot be opened directly. In this case, the token must be duplicated, and the duplicate token used instead. Set to <b>FALSE</b> to allow the token to be opened directly. 


### -param EffectiveOnly [in]

Set to <b>FALSE</b> to allow the server to enable groups and privileges that are currently disabled in the client security context, <b>TRUE</b> otherwise.


### -param ImpersonationLevel [in]

A <a href="ifsk.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a> value that specifies the impersonation level at which the server is to access the token. 


## -returns
<b>PsImpersonateClient</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>It was not possible to impersonate a client because of job restrictions.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>There was insufficient memory to complete the operation.

 


## -remarks
<b>PsImpersonateClient</b> causes the specified server thread to impersonate the specified client. 

The server thread could already be impersonating a client when <b>PsImpersonateClient</b> is called. If this is the case, the reference count on the token representing that client is decremented. To preserve this token for later use, drivers should call <a href="ifsk.psreferenceimpersonationtoken">PsReferenceImpersonationToken</a> before calling <b>PsImpersonateClient</b> and save the pointer that is returned by <b>PsReferenceImpersonationToken</b>. 

To end the new impersonation and return the server thread to the previous impersonation, call <b>PsImpersonateClient</b> again, passing the saved pointer for the <i>Token</i> parameter. To end all impersonations, call the <a href="ifsk.psreverttoself">PsRevertToSelf</a> routine.

Otherwise, to end the impersonation and return the server thread to its original security context (that is, the one represented by its primary token), call <b>PsImpersonateClient</b> again, passing a <b>NULL</b> pointer for the <i>Token</i> parameter. 

The <b>PsImpersonateClient</b> routine can fail to successfully return the server thread to the previous impersonation if the thread is already impersonating or there are job restrictions.

It is extremely unsafe to raise the privilege state of an untrusted user thread (take a user's thread and impersonate LocalSystem, for example). If an untrusted user thread had its privilege raised, the user could grab the thread token after it has been elevated and subvert the security of the entire system. 

In cases where a higher privilege state is required, the task should be dispatched to a work queue where the task can be safely handled by system worker thread . This way no impersonation is necessary.

The <a href="ifsk.seimpersonateclientex">SeImpersonateClientEx</a> routine can be used to cause a thread to impersonate a user.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 


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
Available in Windows XP and later versions of the Windows operating systems.

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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.psgetcurrentthread">PsGetCurrentThread</a>
</dt>
<dt>
<a href="ifsk.psreferenceimpersonationtoken">PsReferenceImpersonationToken</a>
</dt>
<dt>
<a href="ifsk.psreverttoself">PsRevertToSelf</a>
</dt>
<dt>
<a href="ifsk.seimpersonateclientex">SeImpersonateClientEx</a>
</dt>
<dt>
<a href="ifsk.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsImpersonateClient routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

