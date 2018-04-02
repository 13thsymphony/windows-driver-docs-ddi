---
UID: NE:wdm._KEY_INFORMATION_CLASS
title: "_KEY_INFORMATION_CLASS"
author: windows-driver-content
description: The KEY_INFORMATION_CLASS enumeration type represents the type of information to supply about a registry key.
old-location: kernel\key_information_class.htm
old-project: kernel
ms.assetid: cb531a0e-c934-4f3e-9b92-07eb3ab75673
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KEY_INFORMATION_CLASS, KEY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], KeyBasicInformation, KeyCachedInformation, KeyFlagsInformation, KeyFullInformation, KeyHandleTagsInformation, KeyNameInformation, KeyNodeInformation, KeyVirtualizationInformation, MaxKeyInfoClass, _KEY_INFORMATION_CLASS, kernel.key_information_class, sysenum_c64ec9c8-1eda-495a-8b4a-566607e29a78.xml, wdm/KEY_INFORMATION_CLASS, wdm/KeyBasicInformation, wdm/KeyCachedInformation, wdm/KeyFlagsInformation, wdm/KeyFullInformation, wdm/KeyHandleTagsInformation, wdm/KeyNameInformation, wdm/KeyNodeInformation, wdm/KeyVirtualizationInformation, wdm/MaxKeyInfoClass
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	KEY_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: KEY_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _KEY_INFORMATION_CLASS Enumeration
The <b>KEY_INFORMATION_CLASS</b> enumeration type represents the type of information to supply about a registry key.

## Syntax
```
typedef enum _KEY_INFORMATION_CLASS {
  KeyBasicInformation           ,
  KeyNodeInformation            ,
  KeyFullInformation            ,
  KeyNameInformation            ,
  KeyCachedInformation          ,
  KeyFlagsInformation           ,
  KeyVirtualizationInformation  ,
  KeyHandleTagsInformation      ,
  KeyTrustInformation           ,
  KeyLayerInformation           ,
  MaxKeyInfoClass
} KEY_INFORMATION_CLASS;
```

## Constants

<table>
            
                <tr>
                    <td>KeyBasicInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyNodeInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyFullInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyNameInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyCachedInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyFlagsInformation</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>KeyVirtualizationInformation</td>
                    <td>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>KeyHandleTagsInformation</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>KeyTrustInformation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KeyLayerInformation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>MaxKeyInfoClass</td>
                    <td>The maximum value in this enumeration type.</td>
                </tr>
</table>

## Remarks

Use the <b>KEY_INFORMATION_CLASS</b> values to specify the type of data to be supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routines.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>