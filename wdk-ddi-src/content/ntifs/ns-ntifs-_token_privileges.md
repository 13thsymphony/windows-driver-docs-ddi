---
UID: NS:ntifs._TOKEN_PRIVILEGES
title: "_TOKEN_PRIVILEGES"
author: windows-driver-content
description: TOKEN_PRIVILEGES contains information about a set of privileges for an access token.
old-location: ifsk\token_privileges.htm
old-project: ifsk
ms.assetid: f2f4b2b7-bec0-42c3-904b-cbc74ca76bb3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_PRIVILEGES, TOKEN_PRIVILEGES structure [Installable File System Drivers], _TOKEN_PRIVILEGES, ifsk.token_privileges, ntifs/PTOKEN_PRIVILEGES, ntifs/TOKEN_PRIVILEGES, securitystructures_3da1d9ba-6fa7-4b16-bdd7-416890b57f7e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	ntifs.h
api_name:
-	TOKEN_PRIVILEGES
product: Windows
targetos: Windows
req.typenames: TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES
---

# _TOKEN_PRIVILEGES structure
TOKEN_PRIVILEGES contains information about a set of privileges for an access token.

## Syntax
```
typedef struct _TOKEN_PRIVILEGES {
  ULONG               PrivilegeCount;
  LUID_AND_ATTRIBUTES Privileges[ANYSIZE_ARRAY];
} TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES;
```

## Members


`PrivilegeCount`

Specifies the number of entries in the <b>Privileges</b> array.

`Privileges`

Specifies an array of LUID_AND_ATTRIBUTES structures. Each structure contains the LUID and attributes of a privilege.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>