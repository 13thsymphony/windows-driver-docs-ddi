---
UID: NE:wdm._ENLISTMENT_INFORMATION_CLASS
title: "_ENLISTMENT_INFORMATION_CLASS"
author: windows-driver-content
description: The ENLISTMENT_INFORMATION_CLASS enumeration identifies the type of information that the ZwSetInformationEnlistment routine can set and that the ZwQueryInformationEnlistment routine can retrieve for an enlistment object.
old-location: kernel\enlistment_information_class.htm
old-project: kernel
ms.assetid: d031e032-66e3-4697-8db1-67655cfc223d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ENLISTMENT_INFORMATION_CLASS, ENLISTMENT_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], EnlistmentBasicInformation, EnlistmentCrmInformation, EnlistmentRecoveryInformation, _ENLISTMENT_INFORMATION_CLASS, kernel.enlistment_information_class, ktm_ref_9bf2b9fa-5b9a-47fb-873c-6bd5f1930553.xml, wdm/ENLISTMENT_INFORMATION_CLASS, wdm/EnlistmentBasicInformation, wdm/EnlistmentCrmInformation, wdm/EnlistmentRecoveryInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	Wdm.h
api_name:
-	ENLISTMENT_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: ENLISTMENT_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _ENLISTMENT_INFORMATION_CLASS Enumeration
The <b>ENLISTMENT_INFORMATION_CLASS</b> enumeration identifies the type of information that the <a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a> routine can set and that the <a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a> routine can retrieve for an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.

## Syntax
````
typedef enum _ENLISTMENT_INFORMATION_CLASS { 
  EnlistmentBasicInformation     = 0,
  EnlistmentRecoveryInformation,
  EnlistmentCrmInformation
} ENLISTMENT_INFORMATION_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>EnlistmentBasicInformation</td>
                    <td>Information about an enlistment object is stored in an <a href="..\wdm\ns-wdm-_enlistment_basic_information.md">ENLISTMENT_BASIC_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>EnlistmentRecoveryInformation</td>
                    <td>A resource manager is setting or obtaining customized recovery information for an enlistment. To learn more about recovery information, see <a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>.</td>
                </tr>
            
                <tr>
                    <td>EnlistmentCrmInformation</td>
                    <td>Information about an enlistment object is stored in an <b>ENLISTMENT_CRM_INFORMATION</b> structure.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>



<a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>



<a href="..\wdm\ns-wdm-_enlistment_basic_information.md">ENLISTMENT_BASIC_INFORMATION</a>