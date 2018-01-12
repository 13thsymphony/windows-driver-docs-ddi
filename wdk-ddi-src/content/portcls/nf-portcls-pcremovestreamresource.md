---
UID: NF:portcls.PcRemoveStreamResource
title: PcRemoveStreamResource function
author: windows-driver-content
description: PcRemoveStreamResource removes an existing stream resource.
old-location: audio\pcremovestreamresource.htm
old-project: audio
ms.assetid: D923DA5C-0169-475D-8C0C-6A99EB06ECE0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcRemoveStreamResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcRemoveStreamResource
req.alt-loc: NA
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: NA
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# PcRemoveStreamResource function



## -description
PcRemoveStreamResource removes an existing  stream resource. PcRemoveStreamResource can be called by any driver, including non-audio WaveRT miniport drivers, that has interrupts/threads associated with an audio stream. It can also be called by audio WaveRT miniport drivers. 



## -syntax

````
NTSTATUS  PcRemoveStreamResource(
  _In_ PCSTREAMRESOURCE ResourceHandle
);
````


## -parameters

### -param ResourceHandle [in]

PCSTREAMRESOURCE– Resource handle returned by PcAddStreamResource.  
For more information, see <a href="..\portcls\nf-portcls-pcaddstreamresource.md">PcAddStreamResource</a> and <a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>.  


## -returns
STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.


## -remarks
To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 

Audio drivers must remove a previously registered resource.  Drivers may unregister a resource as a result of the following system activities:  



The audio driver must make sure the resource is valid when making this call.

Audio drivers that only run in Windows 10 can use  <a href="..\portcls\nf-portcls-pcaddstreamresource.md">PcAddStreamResource</a> and <b>PcRemoveStreamResource</b>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://msdn.microsoft.com/F9F7E13B-E8D1-4B02-9CC5-737145DEFEB9">AddStreamResource</a> and <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
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
DLL

</th>
<td width="70%">
<dl>
<dt>NA</dt>
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
<a href="..\portcls\nf-portcls-pcaddstreamresource.md">PcAddStreamResource</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\portcls\ne-portcls-_pcstreamresourcetype.md">PcStreamResourceType</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRemoveStreamResource function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

