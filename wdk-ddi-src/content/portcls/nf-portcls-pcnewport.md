---
UID: NF.portcls.PcNewPort
title: PcNewPort function
author: windows-driver-content
description: The PcNewPort function creates a new system-supplied port-driver object, whose interface (derived from base class IPort) is specified by a class ID.
old-location: audio\pcnewport.htm
old-project: audio
ms.assetid: d948b69c-c5cd-4614-a646-76acb493e8de
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcNewPort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewPort function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcNewPort
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

# PcNewPort function



## -description
The <b>PcNewPort</b> function creates a new system-supplied port-driver object, whose interface (derived from base class <a href="..\portcls\nn-portcls-iport.md">IPort</a>) is specified by a class ID.



## -syntax

````
NTSTATUS PcNewPort(
  _Out_ PPORT    *OutPort,
  _In_  REFCLSID ClassId
);
````


## -parameters

### -param OutPort [out]

Output pointer for the port-driver object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs the pointer to the newly created <a href="..\portcls\nn-portcls-iport.md">IPort</a> object. This object has the port interface that is specified by the <i>ClassId</i> parameter. Specify a valid, non-NULL pointer value for this parameter.


### -param ClassId [in]

Specifies the type of port interface that is being requested. For more information, see the following Remarks section.


## -returns
<b>PcNewPort</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
The <i>ClassId</i> parameter can be set to one of the GUIDs in the following table.

<b>CLSID_PortDMus</b>


<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>


<b>CLSID_PortMidi</b>


<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>


<b>CLSID_PortTopology</b>


<a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a>


<b>CLSID_PortWaveCyclic</b>


<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>


<b>CLSID_PortWavePci</b>


<a href="audio.iportwavepci">IPortWavePci</a>


<b>CLSID_PortWaveRT</b>


<a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a>


<b>CLSID_PortDMus</b> is defined in header file dmusicks.h. The other four GUIDs in the preceding table are defined in portcls.h.

In Microsoft Windows XP and later, the MIDI and DirectMusic port drivers share the same internal software implementation. This means that the <b>CLSID_PortMidi</b> GUID is equivalent to <b>CLSID_PortDMus</b>.

For more information about creating port and miniport drivers for subdevices, see <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>.

The <i>OutPort</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>. 


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
The PortCls system driver implements the PcNewPort function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.

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
<a href="..\portcls\nn-portcls-iport.md">IPort</a>
</dt>
<dt>
<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>
</dt>
<dt>
<a href="audio.iportwavepci">IPortWavePci</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewPort function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

