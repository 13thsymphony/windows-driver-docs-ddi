---
UID: NS:iscsiop._ISCSI_Persistent_Login
title: "_ISCSI_Persistent_Login"
author: windows-driver-content
description: The ISCSI_Persistent_Login structure defines a persistent logon that the operating system initiates automatically when the computer boots up.
old-location: storage\iscsi_persistent_login.htm
old-project: storage
ms.assetid: c43ee3dd-552a-41ab-9b4f-01611e44f453
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSI_Persistent_Login, ISCSI_Persistent_Login, ISCSI_Persistent_Login structure [Storage Devices], PISCSI_Persistent_Login, PISCSI_Persistent_Login structure pointer [Storage Devices], _ISCSI_Persistent_Login, iscsiop/ISCSI_Persistent_Login, iscsiop/PISCSI_Persistent_Login, storage.iscsi_persistent_login, structs-iSCSI_86b54cb5-df75-47c0-8dc4-337a5f46bea0.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	ISCSI_Persistent_Login
product: Windows
targetos: Windows
req.typenames: ISCSI_Persistent_Login, *PISCSI_Persistent_Login
---

# _ISCSI_Persistent_Login structure
The ISCSI_Persistent_Login structure defines a persistent logon that the operating system initiates automatically when the computer boots up.

## Syntax
````
typedef struct _ISCSI_Persistent_Login {
  WCHAR               TargetName[223 + 1];
  ULONGLONG           SecurityFlags;
  ULONG               InitiatorPortNumber;
  ULONG               UsernameSize;
  BOOLEAN             IsInformationalSession;
  USHORT              UniqueIdForISID;
  ISCSI_TargetPortal  TargetPortal;
  ISCSI_LoginOptions  LoginOptions;
  ISCSI_TargetMapping TargetMapping;
  UCHAR               Username[1];
} ISCSI_Persistent_Login, *PISCSI_Persistent_Login;
````

## Members


`TargetName`

A wide character string that indicates the name of the target with which the iSCSI initiator service establishes a persistent logon when it restarts.

`SecurityFlags`

A bitwise OR of security flags that indicate the security requirements of the target that is specified in the persistent logon. For a list of possible values for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.

`InitiatorPortNumber`

The port number on the initiator side to perform the logon operation through.

`UsernameSize`

The size, in bytes, of the string in <b>Username</b>.

`IsInformationalSession`

A Boolean value that indicates whether the persistent logon is configured to establish a purely informational session. If this member is <b>TRUE</b>, the persistent logon is configured to establish a purely informational session.

`UniqueIdForISID`

Portal to use for initial connection

`TargetPortal`

An <a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a> structure that specifies which target portal to use for the initial logon connection.

`LoginOptions`

An <a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a> structure that specifies the characteristics of the persistent logon session.

`TargetMapping`

An <a href="..\iscsidef\ns-iscsidef-_iscsi_targetmapping.md">ISCSI_TargetMapping</a> structure that defines the target mappings.

`Username`

A variable-length array of characters that specifies the challenge handshake authentication protocol user name (CHAP_N) to use when the initiator is authenticating the target. The number of elements in the array is specified by the <b>UsernameSize</b> field.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_targetmapping.md">ISCSI_TargetMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561556">ISCSI_Persistent_Login WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a>