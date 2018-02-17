---
UID: NF:icm.WcsCreateIccProfile
title: WcsCreateIccProfile function
author: windows-driver-content
description: The WcsCreateIccProfile function converts a WCS profile into an ICC profile.
old-location: print\wcscreateiccprofile.htm
old-project: print
ms.assetid: fbe37d6c-9b91-46d8-9d29-1de3ef542c19
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: WcsCreateIccProfile function [Print Devices], WcsCreateIccProfile, print.wcscreateiccprofile, colorfnc_cb099d17-1109-4cb5-bbdc-76f1df13c60b.xml, icm/WcsCreateIccProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Included in Windows Vista and later.
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Mscms.dll
apiname:
-	WcsCreateIccProfile
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---


# WcsCreateIccProfile function
The <code>WcsCreateIccProfile</code> function converts a WCS profile into an ICC profile.

## Syntax

````
HPROFILE WcsCreateIccProfile(
  _In_ HPROFILE hWcsProfile,
  _In_ DWORD    dwOptions
);
````

## Parameters

`hWcsProfile`

A handle to the WCS color profile to transform. See Remarks.

`dwOptions`

A flag value that specifies the profile conversion options. This parameter must take the following value:





#### PREFER_WCS_PROFILES

Specifies that when WCS encounters an ICC profile, it should extract and use the WCS profiles that are contained in <b>WcsProfilesTag</b>.


## Return Value

None

## Remarks

The WCS profile that is to be translated must be a Device Model Profile (DMP) in combination with a Color Appearance Model Profile (CAMP) and a Gamut Map Model Profile (GMMP).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Included in Windows Vista and later.  |
| **Target Platform** | Universal |
| **Header** | icm.h |
| **Library** | Mscms.lib |
| **DLL** | Mscms.dll |