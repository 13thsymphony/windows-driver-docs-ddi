---
UID: NS.pepfx._PEP_ACPI_PREPARE_DEVICE
title: PEP_ACPI_PREPARE_DEVICE
author: windows-driver-content
description: The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.
old-location: kernel\pep_acpi_prepare_device.htm
old-project: kernel
ms.assetid: F8D6680D-EFA7-4DED-B808-0E738A852641
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE
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
req.alt-api: PEP_ACPI_PREPARE_DEVICE
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
req.iface: 
---

# PEP_ACPI_PREPARE_DEVICE structure



## -description
<p>The <b>PEP_ACPI_PREPARE_DEVICE</b> structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.</p>


## -syntax

````
typedef struct _PEP_ACPI_PREPARE_DEVICE {
  PANSI_STRING AcpiDeviceName;
  ULONG        InputFlags;
  BOOLEAN      DeviceAccepted;
  ULONG        OutputFlags;
} PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE;
````


## -struct-fields
<dl>

### -field <b>AcpiDeviceName</b>

<dd>
<p>[in] A pointer to an <a href="kernel.ansi_string">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="NULL">Enumerating Child Devices and Control Methods</a>.</p>
</dd>

### -field <b>InputFlags</b>

<dd>
<p>[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_PREPARE_DEVICE_INPUT_FLAG_NONE (0x0).</p>
</dd>

### -field <b>DeviceAccepted</b>

<dd>
<p>[out] Whether the PEP is prepared to provide ACPI services for the device. Set this member to TRUE if the PEP is prepared to be the sole provider of ACPI services for this device, and to FALSE if it is not.</p>
</dd>

### -field <b>OutputFlags</b>

<dd>
<p>[out] A set of output flags. No flags are currently defined for this member. Set this member to PEP_ACPI_PREPARE_DEVICE_OUTPUT_FLAG_NONE (0x0).</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_notify_acpi_prepare_device">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a> notification. The <b>AcpiDeviceName</b> and <b>InputFlags</b> members of the structure contain input values that are supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>DeviceAccepted</b> and <b>OutputFlags</b> members contain output values that the PEP writes to the structure in response to the notification.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
<dt>
<a href="kernel.pep_notify_acpi_prepare_device">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_PREPARE_DEVICE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
