---
UID: NE:ntddpcm._PCMCIA_CONTROLLER_CLASS
title: "_PCMCIA_CONTROLLER_CLASS"
author: windows-driver-content
description: The PCMCIA_CONTROLLER_CLASS enumeration lists the different sorts of PC Card and CardBus controllers.
old-location: pcmcia\pcmcia_controller_class.htm
old-project: PCMCIA
ms.assetid: d834d97c-cf2d-430b-8f54-b0b47ab1503c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PcmciaNEC_98, PcmciaTI, ntddpcm/PcmciaElcController, PcmciaTopic, ntddpcm/PcmciaO2Micro, PcmciaDatabookCB, PCMCIA_CONTROLLER_CLASS, PCMCIA.pcmcia_controller_class, ntddpcm/PcmciaTI, ntddpcm/PcmciaDatabook, ntddpcm/PcmciaRicoh, ntddpcm/PcmciaTrid, ntddpcm/PcmciaNEC, ntddpcm/PcmciaOpti, PcmciaDatabook, PCMCIA_CONTROLLER_CLASS enumeration [Buses], PcmciaO2Micro, PcmciaOpti, ntddpcm/PCMCIA_CONTROLLER_CLASS, PcmciaInvalidControllerClass, ntddpcm/PcmciaCirrusLogic, PPCMCIA_CONTROLLER_CLASS, _PCMCIA_CONTROLLER_CLASS, ntddpcm/PcmciaNEC_98, memcdref_a3d708d3-6fa4-4edd-af5d-1513c8da5a9b.xml, PcmciaCirrusLogic, PcmciaElcController, ntddpcm/PcmciaCardBusCompatible, ntddpcm/PcmciaDatabookCB, ntddpcm/PcmciaTopic, ntddpcm/PcmciaInvalidControllerClass, PcmciaIntelCompatible, PcmciaTrid, *PPCMCIA_CONTROLLER_CLASS, PcmciaRicoh, PcmciaNEC, ntddpcm/PPCMCIA_CONTROLLER_CLASS, ntddpcm/PcmciaPciPcmciaBridge, PPCMCIA_CONTROLLER_CLASS enumeration pointer [Buses], PcmciaCardBusCompatible, PcmciaPciPcmciaBridge, ntddpcm/PcmciaIntelCompatible
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddpcm.h
apiname:
-	PCMCIA_CONTROLLER_CLASS
product: Windows
targetos: Windows
req.typenames: PCMCIA_CONTROLLER_CLASS, *PPCMCIA_CONTROLLER_CLASS
---

# _PCMCIA_CONTROLLER_CLASS Enumeration
The PCMCIA_CONTROLLER_CLASS enumeration lists the different sorts of PC Card and CardBus controllers.

## Syntax
````
typedef enum _PCMCIA_CONTROLLER_CLASS { 
  PcmciaInvalidControllerClass  = -1,
  PcmciaIntelCompatible         = 2,
  PcmciaCardBusCompatible       = 3,
  PcmciaElcController           = 4,
  PcmciaDatabook                = 5,
  PcmciaPciPcmciaBridge         = 6,
  PcmciaCirrusLogic             = 7,
  PcmciaTI                      = 8,
  PcmciaTopic                   = 9,
  PcmciaRicoh                   = 10,
  PcmciaDatabookCB              = 11,
  PcmciaOpti                    = 12,
  PcmciaTrid                    = 13,
  PcmciaO2Micro                 = 14,
  PcmciaNEC                     = 15,
  PcmciaNEC_98                  = 16
} PCMCIA_CONTROLLER_CLASS, *PPCMCIA_CONTROLLER_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>PcmciaCardBusCompatible</td>
                    <td>Indicates a cardbus-compatible controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaCirrusLogic</td>
                    <td>Indicates a CirrusLogic cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaDatabook</td>
                    <td>Indicates a controller from the Databook TCIC family of controllers.</td>
                </tr>
            
                <tr>
                    <td>PcmciaDatabookCB</td>
                    <td>Indicates a Databook cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaElcController</td>
                    <td>Indicates an ELC controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaIntelCompatible</td>
                    <td>Indicates an Intel-compatible controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaInvalidControllerClass</td>
                    <td>Indicates that the controller class is invalid.</td>
                </tr>
            
                <tr>
                    <td>PcmciaNEC</td>
                    <td>Indicates a Yenta-compliant NEC cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaNEC_98</td>
                    <td>Indicates a NEC cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaO2Micro</td>
                    <td>Indicates an O2Micro cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaOpti</td>
                    <td>Indicates an OPTI cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaPciPcmciaBridge</td>
                    <td>Indicates a PCI to PCMCIA bridge.</td>
                </tr>
            
                <tr>
                    <td>PcmciaRicoh</td>
                    <td>Indicates a Ricoh cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaTI</td>
                    <td>Indicates a TI cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaTopic</td>
                    <td>Indicates a Toshiba Topic cardbus controller.</td>
                </tr>
            
                <tr>
                    <td>PcmciaTrid</td>
                    <td>Indicates a TRID controller.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpcm.h (include Ntddpcm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_CONTROLLER_CLASS enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>