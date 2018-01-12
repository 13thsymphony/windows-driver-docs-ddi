---
UID: NF:ksproxy.IKsPin.KsPropagateAcquire
title: IKsPin::KsPropagateAcquire method
author: windows-driver-content
description: The KsPropagateAcquire method directs all the pins on the filter to attain the Acquire state.
old-location: stream\ikspin_kspropagateacquire.htm
old-project: stream
ms.assetid: 059bef5a-1db7-4fd7-a19b-c34df81f4447
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPin, IKsPin::KsPropagateAcquire, KsPropagateAcquire
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
req.alt-api: IKsPin.KsPropagateAcquire
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

# IKsPin::KsPropagateAcquire method



## -description
The <b>KsPropagateAcquire</b> method directs all the pins on the filter to attain the Acquire state. 



## -syntax

````
HRESULT KsPropagateAcquire();
````


## -parameters


## -returns
Returns NOERROR if successful; otherwise, returns an error code.

Returns NOERROR if successful; otherwise, returns an error code.

Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
By using this method, a Communication source pin can direct the sink to which it is connected to change state before the Source. This forces the entire filter to which the sink belongs to change state so that any Acquire can be further propagated if needed.

This method is for proxy use and is not recommended for application use.


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
<a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsPropagateAcquire method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

