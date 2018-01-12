---
UID: NF:ks.KsPinAcquireControl
title: KsPinAcquireControl function
author: windows-driver-content
description: The KsPinAcquireControl function acquires the control mutex for the AVStream pin specified by Pin.
old-location: stream\kspinacquirecontrol.htm
old-project: stream
ms.assetid: 05ff1829-8305-4bc4-be22-233d391a5dc0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinAcquireControl
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
req.alt-api: KsPinAcquireControl
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
req.typenames: 
---

# KsPinAcquireControl function



## -description
The<b> KsPinAcquireControl</b> function acquires the control mutex for the AVStream pin specified by <i>Pin</i>.



## -syntax

````
void __inline KsPinAcquireControl(
  _In_ PKSPIN Pin
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> for which to acquire the control mutex.


## -returns
None


## -remarks
The pin control mutex is the same mutex that is used by <i>Pin</i>'s parent. This means that the mutex for <i>Pin</i> is also a filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

<b>KsPinAcquireControl</b> is an inline call to <a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a> with the appropriate typecasting. Minidrivers manipulating pins should call <b>KsPinAcquireControl</b> instead of calling <b>KsAcquireControl</b> directly.


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
<a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspinreleasecontrol.md">KsPinReleaseControl</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksreleasecontrol.md">KsReleaseControl</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinAcquireControl function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

