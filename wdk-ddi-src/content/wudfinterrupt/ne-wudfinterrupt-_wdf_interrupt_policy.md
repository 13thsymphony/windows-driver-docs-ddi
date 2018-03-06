---
UID: NE:wudfinterrupt._WDF_INTERRUPT_POLICY
title: "_WDF_INTERRUPT_POLICY"
author: windows-driver-content
description: The WDF_INTERRUPT_POLICY enumeration type identifies the affinity policies that the Plug and Play (PnP) manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.
old-location: wdf\wdf_interrupt_policy_umdf.htm
old-project: wdf
ms.assetid: 92E2A992-8A0B-4E0F-B615-DC6E30E4A227
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_INTERRUPT_POLICY, PWDF_INTERRUPT_POLICY, PWDF_INTERRUPT_POLICY enumeration pointer, WDF_INTERRUPT_POLICY, WDF_INTERRUPT_POLICY enumeration, WdfIrqPolicyAllCloseProcessors, WdfIrqPolicyAllProcessorsInMachine, WdfIrqPolicyMachineDefault, WdfIrqPolicyOneCloseProcessor, WdfIrqPolicySpecifiedProcessors, WdfIrqPolicySpreadMessagesAcrossAllProcessors, _WDF_INTERRUPT_POLICY, umdf.wdf_interrupt_policy, wdf.wdf_interrupt_policy_umdf, wudfinterrupt/PWDF_INTERRUPT_POLICY, wudfinterrupt/WDF_INTERRUPT_POLICY, wudfinterrupt/WdfIrqPolicyAllCloseProcessors, wudfinterrupt/WdfIrqPolicyAllProcessorsInMachine, wudfinterrupt/WdfIrqPolicyMachineDefault, wudfinterrupt/WdfIrqPolicyOneCloseProcessor, wudfinterrupt/WdfIrqPolicySpecifiedProcessors, wudfinterrupt/WdfIrqPolicySpreadMessagesAcrossAllProcessors"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfinterrupt.h
api_name:
-	WDF_INTERRUPT_POLICY
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_POLICY Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_policy.md">WDF_INTERRUPT_POLICY</a> enumeration type identifies the affinity policies that the Plug and Play (PnP) manager can use when it assigns a device's interrupts to the processors of a multiprocessor system.

## Syntax
````
typedef enum _WDF_INTERRUPT_POLICY { 
  WdfIrqPolicyMachineDefault                     = 0,
  WdfIrqPolicyAllCloseProcessors                 = 1,
  WdfIrqPolicyOneCloseProcessor                  = 2,
  WdfIrqPolicyAllProcessorsInMachine             = 3,
  WdfIrqPolicySpecifiedProcessors                = 4,
  WdfIrqPolicySpreadMessagesAcrossAllProcessors  = 5
} WDF_INTERRUPT_POLICY, *PWDF_INTERRUPT_POLICY;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIrqPolicyAllCloseProcessors</td>
                    <td>For NUMA systems, the PnP manager should assign the device's interrupts to processors that are close to the device. For non-NUMA systems, specifying <b>WdfIrqPolicyAllCloseProcessors</b> is the same as specifying <b>WdfIrqPolicyAllProcessorsInMachine</b>.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPolicyAllProcessorsInMachine</td>
                    <td>The PnP manager can assign a device's interrupts to any of the system's processors.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPolicyMachineDefault</td>
                    <td>Use the system's default affinity policy.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPolicyOneCloseProcessor</td>
                    <td>For NUMA systems, the PnP manager should assign one interrupt to a processor that is close to the device. For non-NUMA systems, the PnP manager can assign the interrupt to any processor.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPolicySpecifiedProcessors</td>
                    <td>The PnP manager should assign the device's interrupts only to specified processors.</td>
                </tr>
            
                <tr>
                    <td>WdfIrqPolicySpreadMessagesAcrossAllProcessors</td>
                    <td>The PnP manager should assign different message-based interrupts to different processors, if possible.</td>
                </tr>
</table>

## Remarks

The <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_policy.md">WDF_INTERRUPT_POLICY</a> enumeration type is used as input to the <a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfinterrupt.h |

## See Also

<a href="https://msdn.microsoft.com/EDBCBB37-41A4-4234-BE8C-4C8739BC287B">IWDFInterrupt::SetPolicy</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_POLICY enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>