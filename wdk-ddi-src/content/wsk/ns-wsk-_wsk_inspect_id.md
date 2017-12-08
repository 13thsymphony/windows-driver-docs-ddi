---
UID: NS.WSK._WSK_INSPECT_ID
title: _WSK_INSPECT_ID
author: windows-driver-content
description: The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a listening socket.
old-location: netvista\wsk_inspect_id.htm
old-project: netvista
ms.assetid: 54578dc5-a88f-4649-adbd-6a5e1e31e7b3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WSK_INSPECT_ID, *PWSK_INSPECT_ID, WSK_INSPECT_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_INSPECT_ID
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _WSK_INSPECT_ID structure



## -description
The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a
  listening socket.


## -syntax

````
typedef struct _WSK_INSPECT_ID {
  ULONG_PTR Key;
  ULONG     SerialNumber;
} WSK_INSPECT_ID, *PWSK_INSPECT_ID;
````


## -struct-fields

### -field Key

A key that is assigned to the incoming connection request.

### -field SerialNumber

A serial number that is assigned to the incoming connection request.

## -remarks
The WSK subsystem passes a pointer to a WSK_INSPECT_ID structure to a WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a> event callback function
    whenever an incoming connection request arrives on a listening socket that has conditional accept mode
    enabled. The contents of the WSK_INSPECT_ID structure uniquely identify the incoming connection
    request.

If the WSK application returns 
    <b>WskInspectPend</b> from a call to its 
    <i>WskInspectEvent</i> event callback function, the application must first copy the 
    <u>contents</u> of the WSK_INSPECT_ID structure that is provided by the WSK subsystem into its own
    WSK_INSPECT_ID structure. The WSK application then passes a pointer to its WSK_INSPECT_ID structure to
    the 
    <a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a> function when it
    completes the inspection.

If the incoming connection request is dropped by the remote system while an inspect operation is
    pending, the WSK subsystem calls the WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a> event callback function with a
    pointer to a WSK_INSPECT_ID structure that identifies the dropped request. The WSK application uses the
    contents of this WSK_INSPECT_ID structure to determine which inspection of an incoming connection request
    should be terminated. The WSK application should compare the contents of the WSK_INSPECT_ID structures to
    check for a match. The actual values of the structure members are irrelevant.

A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="netvista.listening_for_and_accepting_incoming_connections">Listening for and
    Accepting Incoming Connections</a>.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_INSPECT_ID structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
