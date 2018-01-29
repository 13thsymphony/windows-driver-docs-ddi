---
UID : NS:ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS
title : _KSAUDIO_PACKETSIZE_CONSTRAINTS
author : windows-driver-content
description : The KSAUDIO_PACKETSIZE_CONSTRAINTS structure describes the physical hardware constraints.
old-location : audio\ksaudio_packetsize_constraints.htm
old-project : audio
ms.assetid : 6BD3E98A-A2A5-4285-8F41-1445F90DD8EB
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : FILE_32_BYTE_ALIGNMENT, PKSAUDIO_PACKETSIZE_CONSTRAINTS, FILE_128_BYTE_ALIGNMENT, FILE_256_BYTE_ALIGNMENT, FILE_QUAD_ALIGNMENT, ksmedia/KSAUDIO_PACKETSIZE_CONSTRAINTS, KSAUDIO_PACKETSIZE_CONSTRAINTS structure [Audio Devices], FILE_LONG_ALIGNMENT, FILE_BYTE_ALIGNMENT, audio.ksaudio_packetsize_constraints, ksmedia/PKSAUDIO_PACKETSIZE_CONSTRAINTS, FILE_OCTA_ALIGNMENT, FILE_WORD_ALIGNMENT, FILE_512_BYTE_ALIGNMENT, FILE_64_BYTE_ALIGNMENT, PKSAUDIO_PACKETSIZE_CONSTRAINTS structure pointer [Audio Devices], KSAUDIO_PACKETSIZE_CONSTRAINTS, _KSAUDIO_PACKETSIZE_CONSTRAINTS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSAUDIO_PACKETSIZE_CONSTRAINTS
---

# _KSAUDIO_PACKETSIZE_CONSTRAINTS structure
The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="..\ksmedia\ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint.md">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.

## Syntax
````
typedef struct _KSAUDIO_PACKETSIZE_CONSTRAINTS {
  ULONG                                                                                   MinPacketPeriodInHns;
  ULONG                                                                                   PacketSizeFileAlignment;
  ULONG                                                                                   Reserved;
  ULONG                                                                                   NumProcessingModeConstraints;
  _Field_size_(NumProcessingModeConstraints) KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT ProcessingModeConstraints[ANYSIZE_ARRAY];
} KSAUDIO_PACKETSIZE_CONSTRAINTS, *PKSAUDIO_PACKETSIZE_CONSTRAINTS;
````

## Members


`MinPacketPeriodInHns`

The absolute minimum processing period supported by the driver expressed in hundred-nanosecond (HNS) units. This value can be 0 if the driver has no specific minimum processing period.

`NumProcessingModeConstraints`

The number of additional constraints for specific processing modes. This value can be 0.

`PacketSizeFileAlignment`

The byte size alignment requirement. Use one of these defined file alignment values:
<a id="FILE_BYTE_ALIGNMENT"></a><a id="file_byte_alignment"></a>

`ProcessingModeConstraints`

An array of 0 or more processing mode constraints.

`Reserved`

Unused.

## Remarks
The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints property on the PnP interface of the KS filter that has the streaming pins with the constraints. 


For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint.md">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a>

<a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_PACKETSIZE_CONSTRAINTS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>