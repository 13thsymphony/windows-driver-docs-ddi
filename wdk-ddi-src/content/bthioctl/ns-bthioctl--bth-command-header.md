---
UID: NS.bthioctl._BTH_COMMAND_HEADER
title: BTH_COMMAND_HEADER
author: windows-driver-content
description: The BTH_COMMAND_HEADER structure specifies header information for a vendor-specific HCI command.
old-location: bltooth\bth_command_header.htm
old-project: bltooth
ms.assetid: 2ed2196f-a966-4766-9acd-f0beca20ed26
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: BTH_COMMAND_HEADER, BTH_COMMAND_HEADER, *PBTH_COMMAND_HEADER
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
req.alt-api: BTH_COMMAND_HEADER
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
req.iface: 
---

# BTH_COMMAND_HEADER structure



## -description
<p>The BTH_COMMAND_HEADER structure specifies header information for a vendor-specific HCI
  command.</p>


## -syntax

````
typedef struct _BTH_COMMAND_HEADER {
  USHORT OpCode;
  UCHAR  TotalParameterLength;
} BTH_COMMAND_HEADER, *PBTH_COMMAND_HEADER;
````


## -struct-fields
<dl>

### -field <b>OpCode</b>

<dd>
<p>A USHORT value that specifies the operation code for the command.</p>
</dd>

### -field <b>TotalParameterLength</b>

<dd>
<p>The size, in bytes, of the command payload, which is the data that follows the BTH_COMMAND_HEADER
     structure.</p>
</dd>
</dl>

## -remarks
<p>The BTH_COMMAND_HEADER structure specifies header information in the 
    <b>HciHeader</b> member of the 
    <a href="..\bthioctl\ns-bthioctl--bth-vendor-specific-command.md">
    BTH_VENDOR_SPECIFIC_COMMAND</a> structure. It also provides the header information for the output of
    the 
    <a href="..\bthioctl\ni-bthioctl-ioctl-bth-hci-vendor-command.md">
    IOCTL_BTH_HCI_VENDOR_COMMAND</a> IOCTL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Available in Windows Vista, and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536656">BTH_VENDOR_SPECIFIC_COMMAND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536686">IOCTL_BTH_HCI_VENDOR_COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_COMMAND_HEADER structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
