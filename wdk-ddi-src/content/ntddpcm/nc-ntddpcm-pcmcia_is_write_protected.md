---
UID: NC.ntddpcm.PCMCIA_IS_WRITE_PROTECTED
title: PCMCIA_IS_WRITE_PROTECTED
author: windows-driver-content
description: The PCMCIA_IS_WRITE_PROTECTED interface routine returns the write-protect condition of a PCMCIA memory card.
old-location: pcmcia\pcmcia_is_write_protected.htm
old-project: PCMCIA
ms.assetid: d270f39a-d8e8-4ec6-987e-e755da767495
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: _PAR_SET_INFORMATION, PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IsWriteProtected
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
req.irql: <=DISPATCH_LEVEL (See Remarks section.)
---

# PCMCIA_IS_WRITE_PROTECTED callback



## -description
The <b>PCMCIA_IS_WRITE_PROTECTED</b> interface routine returns the write-protect condition of a PCMCIA memory card.


## -prototype

````
PCMCIA_IS_WRITE_PROTECTED IsWriteProtected;

BOOLEAN IsWriteProtected(
  _In_opt_ PVOID Context
)
{ ... }
````


## -parameters

### -param Context [in, optional]

Pointer to the context for the interface routine.

## -returns
The <b>PCMCIA_IS_WRITE_PROTECTED </b>interface routine returns <b>TRUE</b> if the memory card is write-protected, otherwise it returns <b>FALSE</b>.

## -remarks
A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine must be running at IRQL &lt;= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL &lt; DISPATCH_LEVEL.

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
<dt>Ntddpcm.h (include Ntddpcm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL (See Remarks section.)
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
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_IS_WRITE_PROTECTED callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
