---
UID: NF.irb.AtaPortRegistryControllerKeyRead
title: AtaPortRegistryControllerKeyRead
author: windows-driver-content
description: The AtaPortRegistryControllerKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportregistrycontrollerkeyread.htm
old-project: storage
ms.assetid: 7db22027-49ac-4ee5-8da7-bbd16c97a35b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: AtaPortRegistryControllerKeyRead
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
req.alt-api: AtaPortRegistryControllerKeyRead
req.alt-loc: irb.h
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

# AtaPortRegistryControllerKeyRead function



## -description
<p>The <b>AtaPortRegistryControllerKeyRead</b> routine reads the data that is associated with the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>, where <i>N </i>is the number of the controller.</p>


## -syntax

````
BOOLEAN __inline AtaPortRegistryControllerKeyRead(
  _In_      PVOID  ChannelExtension,
  _In_      UCHAR  ControllerNumber,
  _In_      PCHAR  ValueName,
  _In_      UCHAR  ValueType,
  _Out_opt_ PUCHAR Buffer,
  _Inout_   PULONG Length
);
````


## -parameters
<dl>

### -param ChannelExtension [in]

<dd>
<p>A pointer to the channel extension. </p>
</dd>

### -param ControllerNumber [in]

<dd>
<p>Contains the controller number. </p>
</dd>

### -param ValueName [in]

<dd>
<p>Contains the name of the registry value to read. </p>
</dd>

### -param ValueType [in]

<dd>
<p>Indicates the type of the data that is contained in the registry value. This parameter should be assigned one of values indicated in the following table.</p>
<table>
<tr>
<th>Value type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>IDE_REG_DWORD</p>
</td>
<td>
<p>A 4-byte numeric value. </p>
</td>
</tr>
<tr>
<td>
<p>IDE_REG_BINARY</p>
</td>
<td>
<p>Binary data. </p>
</td>
</tr>
<tr>
<td>
<p>IDE_REG_SZ</p>
</td>
<td>
<p>A null-terminated, Unicode string. </p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param Buffer [out, optional]

<dd>
<p>A pointer to the buffer where the results are to be copied. </p>
</dd>

### -param Length [in, out]

<dd>
<p>A pointer to the number of bytes of data to copy. If the operation fails because of an insufficient buffer, the location that is pointed to by <i>Length</i> will update to the actual length of the data in the registry.</p>
</dd>
</dl>

## -returns
<p><b>AtaPortRegistryControllerKeyRead</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The <b>AtaPortRegistryControllerKeyRead</b> routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine.</p>

## -remarks
<p>The buffer at <i>Buffer</i> must be allocated by using <a href="..\irb\nf-irb-ataportregistryallocatebuffer.md">AtaPortRegistryAllocateBuffer</a>. </p>

<p>The miniport driver must call <b>AtaPortRegistryControllerKeyRead</b> either in its <a href="storage.atachannelinitroutine">AtaChannelInitRoutine</a> routine or in its <a href="storage.idehwcontrol">IdeHwControl</a> routine. It cannot call <b>AtaPortRegistryControllerKeyRead</b> from any other routine. Additionally, the miniport driver can only call <b>AtaPortRegistryControllerKeyRead</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Irb.h (include Ata.h or Irb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.atachannelinitroutine">AtaChannelInitRoutine</a>
</dt>
<dt>
<a href="storage.idehwcontrol">IdeHwControl</a>
</dt>
<dt>
<a href="..\irb\nf-irb-ataportregistryallocatebuffer.md">AtaPortRegistryAllocateBuffer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRegistryControllerKeyRead routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
