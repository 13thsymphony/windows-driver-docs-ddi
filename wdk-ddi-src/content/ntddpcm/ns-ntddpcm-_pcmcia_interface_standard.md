---
UID: NS:ntddpcm._PCMCIA_INTERFACE_STANDARD
title: _PCMCIA_INTERFACE_STANDARD
author: windows-driver-content
description: The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs.
old-location: pcmcia\pcmcia_interface_standard.htm
old-project: PCMCIA
ms.assetid: 3c98fe7b-e60a-4494-b1f0-847a7cbe9d3a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PCMCIA_INTERFACE_STANDARD, PCMCIA_INTERFACE_STANDARD, *PPCMCIA_INTERFACE_STANDARD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCMCIA_INTERFACE_STANDARD
req.alt-loc: ntddpcm.h
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
req.typenames: PCMCIA_INTERFACE_STANDARD, *PPCMCIA_INTERFACE_STANDARD
---

# _PCMCIA_INTERFACE_STANDARD structure



## -description
The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs. 



## -syntax

````
typedef struct _PCMCIA_INTERFACE_STANDARD {
  USHORT                       Size;
  USHORT                       Version;
  PINTERFACE_REFERENCE         InterfaceReference;
  PINTERFACE_DEREFERENCE       InterfaceDereference;
  PVOID                        Context;
  PPCMCIA_MODIFY_MEMORY_WINDOW ModifyMemoryWindow;
  PPCMCIA_SET_VPP              SetVpp;
  PPCMCIA_IS_WRITE_PROTECTED   IsWriteProtected;
} PCMCIA_INTERFACE_STANDARD, *PPCMCIA_INTERFACE_STANDARD;
````


## -struct-fields

### -field Size

Indicates the size of the returned interface. 


### -field Version

Indicates the version of the returned interface. 


### -field InterfaceReference

Pointer to the <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a> implementation. 


### -field InterfaceDereference

Pointer to the <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a> implementation. 


### -field Context

Pointer to an opaque handle that contains interface context information. Drivers that call routines that belong to the <b>PCMCIA_INTERFACE_STANDARD</b> interface must pass this value to the interface routines when they call them. 


### -field ModifyMemoryWindow

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537610">PCMCIA_MODIFY_MEMORY_WINDOW</a> interface routine. 


### -field SetVpp

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a> interface routine.


### -field IsWriteProtected

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a> interface routine.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddpcm.h (include Ntddpcm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537610">PCMCIA_MODIFY_MEMORY_WINDOW</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_INTERFACE_STANDARD structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

