---
UID: NS.BTHIOCTL._BTH_VENDOR_SPECIFIC_COMMAND
title: _BTH_VENDOR_SPECIFIC_COMMAND
author: windows-driver-content
description: The BTH_VENDOR_SPECIFIC_COMMAND structure specifies a Bluetooth vendor-specific command.
old-location: bltooth\bth_vendor_specific_command.htm
old-project: bltooth
ms.assetid: c37844d9-206a-4060-8b46-9afe691fe8f9
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Available in Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTH_VENDOR_SPECIFIC_COMMAND
req.alt-loc: bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _BTH_VENDOR_SPECIFIC_COMMAND structure



## -description
The BTH_VENDOR_SPECIFIC_COMMAND structure specifies a Bluetooth vendor-specific command.


## -syntax

````
typedef struct _BTH_VENDOR_SPECIFIC_COMMAND {
  ULONG              ManufacturerId;
  UCHAR              LmpVersion;
  BOOLEAN            MatchAnySinglePattern;
  BTH_COMMAND_HEADER HciHeader;
  UCHAR              Data[1];
} BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND;
````


## -struct-fields

### -field ManufacturerId

The manufacturer identifier of the radio. Radios that have this manufacturer identifier can
     receive the vendor-specific command.

### -field LmpVersion

A UCHAR that contains the link management protocol (LMP) version. If the LMP version of a radio is
     greater than this value, the command is sent to the radio. Otherwise, the radio does not receive the
     command. If 
     <b>LmpVersion</b> is zero, all radios will receive the vendor-specific command.

### -field MatchAnySinglePattern

A BOOLEAN value that specifies if all the patterns in the 
     <b>Data</b> member must match or only one pattern must match to associate an event with a vendor-specific
     command. If there are no patterns that are associated with a vendor-specific command, this member is
     ignored. If 
     <b>MatchAnySinglePattern</b> is <b>FALSE</b>, all the patterns must match to associate an event with the
     command. If 
     <b>MatchAnySinglePattern</b> is <b>TRUE</b>, matching any pattern associates an event with the command.

### -field HciHeader

A 
     <a href="bltooth.bth_command_header">BTH_COMMAND_HEADER</a> structure that
     contains information about the vendor-specific command that includes an operation code and buffer
     length. The buffer length should only include the size of the data to be sent to the radio. It should
     not include the size of the patterns.

### -field Data

A UCHAR array that contains the data and patterns for the command that is specified in the 
     <b>HciHeader</b> member. Patterns are specified with 
     <a href="bltooth.bth_vendor_pattern">BTH_VENDOR_PATTERN</a> structures.

## -remarks
This BTH_VENDOR_SPECIFIC_COMMAND structure specifies the input buffer for the 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_hci_vendor_command.md">
    IOCTL_BTH_HCI_VENDOR_COMMAND</a> IOCTL. This IOCTL can be used to send vendor-specific commands to
    Bluetooth radios.

To specify the size of the HCI command data, use the
    <b>TotalParameterLength</b> member in the 
    <a href="bltooth.bth_command_header">BTH_COMMAND_HEADER</a> structure in the
    BTH_VENDOR_SPECIFIC_COMMAND structure's 
    <b>HciHeader</b> member.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

If patterns are required, the patterns follow the data to be sent to the radio in the 
    <b>Data</b> member buffer. Each pattern begins with a 
    <a href="bltooth.bth_vendor_pattern">BTH_VENDOR_PATTERN</a> structure.

If such patterns are specified, the 
    <b>TotalParameterLength</b> member should not include the size of the patterns.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Available in Windows Vista, and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bthioctl.h (include Bthioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="bltooth.bth_command_header">BTH_COMMAND_HEADER</a>
</dt>
<dt>
<a href="bltooth.bth_vendor_pattern">BTH_VENDOR_PATTERN</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_hci_vendor_command.md">IOCTL_BTH_HCI_VENDOR_COMMAND</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_VENDOR_SPECIFIC_COMMAND structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
