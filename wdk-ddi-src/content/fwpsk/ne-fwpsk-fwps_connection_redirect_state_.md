---
UID: NE.fwpsk.FWPS_CONNECTION_REDIRECT_STATE_
title: FWPS_CONNECTION_REDIRECT_STATE_
author: windows-driver-content
description: The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.
old-location: netvista\fwps_connection_redirect_state.htm
old-project: netvista
ms.assetid: f4fe8136-8a7c-499a-9f2c-1367138e5f30
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FWPS_CONNECTION_REDIRECT_STATE_, FWPS_CONNECTION_REDIRECT_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_CONNECTION_REDIRECT_STATE
req.alt-loc: fwpsk.h
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
---

# FWPS_CONNECTION_REDIRECT_STATE_ enumeration



## -description
The FWPS_CONNECTION_REDIRECT_STATE enumeration type specifies the current redirection state of a connection.


## -syntax

````
typedef enum FWPS_CONNECTION_REDIRECT_STATE_ { 
  FWPS_CONNECTION_NOT_REDIRECTED,
  FWPS_CONNECTION_REDIRECTED_BY_SELF,
  FWPS_CONNECTION_REDIRECTED_BY_OTHER,
  FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF,
  FWPS_CONNECTION_REDIRECT_STATE_MAX
} FWPS_CONNECTION_REDIRECT_STATE;
````


## -enum-fields

### -field FWPS_CONNECTION_NOT_REDIRECTED

The connection was not redirected.

### -field FWPS_CONNECTION_REDIRECTED_BY_SELF

The connection was redirected by the calling redirect handle.

### -field FWPS_CONNECTION_REDIRECTED_BY_OTHER

The connection was redirected by a different redirect handle.

### -field FWPS_CONNECTION_PREVIOUSLY_REDIRECTED_BY_SELF

The connection was redirected by the calling redirect handle but later redirected again by a different redirect handle.

### -field FWPS_CONNECTION_REDIRECT_STATE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.

## -remarks
The FWPS_CONNECTION_REDIRECT_STATE enumeration is the return type for a call to the <a href="netvista.fwpsqueryconnectionredirectstate0">FwpsQueryConnectionRedirectState0</a>  function.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.fwpsqueryconnectionredirectstate0">FwpsQueryConnectionRedirectState0</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CONNECTION_REDIRECT_STATE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
