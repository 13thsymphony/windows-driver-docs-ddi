---
UID: NS:ntddk._WHEA_ERROR_RECORD_HEADER_VALIDBITS
title: "_WHEA_ERROR_RECORD_HEADER_VALIDBITS"
author: windows-driver-content
description: The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_HEADER structure contain valid data.
old-location: whea\whea_error_record_header_validbits.htm
old-project: whea
ms.assetid: b16dd19f-1a67-4066-9dae-b36ff6f44d43
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: whea.whea_error_record_header_validbits, PWHEA_ERROR_RECORD_HEADER_VALIDBITS, *PWHEA_ERROR_RECORD_HEADER_VALIDBITS, WHEA_ERROR_RECORD_HEADER_VALIDBITS union [WHEA Drivers and Applications], ntddk/WHEA_ERROR_RECORD_HEADER_VALIDBITS, whearef_66b0c2f7-6fad-4cdb-ac15-f4d942d208e1.xml, _WHEA_ERROR_RECORD_HEADER_VALIDBITS, PWHEA_ERROR_RECORD_HEADER_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD_HEADER_VALIDBITS, ntddk/PWHEA_ERROR_RECORD_HEADER_VALIDBITS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_ERROR_RECORD_HEADER_VALIDBITS
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_RECORD_HEADER_VALIDBITS, WHEA_ERROR_RECORD_HEADER_VALIDBITS"
---

# _WHEA_ERROR_RECORD_HEADER_VALIDBITS structure
The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> structure contain valid data.

## Syntax
````
typedef union _WHEA_ERROR_RECORD_HEADER_VALIDBITS {
  struct {
    ULONG PlatformId  :1;
    ULONG Timestamp  :1;
    ULONG PartitionId  :1;
    ULONG Reserved  :29;
  };
  ULONG  AsULONG;
} WHEA_ERROR_RECORD_HEADER_VALIDBITS, *PWHEA_ERROR_RECORD_HEADER_VALIDBITS;
````

## Members


`AsULONG`

A ULONG representation of the contents of the WHEA_ERROR_RECORD_HEADER_VALIDBITS union.

`DUMMYSTRUCTNAME`



## Remarks
A WHEA_ERROR_RECORD_HEADER_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> structure.

<div class="alert"><b>Important</b>  After the release of Windows Server 2008, it was discovered that the <b>Timestamp</b> and <b>PlatformId</b> members of the WHEA_ERROR_RECORD_HEADER_VALIDBITS union are defined in the incorrect order. This topic now defines the correct order for these members.<p class="note">If you build your <a href="https://msdn.microsoft.com/fb559ac3-1f8d-48b7-8ebe-018623ab8d09">Windows hardware error architecture (WHEA) user-mode application</a> or <a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">platform-specific hardware error driver (PSHED) plug-in</a> with the header files from the Windows Server 2008 version of the WDK or Windows SDK, you will have trouble only if your application or PSHED plug-in accesses the <b>Timestamp</b> and <b>PlatformId</b> members directly when it processes the contents of a WHEA_ERROR_RECORD_HEADER structure. When you test these bits in the <b>AsULONG </b>member through the bitfield constants that are described in the following list, you will always produce the correct results.

<p class="note">This problem has been fixed in the Windows 7 version of the WDK and SDK.

</div>
<div> </div>
The following bitfield constants can be used to test the bits in the <b>AsULONG </b>member:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD_HEADER_VALIDBITS union%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>