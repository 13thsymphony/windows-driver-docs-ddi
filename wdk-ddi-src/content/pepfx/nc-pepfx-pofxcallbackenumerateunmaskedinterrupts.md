---
UID : NC:pepfx.POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS
title : POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS
author : windows-driver-content
description : The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled.
old-location : kernel\enumerateunmaskedinterrupts.htm
old-project : kernel
ms.assetid : 8B3E8FE0-9A96-43CD-8C6D-28F302BDF2D7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _VPCI_PNP_ID, VPCI_PNP_ID, *PVPCI_PNP_ID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : EnumerateUnmaskedInterrupts
req.alt-loc : pepfx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= HIGH_LEVEL
req.typenames : VPCI_PNP_ID, *PVPCI_PNP_ID
---


# POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS callback function
The <b>EnumerateUnmaskedInterrupts</b> routine enumerates interrupt sources whose interrupts are unmasked and enabled.

## Syntax

```
POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS Pofxcallbackenumerateunmaskedinterrupts;

NTSTATUS Pofxcallbackenumerateunmaskedinterrupts(
  POHANDLE PluginHandle,
  ULONG EnumerateFlags,
  PPO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK Callback,
  PVOID CallbackContext,
  PPEP_UNMASKED_INTERRUPT_INFORMATION InterruptInformation
)
{...}
```

## Parameters

`PluginHandle`

A POHANDLE value. If non-NULL, this parameter is a handle that identifies the platform extension plug-in (PEP), in which case <b>EnumerateUnmaskedInterrupts</b> enumerates only interrupts that are managed by this PEP. If this parameter is NULL, <b>EnumerateUnmaskedInterrupts</b> enumerates <i>all</i> interrupts in the hardware platform that are unmasked and enabled.

`EnumerateFlags`

No flags are currently defined. Set this parameter to PEP_ENUMERATE_UNMASKED_INTERRUPT_FLAGS_NONE (0x0).

`Callback`

A pointer to a caller-implemented <a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a> callback routine. This callback routine is called once for each interrupt source whose interrupt is unmasked. These callbacks occur synchronously before the <b>EnumerateUnmaskedInterrupts</b> routine returns.

`CallbackContext`

A pointer to a callback context. This pointer is passed as a parameter to the <i>EnumerateInterruptSource</i> callback routine pointed to by the <i>Callback</i> parameter. The contents of the callback context are PEP-defined, and are opaque to the <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

`InterruptInformation`

A pointer to a caller-allocated buffer whose size is at least <b>sizeof</b>(<a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a>) bytes. <b>EnumerateUnmaskedInterrupts</b> will use this buffer to transfer interrupt information to the PEP during calls to the PEP's <i>EnumerateInterruptSource</i> callback routine.


## Return Value

<b>EnumerateUnmaskedInterrupts</b> returns STATUS_SUCCESS if the call successfully enumerates the interrupts. Possible error return values include the following status code.
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>The <b>Size</b> or <b>Version</b> member of the <b>PEP_UNMASKED_INTERRUPT_INFORMATION</b> structure contains an invalid value.

## Remarks

This routine is implemented by PoFx and is called by the PEP. The <b>EnumerateUnmaskedInterrupts</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>EnumerateUnmaskedInterrupts</b> routine.

Before the platform enters a system power state in which the interrupt controllers are power-gated, the PEP can call <b>EnumerateUnmaskedInterrupts</b> to get the information it needs to properly configure wake-up controllers for interrupts that are to remain unmasked.

The PEP can call this routine at IRQL &lt;= HIGH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |
| **Library** |  |
| **IRQL** | <= HIGH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_unmasked_interrupt_information.md">PEP_UNMASKED_INTERRUPT_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>