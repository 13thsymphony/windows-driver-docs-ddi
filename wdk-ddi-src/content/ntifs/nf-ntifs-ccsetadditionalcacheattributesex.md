---
UID: NF:ntifs.CcSetAdditionalCacheAttributesEx
title: CcSetAdditionalCacheAttributesEx function
author: windows-driver-content
description: Call the CcSetAdditionalCacheAttributesEx routine to enable extended cache behavior on a cached file.
old-location: ifsk\ccsetadditionalcacheattributesex.htm
old-project: ifsk
ms.assetid: 187719CD-5F0C-4AFD-BC00-ECD3C29A118F
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/CcSetAdditionalCacheAttributesEx, CcSetAdditionalCacheAttributesEx, CcSetAdditionalCacheAttributesEx routine [Installable File System Drivers], ifsk.ccsetadditionalcacheattributesex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcSetAdditionalCacheAttributesEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcSetAdditionalCacheAttributesEx function
Call the <b>CcSetAdditionalCacheAttributesEx</b> routine to enable extended cache behavior on a cached file.

## Syntax

````
VOID CcSetAdditionalCacheAttributesEx(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        Flags
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file.

`Flags`

Behavior flags to set for <i>FileObject</i>. Currently, only the  <b>AGGRESSIVE_UNMAP_BEHIND</b> flag is available. Setting this flag will allow the cache manager to optimize memory usage when modified writes are disabled for a file object.


## Return Value

None

## Remarks

<b>CcSetAdditionalCacheAttributesEx</b> can be called any time after calling <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>



<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetAdditionalCacheAttributesEx routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>