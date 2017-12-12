---
UID: NN.portcls.IPortClsEtwHelper
title: IPortClsEtwHelper
author: windows-driver-content
description: The IPortClsEtwHelper interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.
old-location: audio\iportclsetwhelper.htm
old-project: audio
ms.assetid: 7BF9E3AB-D508-4FB8-8C47-C0B338933A56
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortClsEtwHelper
req.alt-loc: Portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IPortClsEtwHelper interface



## -description
The <code>IPortClsEtwHelper</code> interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.

The miniport driver uses the information from the helper functions to report glitching errors.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsEtwHelper</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPortClsEtwHelper</b> also has these types of members:

The <b>IPortClsEtwHelper</b> interface has these methods.

The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.

 


## -members
The <b>IPortClsEtwHelper</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="audio.iportclsetwhelper_miniportwriteetwevent">MiniportWriteEtwEvent</a>
</td>
<td align="left" width="63%">
The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.

</td>
</tr>
</table>The <code>MiniportWriteEtwEvent</code> method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/9FF2A5D6-9382-4EE6-AA21-DCF47210F73B">Glitch Reporting for Offloaded Audio</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsEtwHelper interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

