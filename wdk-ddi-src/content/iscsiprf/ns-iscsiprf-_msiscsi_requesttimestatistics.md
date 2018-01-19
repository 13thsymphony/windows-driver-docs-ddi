---
UID : NS:iscsiprf._MSiSCSI_RequestTimeStatistics
title : _MSiSCSI_RequestTimeStatistics
author : windows-driver-content
description : The MSiSCSI_RequestTimeStatistics structure is used by iSCSI initiators to report request time statistics.
old-location : storage\msiscsi_requesttimestatistics.htm
old-project : storage
ms.assetid : fb884cff-dedb-44cf-b9ea-306bfa66b06f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MSiSCSI_RequestTimeStatistics, *PMSiSCSI_RequestTimeStatistics, MSiSCSI_RequestTimeStatistics
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
req.alt-api : MSiSCSI_RequestTimeStatistics
req.alt-loc : iscsiprf.h
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
req.typenames : "*PMSiSCSI_RequestTimeStatistics, MSiSCSI_RequestTimeStatistics"
---

# _MSiSCSI_RequestTimeStatistics structure
The MSiSCSI_RequestTimeStatistics structure is used by iSCSI initiators to report request time statistics.

## Syntax
````
typedef struct _MSiSCSI_RequestTimeStatistics {
  WCHAR     iSCSIName[223 + 1];
  USHORT    CID;
  ULONGLONG USID;
  ULONGLONG UniqueAdapterId;
  ULONG     MaximumProcessingTime;
  ULONG     AverageProcessingTime;
} MSiSCSI_RequestTimeStatistics, *PMSiSCSI_RequestTimeStatistics;
````

## Members

        
            `AverageProcessingTime`

            The average time taken to process a request over this connection.
        
            `CID`

            The iSCSI connection identifier (ID) for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the connection. Do not use this ID. Application software should use the connection identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the UniqueConnectionId parameter.
        
            `iSCSIName`

            The iSCSI target name.
        
            `MaximumProcessingTime`

            The maximum time taken to process a request over this connection.
        
            `UniqueAdapterId`

            A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the UniqueAdapterId member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.
        
            `USID`

            The iSCSI session ID for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the session. Do not use this ID. Application software should use the session identifier that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods return in the UniqueSessionId parameter.

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

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
</dt>
<dt>
<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_RequestTimeStatistics structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>