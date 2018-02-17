---
UID: NS:hbaapi.HBA_FcpScsiEntry
title: HBA_FcpScsiEntry
author: windows-driver-content
description: The HBA_FcpScsiEntry structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpscsientry.htm
old-project: storage
ms.assetid: 19e40a1b-fcbf-4510-a7c0-aa9a61f2f651
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_FCPSCSIENTRY, HBA_FCPSCSIENTRY structure [Storage Devices], hbaapi/HBA_FcpScsiEntry, hbaapi/PHBA_FCPSCSIENTRY, storage.hba_fcpscsientry, HBA_FcpScsiEntry structure [Storage Devices], HBA_FcpScsiEntry, PHBA_FCPSCSIENTRY structure pointer [Storage Devices], *PHBA_FCPSCSIENTRY, structs-Fibre_32b32b55-43e6-484c-a7fb-5c477864b735.xml, PHBA_FCPSCSIENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbaapi.h
apiname:
-	HBA_FCPSCSIENTRY
product: Windows
targetos: Windows
req.typenames: "*PHBA_FCPSCSIENTRY, HBA_FCPSCSIENTRY"
---

# HBA_FcpScsiEntry structure
The HBA_FcpScsiEntry structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit.

## Syntax
````
typedef struct HBA_FcpScsiEntry {
  HBA_SCSIID ScsiId;
  HBA_FCPID  FcpId;
} HBA_FCPSCSIENTRY, *PHBA_FCPSCSIENTRY;
````

## Members


`FcpId`

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> that uniquely identifies the device anywhere on the fibre channel network.

`ScsiId`

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a> that holds information that the operating system uses to identify a SCSI device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FcpScsiEntry structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>