---
UID: NF.irb.AtaPortRegistryControllerKeyWrite
title: AtaPortRegistryControllerKeyWrite function
author: windows-driver-content
description: The AtaPortRegistryControllerKeyWrite routine writes the data to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller.
old-location: storage\ataportregistrycontrollerkeywrite.htm
old-project: storage
ms.assetid: dfe97cce-f349-49a1-9075-c3c3d1a60681
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: AtaPortRegistryControllerKeyWrite
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
req.alt-api: AtaPortRegistryControllerKeyWrite
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
---

# AtaPortRegistryControllerKeyWrite function



## -description
The <b>AtaPortRegistryControllerKeyWrite</b> routine writes the data to the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i>&lt;service name&gt;</i><b>\Controller</b><i>N</i>, where <i>N </i>is the number of the controller. 


## -syntax

````
BOOLEAN __inline AtaPortRegistryControllerKeyWrite(
  _In_ PVOID  ChannelExtension,
  _In_ UCHAR  ControllerNumber,
  _In_ PCHAR  ValueName,
  _In_ UCHAR  ValueType,
  _In_ PUCHAR Buffer,
  _In_ PULONG Length
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension. 

### -param ControllerNumber [in]

Contains the controller number. 

### -param ValueName [in]

Contains the name of the registry value to write to. 

### -param ValueType [in]

Indicates the type of data that is contained in the registry value. This member should be assigned one of the values indicated in the following table.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IDE_REG_DWORD
</td>
<td>
A 4-byte numeric value. 
</td>
</tr>
<tr>
<td>
IDE_REG_BINARY
</td>
<td>
Binary data. 
</td>
</tr>
<tr>
<td>
IDE_REG_SZ
</td>
<td>
A null-terminated, Unicode string. 
</td>
</tr>
</table>
 

### -param Buffer [in]

A pointer to the source buffer that contains the data to write to the registry value. 

### -param Length [in]

A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update the length of data that was successfully copied to the registry.

## -returns
<b>AtaPortRegistryControllerKeyWrite</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine. 

## -remarks
The buffer should be allocated by using <a href="storage.ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryControllerKeyWrite</b> during the <a href="storage.atachannelinitroutine">AtaChannelInitRoutine</a> routine or the <a href="storage.idehwcontrol">IdeHwControl</a> routine.; The miniport driver cannot call <b>AtaPortRegistryControllerKeyWrite</b> from any other routine or it will return <b>FALSE</b>. Additionally, the miniport driver can only call <b>AtaPortRegistryControllerKeyWrite</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 

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
<a href="storage.ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRegistryControllerKeyWrite routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
