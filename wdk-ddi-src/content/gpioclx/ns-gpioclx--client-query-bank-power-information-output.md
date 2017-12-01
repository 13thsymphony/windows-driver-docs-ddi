---
UID: NS.gpioclx._CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
title: CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
author: windows-driver-content
description: The CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_query_bank_power_information_output.htm
old-project: GPIO
ms.assetid: 156115CB-FF0C-4E53-BB7E-CF98420DF443
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.keywords: CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
req.alt-loc: Gpioclx.h
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

# CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure



## -description
<p>The <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b> structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.</p>


## -syntax

````
typedef struct _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT {
  struct {
    USHORT F1StateSupported  :1;
    USHORT Reserved  :15;
  };
  PO_FX_COMPONENT_IDLE_STATE F1IdleStateParameters;
} CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, *PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT;
````


## -struct-fields
<dl>

### -field ( <i>unnamed struct</i> )

<dd>
<p>A set of power-management flag bits.</p>
<dl>

### -field <b>F1StateSupported</b>

<dd>
<p>Indicates whether the GPIO bank supports <a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">component-level power management</a>. If this flag is set, the GPIO bank supports component-level power management. Otherwise, it does not. A GPIO bank that supports power management can change between the F0 (fully powered) state and the F1 (low-power) state independently of the Fx power states of the other banks in the GPIO controller. A GPIO bank that does not support component-level power management is always in the F0 power state when the controller is in the D0 power state.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Not used.</p>
</dd>
</dl>
</dd>

### -field <b>F1IdleStateParameters</b>

<dd>
<p>A <b>PO_FX_COMPONENT_IDLE_STATE</b> structure that describes the parameters (transition latency, residency requirement, and so on) for the F1 power state of the GPIO bank. For more information about these parameters, see <a href="..\wdm\ns-wdm--po-fx-component-idle-state.md">PO_FX_COMPONENT_IDLE_STATE</a>.</p>
</dd>
</dl>

## -remarks
<p>The <b>BankPowerInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure is a structure of type <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b>.</p>

<p>For more information about GPIO banks, see <a href="https://msdn.microsoft.com/D9425459-E052-48D8-A4F3-91387AE7059A">Partioning a GPIO Controller into Banks of Pins</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--po-fx-component-idle-state.md">PO_FX_COMPONENT_IDLE_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
