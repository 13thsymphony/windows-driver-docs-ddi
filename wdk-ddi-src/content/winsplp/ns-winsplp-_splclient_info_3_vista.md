---
UID: NS:winsplp._SPLCLIENT_INFO_3_VISTA
title: "_SPLCLIENT_INFO_3_VISTA"
author: windows-driver-content
description: Contains a super-set of the information in both a SPLCLIENT_INFO_1 and SPLCLIENT_INFO_2 structure. It also contains additional information needed by the provider.
old-location: print\splclient_info_3_vista.htm
old-project: print
ms.assetid: 076ECB20-CFAD-4A16-9B01-6936E0DD7E50
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: SPLCLIENT_INFO_3_VISTA structure [Print Devices], SPLCLIENT_INFO_3_VISTA, _SPLCLIENT_INFO_3_VISTA, winsplp/SPLCLIENT_INFO_3_VISTA, print.splclient_info_3_vista, *LPSPLCLIENT_INFO_3, SPLCLIENT_INFO_3, *PSPLCLIENT_INFO_3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
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
-	Winsplp.h
apiname:
-	SPLCLIENT_INFO_3_VISTA
product: Windows
targetos: Windows
req.typenames: SPLCLIENT_INFO_3_VISTA
req.product: Windows 10 or later.
---

# _SPLCLIENT_INFO_3_VISTA structure
Contains a super-set of the information in both a <a href="https://docs.microsoft.com/en-us/dotnet/core/rid-catalog">SPLCLIENT_INFO_1</a> and <b>SPLCLIENT_INFO_2</b> structure. It also contains additional information needed by the provider.

## Syntax
````
typedef struct _SPLCLIENT_INFO_3_VISTA {
  UINT             cbSize;
  DWORD            dwFlags;
  DWORD            dwSize;
  PWSTR            pMachineName;
  PWSTR            pUserName;
  DWORD            dwBuildNum;
             DWORD dwMajorVersion;
  DWORD            dwMinorVersion;
  WORD             wProcessorArchitecture;
  UINT64           hSplPrinter;
} SPLCLIENT_INFO_3_VISTA;
````

## Members


`cbSize`

Specifies the size in bytes of this structure.

`dwBuildNum`

Specifies the client build number.

`dwFlags`

Specifies open printer additional flags to the provider.

`dwMajorVersion`

Specifies the major version of the client machine.

`dwMinorVersion`

Specifies the minor version of the client machine.

`dwSize`

Reserved. Used for compatibility with the <a href="https://docs.microsoft.com/en-us/dotnet/core/rid-catalog">SPLCLIENT_INFO_1</a> structure.

`hSplPrinter`

Specifies the server-side handle to be used for direct calls.

`pMachineName`

Specifies the client machine name.

`pUserName`

Specifies the client user name.

`wProcessorArchitecture`

Specifies the client machine architecture.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h |