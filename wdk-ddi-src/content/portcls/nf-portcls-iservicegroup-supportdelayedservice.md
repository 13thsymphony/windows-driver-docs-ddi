---
UID: NF.portcls.IServiceGroup.SupportDelayedService
title: IServiceGroup::SupportDelayedService method
author: windows-driver-content
description: The SupportDelayedService method indicates that the service group should prepare to support delayed service.
old-location: audio\iservicegroup_supportdelayedservice.htm
old-project: audio
ms.assetid: ca9fc65f-299d-4d23-b98e-471daf07f413
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IServiceGroup, IServiceGroup::SupportDelayedService, SupportDelayedService
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IServiceGroup.SupportDelayedService
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# IServiceGroup::SupportDelayedService method



## -description
The <code>SupportDelayedService</code> method indicates that the service group should prepare to support delayed service.



## -syntax

````
VOID SupportDelayedService(
    None
);
````


## -parameters

### -param None 


## -returns
None


## -remarks
The <code>SupportDelayedService</code> method initializes the notification timer that is used for delayed service. Call this method once before making any calls to <a href="audio.iservicegroup_requestdelayedservice">IServiceGroup::RequestDelayedService</a>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>
</dt>
<dt>
<a href="audio.iservicegroup_requestdelayedservice">IServiceGroup::RequestDelayedService</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IServiceGroup::SupportDelayedService method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

