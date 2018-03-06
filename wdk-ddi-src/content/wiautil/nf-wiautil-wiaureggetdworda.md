---
UID: NF:wiautil.wiauRegGetDwordA
title: wiauRegGetDwordA function
author: windows-driver-content
description: The wiauRegGetDword function gets a DWORD value from the DeviceData section of the registry.
old-location: image\wiaureggetdword.htm
old-project: image
ms.assetid: 936a3a49-ec36-421f-8554-c9ad37907a6d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiaureggetdword, wiauFncs_a58ebb21-21ce-4815-9dd6-5a1906412a2f.xml, wiauRegGetDword, wiauRegGetDword function [Imaging Devices], wiauRegGetDwordA, wiauRegGetDwordW, wiautil/wiauRegGetDword
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiautil.h
api_name:
-	wiauRegGetDword
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauRegGetDwordA function
The <b>wiauRegGetDword</b> function gets a <b>DWORD</b> value from the <b>DeviceData</b> section of the registry.

## Syntax

````
HRESULT _stdcall wiauRegGetDword(
  _In_  HKEY   hkKey,
  _In_  PCTSTR pwszValueName,
  _Out_ DWORD  *pdwValue
);
````

## Parameters

`hkKey`

Specifies the registry key handle. This parameter should be set to the value pointed to by the <i>phkeyDeviceData </i>parameter when <a href="https://msdn.microsoft.com/library/windows/hardware/ff550179">wiauRegOpenData</a> returns.

`pszValueName`

TBD

`pdwValue`

Pointer to a memory location that receives the returned DWORD value.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550178">wiauRegGetStr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550179">wiauRegOpenData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauRegGetDword function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>