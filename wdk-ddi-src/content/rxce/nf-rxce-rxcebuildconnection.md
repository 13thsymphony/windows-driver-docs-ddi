---
UID: NF.rxce.RxCeBuildConnection
title: RxCeBuildConnection function
author: windows-driver-content
description: RxCeBuildConnection establishes a connection between a local RDBSS connection address and a given remote address.
old-location: ifsk\rxcebuildconnection.htm
old-project: ifsk
ms.assetid: 3d4c2e69-7cdc-4eee-b56c-b1485768e942
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxCeBuildConnection
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
req.alt-api: RxCeBuildConnection
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
req.product: Windows 10 or later.
---

# RxCeBuildConnection function



## -description
<b>RxCeBuildConnection</b> establishes a connection between a local RDBSS connection address and a given remote address. 



## -syntax

````
NTSTATUS RxCeBuildConnection(
  _In_    PRXCE_ADDRESS                  pAddress,
  _In_    PRXCE_CONNECTION_INFORMATION   pConnectionInformation,
  _In_    PRXCE_CONNECTION_EVENT_HANDLER pHandler,
  _In_    PVOID                          pEventContext,
  _Inout_ PRXCE_CONNECTION               pConnection,
  _Inout_ PRXCE_VC                       pVc
);
````


## -parameters

### -param pAddress [in]

A pointer to the local RDBSS connection engine address.


### -param pConnectionInformation [in]

A pointer to the connection information that specifies the remote address.


### -param pHandler [in]

A pointer to the event handler for processing receive indications.


### -param pEventContext [in]

A pointer to the context parameter to be passed back to the event handler and used for indications.


### -param pConnection [in, out]

On input, this parameter contains a pointer to an uninitialized RDBSS connection. On output when this call is successful, the connection is properly initialized.


### -param pVc [in, out]

On input, this parameter contains a pointer to an uninitialized RDBSS virtual circuit. On output when this call is successful, the virtual circuit is associated with the connection and the virtual circuit is properly initialized.


## -returns
<b>RxCeBuildConnection</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The allocation of nonpaged pool memory needed by this routine failed. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the parameters passed to this routine was invalid. 

 


## -remarks
<b>RxCeBuildConnection</b> should be called in the context of a system worker thread.

When <b>RxCeBuildConnection</b> is successful, the data members in the RXCE_CONNECTION structure pointed to by the <i>pConnection</i> parameter and the data members in the RXCE_VC structure pointed to by the <i>pVc</i> parameter will be properly initialized and the virtual circuit will be associated with the connection.

<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. 


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
<dt>Rxce.h (include Rxce.h)</dt>
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
<a href="ifsk.rxceteardownconnection">RxCeTearDownConnection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeBuildConnection function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

