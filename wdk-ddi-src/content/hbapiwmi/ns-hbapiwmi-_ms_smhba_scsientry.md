---
UID : NS:hbapiwmi._MS_SMHBA_SCSIENTRY
title : "_MS_SMHBA_SCSIENTRY"
author : windows-driver-content
description : The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.
old-location : storage\ms_smhba_scsientry.htm
old-project : storage
ms.assetid : 38779458-a561-4048-86d8-905e4e50095f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ms_smhba_scsientry, MS_SMHBA_SCSIENTRY structure [Storage Devices], *PMS_SMHBA_SCSIENTRY, hbapiwmi/PMS_SMHBA_SCSIENTRY, MS_SMHBA_SCSIENTRY, structs-Fibre_95d0f020-6910-4764-9234-181b525abf5b.xml, PMS_SMHBA_SCSIENTRY, _MS_SMHBA_SCSIENTRY, hbapiwmi/MS_SMHBA_SCSIENTRY, PMS_SMHBA_SCSIENTRY structure pointer [Storage Devices]
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
req.typenames : "*PMS_SMHBA_SCSIENTRY, MS_SMHBA_SCSIENTRY"
---

# _MS_SMHBA_SCSIENTRY structure
The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.

## Syntax
````
typedef struct _MS_SMHBA_SCSIENTRY {
  MS_SMHBA_PORTLUN PortLun;
  UCHAR            LUID[256];
  HBAScsiID        ScsiId;
} MS_SMHBA_SCSIENTRY, *PMS_SMHBA_SCSIENTRY;
````

## Members


`LUID`

The logical unit descriptor for the device that the operating system derives from SCSI inquiry data.

`PortLun`

An array of MS_SMHBA_PORTLUN entries.

`ScsiId`

A structure of type HBAScsiID that contains information that uniquely identifies a logical unit to the operating system.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |