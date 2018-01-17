---
UID: NC:pepfx.POFXCALLBACKPLATFORMIDLEVETO
title: POFXCALLBACKPLATFORMIDLEVETO
author: windows-driver-content
description: The PlatformIdleVeto routine increments or decrements the veto count for a veto code for a platform idle state.
old-location: kernel\platformidleveto.htm
old-project: kernel
ms.assetid: 61D637E6-316D-49A5-B1B1-C89415C7D0B8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEPCALLBACKPOWERONCRASHDUMPDEVICE
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
req.alt-api: PlatformIdleVeto
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
req.typenames: *PVPCI_PNP_ID, VPCI_PNP_ID
---

# POFXCALLBACKPLATFORMIDLEVETO callback



## -description
The <b>PlatformIdleVeto</b> routine increments or decrements the veto count for a veto code for a platform idle state.



## -prototype

````
POFXCALLBACKPLATFORMIDLEVETO PlatformIdleVeto;

NTSTATUS PlatformIdleVeto(
  _In_ POHANDLE ProcessorHandle,
  _In_ ULONG    PlatformState,
  _In_ ULONG    VetoReason,
  _In_ BOOLEAN  Increment
)
{ ... }
````


## -parameters

### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param PlatformState [in]

The index of the platform idle state whose veto count is being incremented or decremented. The PEP previously specified the supported platform idle states in response to a <a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified N platform idle states, valid platform idle state indexes range from 0 to N–1.


### -param VetoReason [in]

A PEP-defined veto code that indicates why the platform idle state cannot be entered. The PEP previously specified the number of supported veto reasons in response to a <a href="kernel.pep_notify_ppm_query_veto_reasons">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification. If the PEP specified M veto reasons, valid veto codes range from 1 to M.


### -param Increment [in]

Whether to increment or decrement the veto count. Set to TRUE to increment the veto count for this veto reason, or to FALSE to decrement the count.


## -returns
<b>PlatformIdleVeto</b> returns STATUS_SUCCESS if the call successfully increments or decrements the veto count. Possible error return values include the following status code.
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>Indicates that the <b>PlatformIdleVeto</b> routine is not implemented for this processor.

 


## -remarks
This routine is implemented by the PoFx and is called by the PEP. The <b>PlatformIdleVeto</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to a <b>PlatformIdleVeto</b> routine.

After the PEP handles the <a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification, each platform idle state starts with a veto count of zero for all veto codes. The PEP can increment the veto count of a veto code to prevent the operating system from transitioning the platform to this idle state. The PEP decrements the veto count when the veto reason that caused the count to be incremented is no longer in effect. Only after the count for all veto codes has decremented to zero is the operating system allowed to transition the platform to this idle state.

This routine must be called at IRQL = PASSIVE_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_veto_reasons">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKPLATFORMIDLEVETO routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

