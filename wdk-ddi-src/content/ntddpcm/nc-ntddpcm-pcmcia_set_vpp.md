---
UID: NC:ntddpcm.PCMCIA_SET_VPP
title: PCMCIA_SET_VPP
author: windows-driver-content
description: The PCMCIA_SET_VPP interface routine sets the power level of the Vpp PCMCIA pin (secondary power source).
old-location: pcmcia\pcmcia_set_vpp.htm
old-project: PCMCIA
ms.assetid: 63c34784-6ea5-49e5-8ee7-79b70e5137f7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PCMCIA.pcmcia_set_vpp, PCMCIA_SET_VPP, SetVpp, SetVpp callback function [Buses], memcdref_fe05cf85-9e4b-4267-9214-b8809e42cd5a.xml, ntddpcm/SetVpp
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntddpcm.h
api_name:
-	SetVpp
product: Windows
targetos: Windows
req.typenames: PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
---


# PCMCIA_SET_VPP callback function
The <b>PCMCIA_SET_VPP</b> interface routine sets the power level of the Vpp PCMCIA pin (secondary power source).

## Syntax

```
PCMCIA_SET_VPP PcmciaSetVpp;

BOOLEAN PcmciaSetVpp(
  PVOID Context,
  UCHAR VppLevel
)
{...}
```

## Parameters

`Context`

Pointer to the context for the interface routine.

`VppLevel`

Specifies the voltage level to set on the Vpp pin. <i>VppLevel</i> must be one of the following values:





#### PCMCIA_VPP_0V

Specifies that the voltage on the Vpp pin be set to zero volts and that the Vpp pin be disabled.



#### PCMCIA_VPP_12V

Specifies that the voltage on the Vpp pin be set to twelve volts.



#### PCMCIA_VPP_IS_VCC

Specifies that the voltage on the Vpp pin be set to equal the voltage on the Vcc (primary card power) pin.


## Return Value

The <b>PCMCIA_SET_VPP</b> interface routine returns <b>TRUE</b> after the requested voltage level is set.

## Remarks

The <b>PCMCIA_SET_VPP</b> interface routine returns control to the caller after the requested voltage is established in a stable state for the card.

A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine can run at IRQL &lt;= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddpcm.h (include Ntddpcm.h) |
| **IRQL** | "<=DISPATCH_LEVEL (See Remarks section.)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537610">PCMCIA_MODIFY_MEMORY_WINDOW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_SET_VPP callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>