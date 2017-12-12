---
UID: NF.ks.KsPinReleaseControl
title: KsPinReleaseControl function
author: windows-driver-content
description: The KsPinReleaseControl function releases the control mutex for the AVStream pin specified by Pin.
old-location: stream\kspinreleasecontrol.htm
old-project: stream
ms.assetid: ead50a69-fe33-4e6c-84f9-98491d188140
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsPinReleaseControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsPinReleaseControl
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsPinReleaseControl function



## -description
The<b> KsPinReleaseControl </b>function releases the control mutex for the AVStream pin specified by <i>Pin</i>.



## -syntax

````
void __inline KsPinReleaseControl(
  _In_ PKSPIN Pin
);
````


## -parameters

### -param Pin [in]

A pointer to a <a href="stream.kspin">KSPIN</a> structure representing the pin for which to release the control mutex.


## -returns
None


## -remarks
The pin control mutex is the same mutex that is used by <i>Pin</i>'s parent. In other words, the pin control mutex <i>is</i> the filter control mutex of <i>Pin</i>'s parent. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Note that this function is an inline call to <a href="stream.ksreleasecontrol">KsReleaseControl</a>. Minidrivers manipulating a pin should call this function instead of calling <b>KsReleaseControl</b> directly. 


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
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
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
<a href="stream.ksreleasecontrol">KsReleaseControl</a>
</dt>
<dt>
<a href="stream.kspinacquirecontrol">KsPinAcquireControl</a>
</dt>
<dt>
<a href="stream.ksacquirecontrol">KsAcquireControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinReleaseControl function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

