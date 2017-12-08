---
UID: NS.PEPFX._PEP_REGISTER_DEBUGGER
title: _PEP_REGISTER_DEBUGGER
author: windows-driver-content
description: The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport.
old-location: kernel\pep_register_debugger.htm
old-project: kernel
ms.assetid: 3B0240AB-4599-4F21-8CBB-14A4A60D3EFD
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_REGISTER_DEBUGGER
req.alt-loc: pepfx.h
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
---

# _PEP_REGISTER_DEBUGGER structure



## -description
The <b>PEP_REGISTER_DEBUGGER</b> structure identifies a registered device that is a core system resource that provides debugger transport.


## -syntax

````
typedef struct _PEP_REGISTER_DEBUGGER {
  PEPHANDLE DeviceHandle;
} PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER;
````


## -struct-fields

### -field DeviceHandle

[in] A <b>PEPHANDLE</b> value that identifies the device. The PEP supplied this handle in response to a previous <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification.

## -remarks
This structure is used by the <a href="kernel.pep_dpm_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx).

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 10.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a>
</dt>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REGISTER_DEBUGGER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
