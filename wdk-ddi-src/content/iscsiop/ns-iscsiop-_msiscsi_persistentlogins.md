---
UID: NS:iscsiop._MSiSCSI_PersistentLogins
title: "_MSiSCSI_PersistentLogins"
author: windows-driver-content
description: The MSiSCSI_PersistentLogins structure contains the list of persistent target logon sessions.
old-location: storage\msiscsi_persistentlogins.htm
old-project: storage
ms.assetid: c735d9c9-8e87-4a80-af1d-c97d457f78fa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: iscsiop/MSiSCSI_PersistentLogins, *PMSiSCSI_PersistentLogins, PMSiSCSI_PersistentLogins structure pointer [Storage Devices], _MSiSCSI_PersistentLogins, structs-iSCSI_150a8086-8025-4140-9fdb-75d05bfcb0ac.xml, MSiSCSI_PersistentLogins, MSiSCSI_PersistentLogins structure [Storage Devices], iscsiop/PMSiSCSI_PersistentLogins, storage.msiscsi_persistentlogins, PMSiSCSI_PersistentLogins
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	MSiSCSI_PersistentLogins
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_PersistentLogins, MSiSCSI_PersistentLogins"
---

# _MSiSCSI_PersistentLogins structure
The MSiSCSI_PersistentLogins structure contains the list of persistent target logon sessions.

## Syntax
````
typedef struct _MSiSCSI_PersistentLogins {
  ULONG                  PersistentLoginCount;
  ULONG                  Reserved;
  ISCSI_Persistent_Login PersistentLogins[1];
} MSiSCSI_PersistentLogins, *PMSiSCSI_PersistentLogins;
````

## Members


`PersistentLoginCount`

The number of persistent target logon sessions that the initiator manages.

`PersistentLogins`

A variable length array of <a href="..\iscsiop\ns-iscsiop-_iscsi_persistent_login.md">ISCSI_Persistent_Login</a> structures, each of which contains information that is associated with a particular persistent logon session that the initiator maintains.

`Reserved`

Reserved for Microsoft use only.

## Remarks
Miniport drivers that manage iSCSI initiators automatically establish persistent logon sessions as soon as they are loaded into the storage driver stack. This guarantees that targets for which the initiator maintains persistent logon sessions will be available to the system as early in the startup process as possible. You must implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_iscsi_persistent_login.md">ISCSI_Persistent_Login</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561556">ISCSI_Persistent_Login WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561556">ISCSI_Persistent_Login WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_PersistentLogins structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>