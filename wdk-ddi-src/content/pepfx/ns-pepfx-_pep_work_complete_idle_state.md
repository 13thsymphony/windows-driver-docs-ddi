---
UID: NS.PEPFX._PEP_WORK_COMPLETE_IDLE_STATE
title: _PEP_WORK_COMPLETE_IDLE_STATE
author: windows-driver-content
description: The PEP_WORK_COMPLETE_IDLE_STATE structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new Fx power state.
old-location: kernel\pep_work_complete_idle_state.htm
old-project: kernel
ms.assetid: 6065A77F-5E80-4D3D-8EF1-4D336505122A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_WORK_COMPLETE_IDLE_STATE, *PPEP_WORK_COMPLETE_IDLE_STATE, PEP_WORK_COMPLETE_IDLE_STATE
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
req.alt-api: PEP_WORK_COMPLETE_IDLE_STATE
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

# _PEP_WORK_COMPLETE_IDLE_STATE structure



## -description
The <b>PEP_WORK_COMPLETE_IDLE_STATE</b> structure identifies a component that the platform extension plug-in (PEP) has prepared for a transition to a new F<i>x</i> power state.


## -syntax

````
typedef struct _PEP_WORK_COMPLETE_IDLE_STATE {
  POHANDLE DeviceHandle;
  ULONG    Component;
} PEP_WORK_COMPLETE_IDLE_STATE, *PPEP_WORK_COMPLETE_IDLE_STATE;
````


## -struct-fields

### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.

### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="kernel.pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

## -remarks
The <b>CompleteIdleState</b> member of the <a href="kernel.pep_work_information">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_COMPLETE_IDLE_STATE</b> structure.

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
<a href="kernel.pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>
</dt>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="kernel.pep_work_information">PEP_WORK_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_WORK_COMPLETE_IDLE_STATE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
