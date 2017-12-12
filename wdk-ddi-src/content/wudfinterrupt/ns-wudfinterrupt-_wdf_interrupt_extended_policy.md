---
UID: NS.WUDFINTERRUPT._WDF_INTERRUPT_EXTENDED_POLICY
title: _WDF_INTERRUPT_EXTENDED_POLICY
author: windows-driver-content
description: The WDF_INTERRUPT_EXTENDED_POLICY structure contains information about an interrupt's policy, priority, affinity, and group.
old-location: wdf\wdf_interrupt_extended_policy_umdf.htm
old-project: wdf
ms.assetid: CD11AD87-D3F1-41E5-AE86-DC289504EF6D
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY, WDF_INTERRUPT_EXTENDED_POLICY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: WDF_INTERRUPT_EXTENDED_POLICY
req.alt-loc: Wudfinterrupt.h
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
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_EXTENDED_POLICY structure



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="wdf.wdf_interrupt_extended_policy">WDF_INTERRUPT_EXTENDED_POLICY</a> structure contains information about an interrupt's policy, priority, affinity, and group.



## -syntax

````
typedef struct _WDF_INTERRUPT_EXTENDED_POLICY {
  ULONG                  Size;
  WDF_INTERRUPT_POLICY   Policy;
  WDF_INTERRUPT_PRIORITY Priority;
  GROUP_AFFINITY         TargetProcessorSetAndGroup;
} WDF_INTERRUPT_EXTENDED_POLICY, *PWDF_INTERRUPT_EXTENDED_POLICY;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Policy

A <a href="wdf.wdf_interrupt_policy">WDF_INTERRUPT_POLICY</a>-typed enumerator that specifies a processor affinity policy for the interrupt.


### -field Priority

A <a href="wdf.wdf_interrupt_priority">WDF_INTERRUPT_PRIORITY</a>-typed enumerator that specifies a priority for the interrupt.


### -field TargetProcessorSetAndGroup

A <a href="kernel.group_affinity">GROUP_AFFINITY</a> structure that specifies a processor group and a processor affinity mask within the group, if the <i>Policy</i> parameter is set to <b>WdfIrqPolicySpecifiedProcessors</b>. The GROUP_AFFINITY structure is defined in <i>Winnt.h</i>. 


## -remarks
The <a href="wdf.wdf_interrupt_extended_policy">WDF_INTERRUPT_EXTENDED_POLICY</a> structure is used as input for the <a href="wdf.iwdfinterrupt_setextendedpolicy">IWDFInterrupt::SetExtendedPolicy</a> method. 

To initialize a <a href="wdf.wdf_interrupt_extended_policy">WDF_INTERRUPT_EXTENDED_POLICY</a> structure, your driver must call <a href="wdf.wdf_interrupt_extended_policy_init">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>.


## -requirements
<table>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfinterrupt.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_interrupt_extended_policy_init">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a>
</dt>
<dt>
<a href="wdf.iwdfinterrupt_setextendedpolicy">IWDFInterrupt::SetExtendedPolicy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_EXTENDED_POLICY structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

