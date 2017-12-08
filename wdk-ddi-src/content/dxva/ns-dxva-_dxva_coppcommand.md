---
UID: NS.DXVA._DXVA_COPPCOMMAND
title: _DXVA_COPPCommand
author: windows-driver-content
description: The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.
old-location: display\dxva_coppcommand.htm
old-project: display
ms.assetid: 08c87f1f-ea50-4521-80a2-67369fc6598a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXVA_COPPCommand, DXVA_COPPCommand, *LPDXVA_COPPCommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_COPPCommand
req.alt-loc: dxva.h
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

# _DXVA_COPPCommand structure



## -description
The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.


## -syntax

````
typedef struct _DXVA_COPPCommand {
  GUID  macKDI;
  GUID  guidCommandID;
  ULONG dwSequence;
  ULONG cbSizeData;
  UCHAR CommandData[4056];
} DXVA_COPPCommand, *LPDXVA_COPPCommand;
````


## -struct-fields

### -field macKDI

Specifies a message authentication code (MAC) GUID for the command at <b>CommandData</b>. The display driver can use the MAC to verify that the transmission of the command was secure (that is, it was not tampered with in transit to the driver). 

### -field guidCommandID

Specifies the GUID that identifies the command. The following GUIDs are supported:


### -field DXVA_COPPSetProtectionLevel

Sets the protection type and level on the physical connector associated with the COPP device.
The DXVA_COPPSetProtectionLevel GUID is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_GUID(DXVA_COPPSetProtectionLevel,
    0x9bb9327c,0x4eb5,0x4727,0x9f,0x00,0xb4,0x2b,0x09,0x19,0xc0,0xda);</pre>
</td>
</tr>
</table></span></div>

### -field DXVA_COPPSetSignaling

An instruction about how to protect the signal that goes through the physical connector associated with the DirectX VA COPP device.
The DXVA_COPPSetSignaling GUID is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_GUID(DXVA_COPPSetSignaling,
    0x9a631a5,0xd684,0x4c60,0x8e,0x4d,0xd3,0xbb,0xf,0xb,0xe3,0xee);</pre>
</td>
</tr>
</table></span></div>
</dd>
</dl>

### -field dwSequence

Specifies a sequence number. For the <a href="display.coppcommand">COPPCommand</a> function to process the command, the value in <b>dwSequence</b> must match the 32-bit random starting status sequence number that was passed in the <a href="display.dxva_coppsignature">DXVA_COPPSignature</a> structure to the <a href="display.coppsequencestart">COPPSequenceStart</a> function.

### -field cbSizeData

Specifies the size, in bytes, of the command data at <b>CommandData</b>.

### -field CommandData

Specifies an array that comprises the command data. 

## -remarks
For a DXVA_COPPSetProtectionLevel command, the protection information is supplied in the first 16 bytes of the <b>CommandData</b> array (the protection type in the first 4 bytes, the protection level in the next 4 bytes, and possibly some extended information in the last 8 bytes). In the call to the <a href="display.coppcommand">COPPCommand</a> function, the <b>CommandData</b> array should be cast to a pointer to a <a href="display.dxva_coppsetprotectionlevelcmddata">DXVA_COPPSetProtectionLevelCmdData</a> structure, which contains protection type, protection level, and extended information members. 

For a DXVA_COPPSetSignaling command, the signaling information is supplied by casting the <b>CommandData</b> array to a pointer to a <a href="display.dxva_coppsetsignalingcmddata">DXVA_COPPSetSignalingCmdData</a> structure. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.coppcommand">COPPCommand</a>
</dt>
<dt>
<a href="display.coppsequencestart">COPPSequenceStart</a>
</dt>
<dt>
<a href="display.dxva_coppsetprotectionlevelcmddata">DXVA_COPPSetProtectionLevelCmdData</a>
</dt>
<dt>
<a href="display.dxva_coppsetsignalingcmddata">DXVA_COPPSetSignalingCmdData</a>
</dt>
<dt>
<a href="display.dxva_coppsignature">DXVA_COPPSignature</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPCommand structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
