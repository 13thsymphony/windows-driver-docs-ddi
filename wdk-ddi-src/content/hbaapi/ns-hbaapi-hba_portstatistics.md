---
UID : NS:hbaapi.HBA_PortStatistics
title : HBA_PortStatistics
author : windows-driver-content
description : The HBA_PortStatistics structure contains statistical information about a port.
old-location : storage\hba_portstatistics.htm
old-project : storage
ms.assetid : 3a0d6633-b4a6-4864-96ae-4f91de11daa1
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : SMHBA_FCPHYSTATISTICS, HBA_PORTSTATISTICS, hbaapi/PHBA_PORTSTATISTICS, storage.hba_portstatistics, *PHBA_PORTSTATISTICS, HBA_PortStatistics, *PSMHBA_FCPHYSTATISTICS, PHBA_PORTSTATISTICS, hbaapi/HBA_PortStatistics, HBA_PortStatistics structure [Storage Devices], PHBA_PORTSTATISTICS structure pointer [Storage Devices], HBA_PORTSTATISTICS structure [Storage Devices], structs-Fibre_4c6c7237-af5e-415a-a7db-db594b1a5968.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbaapi.h
req.include-header : Hbaapi.h
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
req.typenames : "*PHBA_PORTSTATISTICS, HBA_PORTSTATISTICS"
---

# HBA_PortStatistics structure
The HBA_PortStatistics structure contains statistical information about a port.

## Syntax
````
typedef struct HBA_PortStatistics {
  HBA_INT64 SecondsSinceLastReset;
  HBA_INT64 TxFrames;
  HBA_INT64 TxWords;
  HBA_INT64 RxFrames;
  HBA_INT64 RxWords;
  HBA_INT64 LIPCount;
  HBA_INT64 NOSCount;
  HBA_INT64 ErrorFrames;
  HBA_INT64 DumpedFrames;
  HBA_INT64 LinkFailureCount;
  HBA_INT64 LossOfSyncCount;
  HBA_INT64 LossOfSignalCount;
  HBA_INT64 PrimitiveSeqProtocolErrCount;
  HBA_INT64 InvalidTxWordCount;
  HBA_INT64 InvalidCRCCount;
} HBA_PORTSTATISTICS, *PHBA_PORTSTATISTICS;
````

## Members


`DumpedFrames`

Reports the number of frames that were lost due to a lack of host buffers available.

`ErrorFrames`

Reports the number of frames that have been received in error.

`InvalidCRCCount`

Reports the value of the invalid CRC count field of the link error status block for the specified port.

`InvalidTxWordCount`

Reports the value of the invalid transmission word field of the link error status block for the specified port.

`LinkFailureCount`

Reports the link failure count field of the error status block for the port.

`LIPCount`

Reports the number of LIP events that have occurred on a arbitrated loop.

`LossOfSignalCount`

Reports the value of the loss of signal count field of the link error status block for the specified port.

`LossOfSyncCount`

Reports the value of the loss of synchronization count field of the link error status block for the port.

`NOSCount`

Reports the number of NOS events that have occurred on the switched fabric.

`PrimitiveSeqProtocolErrCount`

Reports the value of the primitive sequence protocol error field of the link error status block for the port.

`RxFrames`

Reports the number of fibre channel frames received for all protocols and classes.

`RxWords`

Reports the number of fibre channel words received for all protocols and classes.

`SecondsSinceLastReset`

Reports the number of seconds since the statistics were last reset.

`TxFrames`

Reports the number of fibre channel frames transmitted for all protocols and classes.

`TxWords`

Reports the number of fibre channel words transmitted for all protocols and classes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\nf-hbaapi-hba_getportstatistics.md">HBA_GetPortStatistics</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_PortStatistics structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>