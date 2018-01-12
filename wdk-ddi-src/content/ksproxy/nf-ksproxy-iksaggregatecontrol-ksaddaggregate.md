---
UID: NF:ksproxy.IKsAggregateControl.KsAddAggregate
title: IKsAggregateControl::KsAddAggregate method
author: windows-driver-content
description: The KsAddAggregate method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the IKsAggregateControl interface.
old-location: stream\iksaggregatecontrol_ksaddaggregate.htm
old-project: stream
ms.assetid: 9808bdb9-17f9-4a80-90c7-e85ab35b74ae
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsAggregateControl, IKsAggregateControl::KsAddAggregate, KsAddAggregate
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
req.alt-api: IKsAggregateControl.KsAddAggregate
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

# IKsAggregateControl::KsAddAggregate method



## -description
The <b>KsAddAggregate</b> method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the <a href="..\ksproxy\nn-ksproxy-iksaggregatecontrol.md">IKsAggregateControl</a> interface.



## -syntax

````
HRESULT KsAddAggregate(
  [in] REFGUID AggregateClass
);
````


## -parameters

### -param AggregateClass [in]

Identifies the COM server to add.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559717">IKsAggregateControl::KsRemoveAggregate</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksaggregatecontrol.md">IKsAggregateControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAggregateControl::KsAddAggregate method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

