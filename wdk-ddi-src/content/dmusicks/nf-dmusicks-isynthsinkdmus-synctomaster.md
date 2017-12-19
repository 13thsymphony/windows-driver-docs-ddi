---
UID: NF.dmusicks.ISynthSinkDMus.SyncToMaster
title: ISynthSinkDMus::SyncToMaster method
author: windows-driver-content
description: The SyncToMaster method allows synchronization to the master clock in order to avoid drift.
old-location: audio\isynthsinkdmus_synctomaster.htm
old-project: audio
ms.assetid: 5009e4d8-5299-4eeb-a70d-5be87694b1d0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISynthSinkDMus, ISynthSinkDMus::SyncToMaster, SyncToMaster
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISynthSinkDMus.SyncToMaster
req.alt-loc: dmusicks.h
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
---

# ISynthSinkDMus::SyncToMaster method



## -description
The <code>SyncToMaster</code> method allows synchronization to the master clock in order to avoid drift.



## -syntax

````
NTSTATUS SyncToMaster(
  [in] REFERENCE_TIME rtTime,
  [in] BOOL           fStart
);
````


## -parameters

### -param rtTime [in]

Specifies the reference time from the master clock. Reference time is measured in 100-nanosecond units.


### -param fStart [in]

Specifies whether the sample clock is to be reset to zero with this reference time. If <b>TRUE</b>, the sample clock must be reset to zero at time <i>rtTime</i>. If <b>FALSE</b>, the sample clock is not reset.


## -returns
<code>SyncToMaster</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
Because the master time and sample time might be driven by different crystals, they can drift apart. The port driver periodically calls this method to give the miniport driver an opportunity to synchronize its sample clock to the master clock.

Parameter <i>fStart</i> is <b>TRUE</b> during the first call to <code>SyncToMaster</code> after the stream enters the KSSTATE_RUN state (see <a href="stream.ksstate">KSSTATE</a>). Otherwise, <i>fStart</i> is <b>FALSE</b>.


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
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-isynthsinkdmus.md">ISynthSinkDMus</a>
</dt>
<dt>
<a href="stream.ksstate">KSSTATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20ISynthSinkDMus::SyncToMaster method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

