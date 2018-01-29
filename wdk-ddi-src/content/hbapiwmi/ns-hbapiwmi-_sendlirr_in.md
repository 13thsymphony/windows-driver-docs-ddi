---
UID : NS:hbapiwmi._SendLIRR_IN
title : _SendLIRR_IN
author : windows-driver-content
description : The SendLIRR_IN structure is used to deliver parameter data to the SendLIRR WMI method.
old-location : storage\sendlirr_in.htm
old-project : storage
ms.assetid : 774acafb-c929-483a-82b0-2a358054dc7f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : hbapiwmi/PSendLIRR_IN, hbapiwmi/SendLIRR_IN, SendLIRR_IN structure [Storage Devices], PSendLIRR_IN, SendLIRR_IN, structs-Fibre_6f0fd3c1-9eb5-4042-b12e-8dd225d966b1.xml, storage.sendlirr_in, *PSendLIRR_IN, _SendLIRR_IN, PSendLIRR_IN structure pointer [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
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
req.typenames : "*PSendLIRR_IN, SendLIRR_IN"
---

# _SendLIRR_IN structure
The SendLIRR_IN structure is used to deliver parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a> WMI method.

## Syntax
````
typedef struct _SendLIRR_IN {
  UCHAR SourceWWN[8];
  UCHAR DestWWN[8];
  UCHAR Function;
  UCHAR Type;
} SendLIRR_IN, *PSendLIRR_IN;
````

## Members


`DestWWN`

Contains a worldwide name for the destination port.

`Function`

Contains the code that identifies which registration function is to be performed. For an explanation of which values can be assigned to this member, see the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification.

`SourceWWN`

Contains a worldwide name for the local port through which the link incident record registration (LIRR) command is sent.

`Type`

Indicates the device type for which link information is requested. For an explanation of which values can be assigned to this member, see the T11 committee's <i>Fibre Channel Framing and Signaling</i> specification.

## Remarks
The WMI tool suite generates a declaration of the SendLIRR_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendLIRR_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>