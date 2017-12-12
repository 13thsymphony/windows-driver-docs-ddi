---
UID: NF.irb.AtaPortGetUnCachedExtension
title: AtaPortGetUnCachedExtension function
author: windows-driver-content
description: The AtaPortGetUncachedExtension routine allocates an uncached common buffer that is shared by the CPU and the device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetuncachedextension.htm
old-project: storage
ms.assetid: 7b81fc29-4906-4095-b197-6b63f5f01ac0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: AtaPortGetUnCachedExtension
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
req.alt-api: AtaPortGetUnCachedExtension
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

# AtaPortGetUnCachedExtension function



## -description
The <b>AtaPortGetUncachedExtension</b> routine allocates an uncached common buffer that is shared by the CPU and the device.



## -syntax

````
PVOID AtaPortGetUnCachedExtension(
  _In_ PVOID ChannelExtension,
  _In_ ULONG UncachedExtensionSize,
  _In_ ULONG IrbExtensionSize
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param UncachedExtensionSize [in]

Specifies the length, in bytes, of the uncached common buffer. Set this parameter to 0 if the miniport driver does not require an uncached extension.


### -param IrbExtensionSize [in]

Specifies the size, in bytes, that is required by the miniport driver for its per request storage, if any. 

Set this parameter set to 0 if the miniport driver does not maintain per IRB information for which it requires storage. 


## -returns
<b>AtaPortGetUncachedExtension</b> returns a virtual address pointer to the uncached extension. If it cannot allocate the requested memory, or if the memory was previously allocated, it returns <b>NULL</b>.


## -remarks
The miniport driver can use IRB extensions as storage for driver-determined, request-specific information, such as data that is necessary to process a particular request.

The port driver does not initialize IRB extensions, but sets a pointer to an extension in each IRB that it sends to the miniport driver.

HBA hardware can safely access an IRB extension.

The miniport driver must not call <b>AtaPortGetUncachedExtension</b> from any routine other than its <a href="storage.idehwcontrol">IdeHwControl</a> routine, and only when it is processing a control action of <b>StartChannel</b>. Calls of <b>AtaPortGetUncachedExtension</b> from other miniport driver routines result in incorrect operation or even system failure. The port driver automatically frees the uncached extension after it invokes <b>IdeHwControl</b> with the <b>StopChannel</b> control action.


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
<a href="storage.idehwcontrol">IdeHwControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortGetUnCachedExtension routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

