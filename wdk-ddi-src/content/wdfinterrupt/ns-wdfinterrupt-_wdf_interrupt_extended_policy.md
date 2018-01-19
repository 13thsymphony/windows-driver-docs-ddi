---
UID : NS:wdfinterrupt._WDF_INTERRUPT_EXTENDED_POLICY
title : _WDF_INTERRUPT_EXTENDED_POLICY
author : windows-driver-content
description : The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group.
old-location : wdf\wdf_interrupt_extended_policy.htm
old-project : wdf
ms.assetid : 28cc79e8-7078-4b29-ab2a-2eeca5c5b8b3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY, WDF_INTERRUPT_EXTENDED_POLICY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfinterrupt.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.9
req.umdf-ver : 
req.alt-api : WDF_INTERRUPT_EXTENDED_POLICY
req.alt-loc : wdfinterrupt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Any level
req.typenames : "*PWDF_INTERRUPT_EXTENDED_POLICY, WDF_INTERRUPT_EXTENDED_POLICY"
req.product : Windows 10 or later.
---

# _WDF_INTERRUPT_EXTENDED_POLICY structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure contains information about an interrupt's policy, priority, affinity, and group.

## Syntax
````
typedef struct _WDF_INTERRUPT_EXTENDED_POLICY {
  ULONG                  Size;
  WDF_INTERRUPT_POLICY   Policy;
  WDF_INTERRUPT_PRIORITY Priority;
  GROUP_AFFINITY         TargetProcessorSetAndGroup;
} WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY;
````

## Members

        
            `Policy`

            A <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_policy.md">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.
        
            `Priority`

            A <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_priority.md">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.
        
            `Size`

            The size, in bytes, of this structure.
        
            `TargetProcessorSetAndGroup`

            A GROUP_AFFINITY structure that specifies a processor group and a processor affinity mask within the group, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>. The GROUP_AFFINITY structure is defined in <i>Winnt.h</i>.

    ## Remarks
        The <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure is used as input the <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetextendedpolicy.md">WdfInterruptSetExtendedPolicy</a>. 

To initialize a <b>WDF_INTERRUPT_EXTENDED_POLICY</b> structure, your driver must call <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.9 |
| **Minimum UMDF version** |  |
| **Header** | wdfinterrupt.h (include Wdf.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptsetextendedpolicy.md">WdfInterruptSetExtendedPolicy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_EXTENDED_POLICY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>