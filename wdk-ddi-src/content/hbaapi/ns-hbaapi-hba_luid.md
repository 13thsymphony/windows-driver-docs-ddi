---
UID : NS:hbaapi.HBA_LUID
title : HBA_LUID
author : windows-driver-content
description : The HBA_LUID structure contains the identification descriptor from the device identification page of the vital products data returned by a SCSI INQUIRY command.
old-location : storage\hba_luid.htm
old-project : storage
ms.assetid : af272e27-6cb4-4f87-9c46-512ac80fa310
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : HBA_LUID structure [Storage Devices], hbaapi/PHBA_LUID, PHBA_LUID structure pointer [Storage Devices], PHBA_LUID, storage.hba_luid, HBA_LUID, *PHBA_LUID, hbaapi/HBA_LUID, structs-Fibre_32d9473b-e356-41cc-9352-7a142fc3dcc7.xml
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
req.typenames : "*PHBA_LUID, HBA_LUID"
---

# HBA_LUID structure
The HBA_LUID structure contains the identification descriptor from the device identification page of the vital products data returned by a SCSI INQUIRY command.

## Syntax
````
typedef struct HBA_LUID {
  char buffer[256];
} HBA_LUID, *PHBA_LUID;
````

## Members


`buffer`

Contains a buffer that holds the identification descriptor.

## Remarks
A vendor specific LUID is not guaranteed to be unique or persistent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_fcpbindingentry2.md">HBA_FCPBindingEntry2</a>

<a href="..\hbaapi\ns-hbaapi-hba_fcpscsientryv2.md">HBA_FcpScsiEntryV2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_LUID structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>