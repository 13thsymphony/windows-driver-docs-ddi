---
UID: NF:ksproxy.IKsPinEx.KsNotifyError
title: IKsPinEx::KsNotifyError method
author: windows-driver-content
description: The KsNotifyError method notifies the filter graph of an error to give the filter graph an opportunity to halt.
old-location: stream\ikspinex_ksnotifyerror.htm
old-project: stream
ms.assetid: a2526734-c0bf-4f6b-b91e-2f6891c46c69
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPinEx, IKsPinEx::KsNotifyError, KsNotifyError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPinEx.KsNotifyError
req.alt-loc: ksproxy.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: PIPE_STATE
---

# IKsPinEx::KsNotifyError method



## -description
The <b>KsNotifyError</b> method notifies the filter graph of an error to give the filter graph an opportunity to halt. 



## -syntax

````
VOID KsNotifyError(
  [in] IMediaSample *Sample,
  [in] HRESULT      hr
);
````


## -parameters

### -param Sample [in]

Pointer to the <b>IMediaSample</b> interface for the associated media sample.


### -param hr [in]

Error value for notification. If ERROR_OPERATION_ABORTED (that is, the I/O was purposefully canceled), the filter graph is not notified. 


## -returns
None


## -remarks
The <b>KsNotifyError</b> method notifies the filter graph of the specific error using the EC_ERRORABORT event, which specifies that the error forced the termination of an I/O operation.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.


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
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspinex.md">IKsPinEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinEx::KsNotifyError method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

