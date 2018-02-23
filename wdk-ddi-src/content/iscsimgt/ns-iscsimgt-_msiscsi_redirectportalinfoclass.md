---
UID: NS:iscsimgt._MSiSCSI_RedirectPortalInfoClass
title: "_MSiSCSI_RedirectPortalInfoClass"
author: windows-driver-content
description: The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.
old-location: storage\msiscsi_redirectportalinfoclass.htm
old-project: storage
ms.assetid: fcddf029-748b-4300-9f87-a103d961918a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PMSiSCSI_RedirectPortalInfoClass, PMSiSCSI_RedirectPortalInfoClass, iscsimgt/MSiSCSI_RedirectPortalInfoClass, structs-iSCSI_211386cb-7e73-40d9-8284-560555fe8201.xml, PMSiSCSI_RedirectPortalInfoClass structure pointer [Storage Devices], MSiSCSI_RedirectPortalInfoClass structure [Storage Devices], storage.msiscsi_redirectportalinfoclass, MSiSCSI_RedirectPortalInfoClass, _MSiSCSI_RedirectPortalInfoClass, iscsimgt/PMSiSCSI_RedirectPortalInfoClass"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
apiname:
-	MSiSCSI_RedirectPortalInfoClass
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_RedirectPortalInfoClass, MSiSCSI_RedirectPortalInfoClass"
---

# _MSiSCSI_RedirectPortalInfoClass structure
The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.

## Syntax
````
typedef struct _MSiSCSI_RedirectPortalInfoClass {
  ULONGLONG                 UniqueAdapterId;
  ULONG                     SessionCount;
  ISCSI_RedirectSessionInfo RedirectSessionList[1];
} MSiSCSI_RedirectPortalInfoClass, *PMSiSCSI_RedirectPortalInfoClass;
````

## Members


`RedirectSessionList`

An array of structures that contains as many ISCSI_RedirectSessionInfo structures as specified in the connection count.

`SessionCount`

The number of sessions for which this structure contains information.

`UniqueAdapterId`

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID).

## Remarks
You must implement this class if the adapter supports target portal hopping. Otherwise, it is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsimgt.h (include Iscsimgt.h) |