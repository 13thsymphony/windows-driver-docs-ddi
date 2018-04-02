---
UID: NF:ntifs.RtlIsValidOemCharacter
title: RtlIsValidOemCharacter function
author: windows-driver-content
description: The RtlIsValidOemCharacter routine determines if the specified Unicode character can be mapped to a valid OEM character.
old-location: ifsk\rtlisvalidoemcharacter.htm
old-project: ifsk
ms.assetid: 76040e0d-a43c-4e3d-aaaa-b84fc2613603
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlIsValidOemCharacter, RtlIsValidOemCharacter routine [Installable File System Drivers], ifsk.rtlisvalidoemcharacter, ntifs/RtlIsValidOemCharacter, rtlref_ebbaa5fc-63da-4eef-b8ac-be10a6e062a0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIsValidOemCharacter
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlIsValidOemCharacter function
The <b>RtlIsValidOemCharacter</b> routine determines if the specified Unicode character can be mapped to a valid OEM character.

## Syntax

```
NTSYSAPI BOOLEAN RtlIsValidOemCharacter(
  PWCHAR Char
);
```

## Parameters

`Char`

Pointer to the character. If the character can be mapped to a valid OEM character, this parameter receives the Unicode translation of the valid OEM character.


## Return Value

<b>RtlIsValidOemCharacter</b> returns <b>TRUE</b> if the character can be mapped to a valid OEM character, <b>FALSE</b> otherwise.

## Remarks

<b>RtlIsValidOemCharacter</b> translates the Unicode character at <i>Char</i> using the OEM code page that was installed as the current system code page at system boot time, and converts the translated character to uppercase. <b>RtlIsValidOemCharacter</b> checks that the resulting character is a valid OEM character.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows 2000 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553153">RtlOemStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553272">RtlUnicodeToOemN</a>