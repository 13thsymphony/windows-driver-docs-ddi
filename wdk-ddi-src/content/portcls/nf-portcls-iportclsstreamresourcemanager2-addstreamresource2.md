---
UID: NF.portcls.IPortClsStreamResourceManager2.AddStreamResource2
title: IPortClsStreamResourceManager2::AddStreamResource2 method
author: windows-driver-content
description: AddStreamResource2 adds a stream resource. Two type of stream resources are supported: interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.
old-location: audio\iportclsstreamresourcemanager2_addstreamresource2.htm
old-project: audio
ms.assetid: C140D11C-41D6-4812-AD95-990CBFA06FE8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortClsStreamResourceManager2, IPortClsStreamResourceManager2::AddStreamResource2, AddStreamResource2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortClsStreamResourceManager2.AddStreamResource2
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IPortClsStreamResourceManager2::AddStreamResource2 method



## -description
AddStreamResource2 adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. The AddStreamResource2 method can only be used by audio waveRT miniport drivers.



## -syntax

````
NTSTATUS  AddStreamResource2(
  [in]  PDEVICE_OBJECT               PhysicalDeviceObject,
  [in]  PVOID                        ResourceSet,
  [in]  PPCSTREAMRESOURCE_DESCRIPTOR ResourceDescriptor,
  [out] PCSTREAMRESOURCE*            ResourceHandle
);
````


## -parameters

### -param PhysicalDeviceObject [in]

Pointer to the device object. The device object is a system structure of type <a href="kernel.device_object">DEVICE_OBJECT</a>.


### -param ResourceSet [in]

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time.


### -param ResourceDescriptor [in]

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information see, <a href="audio.pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>. 



### -param ResourceHandle [out]

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="audio.iportclsstreamresourcemanager_removestreamresource">RemoveStreamResource</a>.  


## -returns
STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 10, version 1511 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.iportclsstreamresourcemanager_removestreamresource">RemoveStreamResource</a>
</dt>
<dt>
<a href="audio.pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportclsstreamresourcemanager.md">IPortClsStreamResourceManager</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportclsstreamresourcemanager2.md">IPortClsStreamResourceManager2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsStreamResourceManager2::AddStreamResource2 method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
