---
UID: NC.netdispumdddi.PFN_START_MIRACAST_SESSION
title: PFN_START_MIRACAST_SESSION
author: windows-driver-content
description: Called by the operating system to start a Miracast connected session.
old-location: display\startmiracastsession.htm
ms.assetid: 2778d9d0-7f97-416f-a5ae-3754b17e8a29
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StartMiracastSession
req.alt-loc: Netdispumdddi.h
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
ms.keywords: NDK_SRQ, NDK_SRQ
req.iface: 
---

# PFN_START_MIRACAST_SESSION callback



## -description
<p>Called by the operating system to start a Miracast connected session.</p>


## -prototype

````
PFN_START_MIRACAST_SESSION StartMiracastSession;

NTSTATUS StartMiracastSession(
  _In_  PVOID                         pMiracastContext,
  _In_  SOCKET                        MiracastRTSPSocket,
  _In_  MIRACAST_WFD_CONNECTION_STATS *pWfdConnectionStats,
  _Out_ MIRACAST_SESSION_INFO         *pSessionInfo
)
{ ... }
````


## -parameters
<dl>

### -param <i>pMiracastContext</i> [in]

<dd>
<p>A pointer to a context associated with a display adapter.</p>
<p>The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.</p>
</dd>

### -param <i>MiracastRTSPSocket</i> [in]

<dd>
<p>The operating system-supplied network socket handle of the Real Time Streaming Protocol (RTSP). </p>
<div class="alert"><b>Note</b>  The Miracast user-mode driver should not close this socket. When the <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> function is called, the operating system will close this socket.</div>
<div> </div>
</dd>

### -param <i>pWfdConnectionStats</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a> structure that indicates the Wi-Fi Direct connection statistics.</p>
</dd>

### -param <i>pSessionInfo</i> [out]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a> structure that the Miracast user-mode driver should complete after it has obtained the capabilities of the Miracast sink.</p>
</dd>
</dl>

## -returns
<p>On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header, including the following:</p><dl>
<dt><b>STATUS_DEVICE_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>The current suggested encode rate cannot sustain a Miracast sink that supports more than 1024 x 768 pixels.</p>

<p> </p>

## -remarks
<p>When this function is called, the Miracast user-mode driver should start communicating with the Miracast sink using the Miracast protocol. The driver should  gather the capabilities of the sink and the attributes of the monitor that's connected to the sink.  The driver should perform enough of the negotiation with the sink to determine whether a monitor is connected to the sink or not. If the driver determines that a monitor is connected to the sink, it should also determine whether the current suggested bit rate is high enough to at least support the lowest sink supported mode of 1024 x 768 pixels.</p>

<p>The driver should also set the value of these members of <a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a> pointed to by <i>pSessionInfo</i> in these cases:</p>

<p></p><dl>
<dt><a id="MonitorConnected"></a><a id="monitorconnected"></a><a id="MONITORCONNECTED"></a><b>MonitorConnected</b></dt>
<dd>
<p>The driver should set this member to indicate that the sink reported that a monitor connected to the sink during an M3 message exchange.</p>
</dd>
<dt><a id="ReducedModeListDueToBandwidth"></a><a id="reducedmodelistduetobandwidth"></a><a id="REDUCEDMODELISTDUETOBANDWIDTH"></a><b>ReducedModeListDueToBandwidth</b></dt>
<dd>
<p> The driver should set this member to indicate that the driver will reduce the modes exposed to the operating system based on the current suggested encode rate.
In the case that a monitor is connected to the sink, the driver should return from <i>StartMiracastSession</i> before it calls the display miniport driver to send a monitor hot-plug detection (HPD) awareness value. This procedure should avoid any deadlocks that could arise due to messages from kernel- to user-mode not being delivered while this thread is in the control of the user-mode function.</p>
</dd>
</dl><p>The driver should set this member to indicate that the sink reported that a monitor connected to the sink during an M3 message exchange.</p>

<p> The driver should set this member to indicate that the driver will reduce the modes exposed to the operating system based on the current suggested encode rate.
In the case that a monitor is connected to the sink, the driver should return from <i>StartMiracastSession</i> before it calls the display miniport driver to send a monitor hot-plug detection (HPD) awareness value. This procedure should avoid any deadlocks that could arise due to messages from kernel- to user-mode not being delivered while this thread is in the control of the user-mode function.</p>

<p>The operating system guarantees that only one of the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <i>StartMiracastSession</i>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions is called at a time.</p>

<p>When this function is called, the Miracast user-mode driver should start communicating with the Miracast sink using the Miracast protocol. The driver should  gather the capabilities of the sink and the attributes of the monitor that's connected to the sink.  The driver should perform enough of the negotiation with the sink to determine whether a monitor is connected to the sink or not. If the driver determines that a monitor is connected to the sink, it should also determine whether the current suggested bit rate is high enough to at least support the lowest sink supported mode of 1024 x 768 pixels.</p>

<p>The driver should also set the value of these members of <a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a> pointed to by <i>pSessionInfo</i> in these cases:</p>

<p></p><dl>
<dt><a id="MonitorConnected"></a><a id="monitorconnected"></a><a id="MONITORCONNECTED"></a><b>MonitorConnected</b></dt>
<dd>
<p>The driver should set this member to indicate that the sink reported that a monitor connected to the sink during an M3 message exchange.</p>
</dd>
<dt><a id="ReducedModeListDueToBandwidth"></a><a id="reducedmodelistduetobandwidth"></a><a id="REDUCEDMODELISTDUETOBANDWIDTH"></a><b>ReducedModeListDueToBandwidth</b></dt>
<dd>
<p> The driver should set this member to indicate that the driver will reduce the modes exposed to the operating system based on the current suggested encode rate.
In the case that a monitor is connected to the sink, the driver should return from <i>StartMiracastSession</i> before it calls the display miniport driver to send a monitor hot-plug detection (HPD) awareness value. This procedure should avoid any deadlocks that could arise due to messages from kernel- to user-mode not being delivered while this thread is in the control of the user-mode function.</p>
</dd>
</dl><p>The driver should set this member to indicate that the sink reported that a monitor connected to the sink during an M3 message exchange.</p>

<p> The driver should set this member to indicate that the driver will reduce the modes exposed to the operating system based on the current suggested encode rate.
In the case that a monitor is connected to the sink, the driver should return from <i>StartMiracastSession</i> before it calls the display miniport driver to send a monitor hot-plug detection (HPD) awareness value. This procedure should avoid any deadlocks that could arise due to messages from kernel- to user-mode not being delivered while this thread is in the control of the user-mode function.</p>

<p>The operating system guarantees that only one of the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <i>StartMiracastSession</i>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions is called at a time.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_START_MIRACAST_SESSION callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
