---
UID: NS.ntddk._WHEA_ERROR_PACKET_FLAGS
title: WHEA_ERROR_PACKET_FLAGS
author: windows-driver-content
description: The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a WHEA_ERROR_PACKET structure.
old-location: whea\whea_error_packet_flags.htm
old-project: whea
ms.assetid: e1dae7df-7d81-42cc-9a01-44345f53ba4e
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_ERROR_PACKET_FLAGS, WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_PACKET_FLAGS
req.alt-loc: ntddk.h
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
req.iface: 
---

# WHEA_ERROR_PACKET_FLAGS structure



## -description
<p>The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.</p>


## -syntax

````
typedef union _WHEA_ERROR_PACKET_FLAGS {
  struct {
    ULONG PreviousError  :1;
    ULONG Reserved1  :1;
    ULONG HypervisorError  :1;
    ULONG Simulated  :1;
    ULONG PlatformPfaControl  :1;
    ULONG PlatformDirectedOffline  :1;
    ULONG Reserved2  :26;
  };
  ULONG  AsULONG;
} WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS;
````


## -struct-fields
<dl>

### -field <b>PreviousError</b>

<dd>
<p>A single bit that indicates whether the hardware error packet contains information about a fatal hardware error. This error caused the operating system to generate a bug check and restart.</p>
</dd>

### -field <b>Reserved1</b>

<dd>
<p>Reserved for system use.</p>
<p>
<div class="alert"><b>Note</b>  In versions of the Windows Driver Kit (WDK) prior to Windows 7, this member was named <b>CpuValid</b>. The <b>CpuValid </b>member has been deprecated in the WDK for Windows 7 and later versions of Windows.</div>
<div> </div>
</p>
</dd>

### -field <b>HypervisorError</b>

<dd>
<p>A single bit that indicates that a hypervisor error has occurred.</p>
</dd>

### -field <b>Simulated</b>

<dd>
<p>A single bit that indicates that the error condition was simulated.</p>
</dd>

### -field <b>PlatformPfaControl</b>

<dd>
<p>A single bit that indicates whether WHEA or a PSHED plug-in is in control of predictive failure analysis (PFA). If this bit is set, the PSHED plug-in is in control of PFA and must set the <b>PlatformDirectedOffline </b>to bring an <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> memory page into an offline state.</p>
<p>For more information about PFA support for WHEA, see <a href="NULL">Predictive Failure Analysis (PFA)</a>.</p>
<p>
<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>
</p>
</dd>

### -field <b>PlatformDirectedOffline</b>

<dd>
<p>A single bit that indicates whether the PSHED plug-in that performs PFA on a system component has determined if the component should be brought into an offline state. This bit is only valid if the <b>PlatformPfaControl</b> member is set.</p>
<p>
<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>
</p>
</dd>

### -field <b>Reserved2</b>

<dd>
<p>Reserved for system use. </p>
</dd>

### -field <b>AsULONG</b>

<dd>
<p>A ULONG representation of the contents of the WHEA_ERROR_PACKET_FLAGS union.</p>
</dd>
</dl>

## -remarks
<p>The WHEA_ERROR_PACKET_FLAGS union describes the error condition reported by using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="NULL">Predictive Failure Analysis (PFA)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_FLAGS union%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
