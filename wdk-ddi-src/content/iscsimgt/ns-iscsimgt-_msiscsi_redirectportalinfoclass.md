---
UID: NS:iscsimgt._MSiSCSI_RedirectPortalInfoClass
title: _MSiSCSI_RedirectPortalInfoClass
author: windows-driver-content
description: The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.
old-location: storage\msiscsi_redirectportalinfoclass.htm
old-project: storage
ms.assetid: fcddf029-748b-4300-9f87-a103d961918a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSiSCSI_RedirectPortalInfoClass, *PMSiSCSI_RedirectPortalInfoClass, MSiSCSI_RedirectPortalInfoClass
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
req.alt-api: MSiSCSI_RedirectPortalInfoClass
req.alt-loc: iscsimgt.h
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
req.typenames: *PMSiSCSI_RedirectPortalInfoClass, MSiSCSI_RedirectPortalInfoClass
---

# _MSiSCSI_RedirectPortalInfoClass structure



## -description
The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions.



## -syntax

````
typedef struct _MSiSCSI_RedirectPortalInfoClass {
  ULONGLONG                 UniqueAdapterId;
  ULONG                     SessionCount;
  ISCSI_RedirectSessionInfo RedirectSessionList[1];
} MSiSCSI_RedirectPortalInfoClass, *PMSiSCSI_RedirectPortalInfoClass;
````


## -struct-fields

### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID).


### -field SessionCount

The number of sessions for which this structure contains information.


### -field RedirectSessionList

An array of structures that contains as many ISCSI_RedirectSessionInfo structures as specified in the connection count.


## -remarks
You must implement this class if the adapter supports target portal hopping. Otherwise, it is optional.</p>