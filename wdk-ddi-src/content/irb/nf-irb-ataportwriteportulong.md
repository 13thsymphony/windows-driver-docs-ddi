---
UID: NF.irb.AtaPortWritePortUlong
title: AtaPortWritePortUlong function
author: windows-driver-content
description: The AtaPortWritePortUlong routine transfers a ULONG value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportulong.htm
old-project: storage
ms.assetid: 49c01a7c-4e09-4ad2-9157-ab75b1a23d66
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: AtaPortWritePortUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AtaPortWritePortUlong
req.alt-loc: ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
---

# AtaPortWritePortUlong function



## -description
The <b>AtaPortWritePortUlong</b> routine transfers a ULONG value to the HBA.



## -syntax

````
VOID AtaPortWritePortUlong(
  _In_ PULONG Port,
  _In_ ULONG  Value
);
````


## -parameters

### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="storage.ataportgetdevicebase">AtaPortGetDeviceBase</a>.


### -param Value [in]

Specifies the value to write to the HBA's I/O port.


## -returns
None 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Irb.h (include Ata.h or Irb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ataport.lib; </dt>
<dt>Pciidex.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.ataportgetdevicebase">AtaPortGetDeviceBase</a>
</dt>
<dt>
<a href="storage.ataportwriteportuchar">AtaPortWritePortUchar</a>
</dt>
<dt>
<a href="storage.ataportwriteportushort">AtaPortWritePortUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWritePortUlong routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
