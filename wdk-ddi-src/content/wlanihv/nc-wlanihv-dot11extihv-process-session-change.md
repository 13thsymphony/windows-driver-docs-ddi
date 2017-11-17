---
UID: NC.wlanihv.DOT11EXTIHV_PROCESS_SESSION_CHANGE
title: DOT11EXTIHV_PROCESS_SESSION_CHANGE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvprocesssessionchange.htm
ms.assetid: 17d5ab30-141a-4b7b-93f1-113fb1a39ba6
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvProcessSessionChange
req.alt-loc: wlanihv.h
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
ms.keywords: PrintPropertyValue, PrintPropertyValue
req.iface: 
req.product: Windows 10 or later.
---

# DOT11EXTIHV_PROCESS_SESSION_CHANGE callback



## -description

## -prototype

````
DOT11EXTIHV_PROCESS_SESSION_CHANGE Dot11ExtIhvProcessSessionChange;

DWORD APIENTRY Dot11ExtIhvProcessSessionChange(
  _In_ ULONG                    uEventType,
  _In_ PWTSSESSION_NOTIFICATION pSessionNotification
)
{ ... }
````


## -parameters
<dl>

### -param <i>uEventType</i> [in]

<dd>
<p>The type of event. This parameter can have one of the following values.
     </p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>WTS_CONSOLE_CONNECT</p>
</td>
<td>
<p>A session was connected to the console session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_CONSOLE_DISCONNECT</p>
</td>
<td>
<p>A session was disconnected from the console session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_REMOTE_CONNECT</p>
</td>
<td>
<p>A session was connected to the remote session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_REMOTE_DISCONNECT</p>
</td>
<td>
<p>A session was disconnected from the remote session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_SESSION_LOGON</p>
</td>
<td>
<p>A user has logged on to the session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_SESSION_LOGOFF</p>
</td>
<td>
<p>A user has logged off of the session.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_SESSION_LOCK</p>
</td>
<td>
<p>A session has been locked.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_SESSION_UNLOCK</p>
</td>
<td>
<p>A session has been unlocked.</p>
</td>
</tr>
<tr>
<td>
<p>WTS_SESSION_REMOTE_CONTROL</p>
</td>
<td>
<p>A session has changed its remote controlled status. To determine the status, call the 
        <b>GetSystemMetrics</b> function and check the SM_REMOTECONTROL metric. For more information about
        this function, refer to the Microsoft Windows SDK documentation.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>pSessionNotification</i> [in]

<dd>
<p>A pointer to a WTSSESSION_NOTIFICATION structure, which provides information about the session
     change notification. For more information about this structure, refer to the Windows SDK
     documentation.</p>
</dd>
</dl>

## -returns
<p>If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.</p>

## -remarks
<p>The operating system calls the function to notify the IHV Extensions DLL whenever a switch in a user
    session occurs.</p>

<p>If the 
    <i>uEventType</i> parameter is set to WTS_SESSION_LOGOFF, the IHV Extensions DLL must cancel all pending
    user interface requests internally and must release any allocated resources for the user interface
    requests.</p>

<p>The operating system calls the function to notify the IHV Extensions DLL whenever a switch in a user
    session occurs.</p>

<p>If the 
    <i>uEventType</i> parameter is set to WTS_SESSION_LOGOFF, the IHV Extensions DLL must cancel all pending
    user interface requests internally and must release any allocated resources for the user interface
    requests.</p>

## -requirements
<table>
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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wlanihv.h (include Wlanihv.h)</dt>
</dl>
</td>
</tr>
</table>