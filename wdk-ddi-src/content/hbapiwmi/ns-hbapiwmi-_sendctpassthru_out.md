---
UID : NS:hbapiwmi._SendCTPassThru_OUT
title : "_SendCTPassThru_OUT"
author : windows-driver-content
description : The SendCTPassThru_OUT structure is used to report the output parameter data of the SendCTPassThru WMI method to the WMI client.
old-location : storage\sendctpassthru_out.htm
old-project : storage
ms.assetid : f9340f0d-4f70-4751-b339-de11ee13a469
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : SendCTPassThru_OUT structure [Storage Devices], storage.sendctpassthru_out, structs-Fibre_f795d452-fb3f-4236-a543-d0f80f94c14f.xml, SendCTPassThru_OUT, PSendCTPassThru_OUT, _SendCTPassThru_OUT, PSendCTPassThru_OUT structure pointer [Storage Devices], *PSendCTPassThru_OUT, hbapiwmi/SendCTPassThru_OUT, hbapiwmi/PSendCTPassThru_OUT
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
req.typenames : "*PSendCTPassThru_OUT, SendCTPassThru_OUT"
---

# _SendCTPassThru_OUT structure
The SendCTPassThru_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method to the WMI client.

## Syntax
````
typedef struct _SendCTPassThru_OUT {
  ULONG HBAStatus;
  ULONG TotalResponseBufferCount;
  ULONG ActualResponseBufferCount;
  UCHAR ResponseBuffer[1];
} SendCTPassThru_OUT, *PSendCTPassThru_OUT;
````

## Members


`ActualResponseBufferCount`

Contains the size in bytes of the data that was actually retrieved.

`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`ResponseBuffer`

Contains the results of the common transport command.

`TotalResponseBufferCount`

Contains the size in bytes of the results common transport (CT) command.

## Remarks
The WMI tool suite generates a declaration of the SendCTPassThru_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendCTPassThru_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>