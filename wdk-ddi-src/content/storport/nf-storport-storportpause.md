---
UID: NF.storport.StorPortPause
title: StorPortPause
author: windows-driver-content
description: The StorPortPause routine pauses an adapter for the specified period of time.
old-location: storage\storportpause.htm
old-project: storage
ms.assetid: 304df6fb-8586-454a-a89a-24ac8848d3a1
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortPause
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortPause
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# StorPortPause function



## -description
<p>The <b>StorPortPause</b> routine pauses an adapter for the specified period of time. </p>


## -syntax

````
STORPORT_API BOOLEAN StorPortPause(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG TimeOut
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>Pointer to the hardware device extension of the adapter to pause. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device.</p>
</dd>

### -param <i>TimeOut</i> [in]

<dd>
<p>Specifies the interval of time, in seconds, that the adapter is to be paused. </p>
</dd>
</dl>

## -returns
<p><b>StorPortPause</b> returns <b>TRUE</b> if the miniport driver succeeded in pausing the adapter, <b>FALSE</b> if not. </p>

## -remarks
<p>All requests to the adapter are held until the time-out expires or the device resumes. All requests to all targets attached to the adapter will be held until the adapter is resumed or the time-out expires.</p>

<p>All requests to the adapter are held until the time-out expires or the device resumes. All requests to all targets attached to the adapter will be held until the adapter is resumed or the time-out expires.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567499">StorPortResume</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPause routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
