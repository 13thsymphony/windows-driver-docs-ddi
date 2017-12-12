---
UID: NC.pepfx.POFXCALLBACKREQUESTWORKER
title: POFXCALLBACKREQUESTWORKER
author: windows-driver-content
description: The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.
old-location: kernel\requestworker.htm
old-project: kernel
ms.assetid: A77277D2-B644-469D-A668-78C23BF41367
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _VPCI_PNP_ID, *PVPCI_PNP_ID, VPCI_PNP_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RequestWorker
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
req.irql: <= DISPATCH_LEVEL
---

# POFXCALLBACKREQUESTWORKER callback



## -description
The <b>RequestWorker</b> routine is called by a platform extension plug-in (PEP) to inform the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.



## -prototype

````
POFXCALLBACKREQUESTWORKER RequestWorker;

VOID RequestWorker(
  _In_ POHANDLE PluginHandle
)
{ ... }
````


## -parameters

### -param PluginHandle [in]

A POHANDLE value that represents the registration of the device with PoFx. The PEP previously received this handle from PoFx during the <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.


## -returns
None.


## -remarks
This routine is implemented by PoFx and is called by the PEP. The <b>RequestWorker</b> member of the <a href="kernel.pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>RequestWorker</b> routine.

Each time the PEP calls this routine, PoFx responds by sending a <a href="kernel.pep_dpm_work">PEP_DPM_WORK</a> notification to the PEP. This notification might be delayed if a worker thread is not immediately available to process the work request.

A PEP can call this routine at IRQL &lt;= DISPATCH_LEVEL.


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_work">PEP_DPM_WORK</a>
</dt>
<dt>
<a href="kernel.pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKREQUESTWORKER routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

