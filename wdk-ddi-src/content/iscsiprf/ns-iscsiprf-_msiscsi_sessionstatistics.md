---
UID : NS:iscsiprf._MSiSCSI_SessionStatistics
title : "_MSiSCSI_SessionStatistics"
author : windows-driver-content
description : The MSiSCSI_SessionStatistics structure is used by iSCSI initiators to report session statistics.
old-location : storage\msiscsi_sessionstatistics.htm
old-project : storage
ms.assetid : 04ceffce-cd5f-4e62-98cb-450e8552a811
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : iscsiprf/MSiSCSI_SessionStatistics, MSiSCSI_SessionStatistics, _MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics, iscsiprf/PMSiSCSI_SessionStatistics, storage.msiscsi_sessionstatistics, PMSiSCSI_SessionStatistics structure pointer [Storage Devices], MSiSCSI_SessionStatistics structure [Storage Devices], structs-iSCSI_90b593e8-cda5-4b61-860b-b17394f90891.xml, PMSiSCSI_SessionStatistics
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsiprf.h
req.include-header : Iscsiprf.h
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
req.typenames : MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
---

# _MSiSCSI_SessionStatistics structure
The MSiSCSI_SessionStatistics structure is used by iSCSI initiators to report session statistics.

## Syntax
````
typedef struct _MSiSCSI_SessionStatistics {
  WCHAR     iSCSIName[223 + 1];
  ULONGLONG USID;
  ULONGLONG UniqueAdapterId;
  ULONGLONG BytesSent;
  ULONGLONG BytesReceived;
  ULONGLONG PDUCommandsSent;
  ULONGLONG PDUResponsesReceived;
  ULONGLONG DigestErrors;
  ULONGLONG ConnectionTimeoutErrors;
  ULONGLONG FormatErrors;
} MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics;
````

## Members


`BytesReceived`

The number of bytes that are received over this session.

`BytesSent`

The number of bytes that are sent over this session.

`ConnectionTimeoutErrors`

The number of connection time-out errors that have occurred in this session.

`DigestErrors`

The number of digest errors that have occurred in this session.

`FormatErrors`

The number of format errors that have occurred in this session.

`iSCSIName`

A wide character string that contains the name of an iSCSI target.

`PDUCommandsSent`

The number of PDUs that are sent over this session.

`PDUResponsesReceived`

The number of PDUs that are received over this session.

`UniqueAdapterId`

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this ID. The initiator reports this value in the <i>UniqueAdapterId</i> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.

`USID`

The iSCSI session identifier (ID) for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the session. Do not use this ID. Application software should use the session identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the <i>UniqueSessionId</i> parameter.

## Remarks
It is optional that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iscsiprf.h (include Iscsiprf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563139">MSiSCSI_SessionStatistics WMI Class</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_SessionStatistics structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>