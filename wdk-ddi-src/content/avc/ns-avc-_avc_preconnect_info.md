---
UID: NS.AVC._AVC_PRECONNECT_INFO
title: _AVC_PRECONNECT_INFO
author: windows-driver-content
description: The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device.
old-location: stream\avc_preconnect_info.htm
old-project: stream
ms.assetid: 823713de-16d4-45cd-936e-1af4a8425c94
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _AVC_PRECONNECT_INFO, *PAVC_PRECONNECT_INFO, AVC_PRECONNECT_INFO
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
req.alt-api: AVC_PRECONNECT_INFO
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
---

# _AVC_PRECONNECT_INFO structure



## -description
The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device.



## -syntax

````
typedef struct _AVC_PRECONNECT_INFO {
  ULONG             PinId;
  AVCPRECONNECTINFO ConnectInfo;
} AVC_PRECONNECT_INFO, *PAVC_PRECONNECT_INFO;
````


## -struct-fields

### -field PinId

Specifies the offset (or ID) of the pin for which information is to be retrieved.


### -field ConnectInfo

The AVCPRECONNECTINFO values for the specified pin.


## -remarks
This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> for information about building and sending an AV/C command.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="stream.avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>
</dt>
<dt>
<a href="stream.avc_function">AVC_FUNCTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PRECONNECT_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

