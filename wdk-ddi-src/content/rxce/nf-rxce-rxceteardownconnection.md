---
UID: NF:rxce.RxCeTearDownConnection
title: RxCeTearDownConnection function
author: windows-driver-content
description: RxCeTearDownConnection tears down a given connection between a local RDBSS connection address and a remote address.
old-location: ifsk\rxceteardownconnection.htm
old-project: ifsk
ms.assetid: 71b48983-af12-4361-8cf9-adec1afffb65
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCeTearDownConnection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxCeTearDownConnection
req.alt-loc: rxce.h
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
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeTearDownConnection function



## -description
<b>RxCeTearDownConnection</b> tears down a given connection between a local RDBSS connection address and a remote address.



## -syntax

````
NTSTATUS RxCeTearDownConnection(
  _In_ PRXCE_CONNECTION pConnection
);
````


## -parameters

### -param pConnection [in]

A pointer to an connection to be torn down.


## -returns
<b>RxCeTearDownConnection</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The allocation of nonpaged pool memory needed by this routine failed. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the parameters passed to this routine was invalid. 

 


## -remarks
When <b>RxCeTearDownConnection</b> is successful, the data members in the RXCE_CONNECTION structure pointed to by the <i>pConnection</i> parameter will be properly uninitialized, and allocated memory for connection information and handler will be freed. 


## -see-also
<dl>
<dt>
<a href="..\rxce\nf-rxce-rxcebuildconnection.md">RxCeBuildConnection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeTearDownConnection function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

