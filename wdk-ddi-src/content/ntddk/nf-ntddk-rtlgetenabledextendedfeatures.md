---
UID: NF:ntddk.RtlGetEnabledExtendedFeatures
title: RtlGetEnabledExtendedFeatures function
author: windows-driver-content
description: The RtlGetEnabledExtendedFeatures routine returns a mask of extended processor features that are enabled by the system.
old-location: kernel\rtlgetenabledextendedfeatures.htm
old-project: kernel
ms.assetid: c23d3bfd-a83c-4480-b5a1-b057201ea279
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlGetEnabledExtendedFeatures, RtlGetEnabledExtendedFeatures routine [Kernel-Mode Driver Architecture], XSTATE_MASK_LEGACY, XSTATE_MASK_GSSE, k109_94843b2d-9abe-4b82-a781-dd2863ddc9c1.xml, XSTATE_MASK_LEGACY_SSE, XSTATE_MASK_LEGACY_FLOATING_POINT, wdm/RtlGetEnabledExtendedFeatures, kernel.rtlgetenabledextendedfeatures
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntdll.lib (user mode); NtosKrnl.lib (kernel mode); OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-XState-l1-1-0.dll
-	API-MS-Win-Core-XState-l1-1-1.dll
-	API-MS-Win-Core-XState-L1-1-2.dll
apiname:
-	RtlGetEnabledExtendedFeatures
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# RtlGetEnabledExtendedFeatures function
The <b>RtlGetEnabledExtendedFeatures</b> routine returns a mask of extended processor features that are enabled by the system.

## Syntax

````
ULONG64 RtlGetEnabledExtendedFeatures(
  _In_ ULONG64 FeatureMask
);
````

## Parameters

`FeatureMask`

A 64-bit feature mask. This parameter indicates a set of extended processor features for which the caller requests information about whether the features are enabled. If a mask bit is one, the caller requests information about the feature that corresponds to this mask bit. The caller sets all other mask bits to zero. Set this parameter to (ULONG64)(-1) to get the mask of all enabled features. To determine whether a particular set of features is enabled, set this parameter to the bitwise OR of one or more of the following <b>XSTATE_MASK_<i>XXX</i></b> flag bits:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY_FLOATING_POINT"></a><a id="xstate_mask_legacy_floating_point"></a><dl>
<dt><b>XSTATE_MASK_LEGACY_FLOATING_POINT</b></dt>
</dl>
</td>
<td width="60%">
The floating-point extension (x87/MMX).

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY_SSE"></a><a id="xstate_mask_legacy_sse"></a><dl>
<dt><b>XSTATE_MASK_LEGACY_SSE</b></dt>
</dl>
</td>
<td width="60%">
The streaming SIMD extension (SSE).

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_LEGACY"></a><a id="xstate_mask_legacy"></a><dl>
<dt><b>XSTATE_MASK_LEGACY</b></dt>
</dl>
</td>
<td width="60%">
Both the x87/MMX and SSE extensions.

</td>
</tr>
<tr>
<td width="40%"><a id="XSTATE_MASK_GSSE"></a><a id="xstate_mask_gsse"></a><dl>
<dt><b>XSTATE_MASK_GSSE</b></dt>
</dl>
</td>
<td width="60%">
The Intel Sandy Bridge (formerly Gesher) SSE extension.

</td>
</tr>
</table>


## Return Value

<b>RtlGetEnabledExtendedFeatures</b> returns a 64-bitmask of enabled extended processor features. The routine calculates this mask as the intersection (bitwise AND) between all enabled features and the value of the <i>FeatureMask</i> parameter. For more information about the features that are indicated by this return value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566413">XSTATE_MASK_XXX</a>.

<b>RtlGetEnabledExtendedFeatures</b> returns 0 if the XSAVE and XRSTOR instructions are disabled by the system.  This happens even if the system supports XSTATE_MASK_LEGACY_FLOATING_POINT and XSTATE_MASK_LEGACY_SSE features. Use <b>ExIsProcessorFeaturePresent </b>or CPUID to determine the availability of x87, MMX, and SSE processor features on x86 or x64 systems.

## Remarks

Another routine, <a href="..\wdm\nf-wdm-exisprocessorfeaturepresent.md">ExIsProcessorFeaturePresent</a>, indicates whether an extended processor feature is available. Unlike <b>RtlGetEnabledExtendedFeatures</b>, however, it does not indicate whether the operating system has enabled the feature for use by kernel-mode drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating system.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Ntdll.lib (user mode); NtosKrnl.lib (kernel mode); OneCoreUAP.lib on Windows 10 |
| **DLL** | NtDll.dll (user mode); NtosKrnl.exe (kernel mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\nf-wdm-exisprocessorfeaturepresent.md">ExIsProcessorFeaturePresent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlGetEnabledExtendedFeatures routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>