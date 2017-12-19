---
UID: NF.portcls.IPinName.GetPinName
title: IPinName::GetPinName method
author: windows-driver-content
description: The GetPinName method retrieves the friendly name of an audio endpoint.
old-location: audio\ipinname_getpinname.htm
old-project: audio
ms.assetid: 97fa159c-ce71-4ce2-8d40-def7671d014c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPinName, IPinName::GetPinName, GetPinName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPinName.GetPinName
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
---

# IPinName::GetPinName method



## -description
The <code>GetPinName</code> method retrieves the friendly name of an audio endpoint.



## -syntax

````
NTSTATUS GetPinName(
  [in]  PIRP     Irp,
  [in]  PKSP_PIN Pin,
  [out] PVOID    Data
);
````


## -parameters

### -param Irp [in]

Specifies a pointer to an I/O request packet (IRP) structure. 


### -param Pin [in]

Specifies a pointer to the underlying kernel streaming (KS) pin.


### -param Data [out]

Specifies a pointer to the buffer that holds the data for the <code>GetPinName</code> method.


## -returns
The <code>GetPinName</code> method returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
If a client needs the current pin name of an endpoint, but has determined that the miniport driver does not support the <code>GetPinName</code> method, the client uses the friendly name of the topology bridge pin. For more information about pin categories and friendly names, see <a href="https://msdn.microsoft.com/fd4a4afd-2c17-4002-87ae-21501b1d75c1">Pin Category Property</a> and <a href="https://msdn.microsoft.com/e0937d20-dd5b-453f-99f6-4e501f0f0e5b">Friendly Names for Audio Endpoint Devices</a>. 

KSNODETYPE_SPEAKER

KSNODETYPE_DESKTOP_SPEAKER

KSNODETYPE_ROOM_SPEAKER

KSNODETYPE_LOW_FREQUENCY_EFFECTS_SPEAKER


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-ipinname.md">IPinName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e0937d20-dd5b-453f-99f6-4e501f0f0e5b">Friendly Names for Audio Endpoint Devices</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fd4a4afd-2c17-4002-87ae-21501b1d75c1">Pin Category Property</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPinName::GetPinName method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

