---
UID: NS.avc._AVC_SETCONNECT_INFO
title: AVC_SETCONNECT_INFO
author: windows-driver-content
description: The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avc_setconnect_info.htm
old-project: stream
ms.assetid: 16672908-6f1f-471b-b82e-d548e3efeb20
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: AVC_SETCONNECT_INFO, AVC_SETCONNECT_INFO, *PAVC_SETCONNECT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_SETCONNECT_INFO
req.alt-loc: avc.h
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
req.iface: 
---

# AVC_SETCONNECT_INFO structure



## -description
<p>The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.</p>


## -syntax

````
typedef struct _AVC_SETCONNECT_INFO {
  ULONG          PinId;
  AVCCONNECTINFO ConnectInfo;
} AVC_SETCONNECT_INFO, *PAVC_SETCONNECT_INFO;
````


## -struct-fields
<dl>

### -field <b>PinId</b>

<dd>
<p>Specifies the offset (or ID) of the pin for which information is to be set.</p>
</dd>

### -field <b>ConnectInfo</b>

<dd>
<p>The AVCCONNECTINFO values for the specified pin.</p>
</dd>
</dl>

## -remarks
<p>This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a> function code.</p>

<p>This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.</p>

<p>See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554177">AVC_MULTIFUNC_IRB</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554145">AVC_FUNCTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_SETCONNECT_INFO structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
