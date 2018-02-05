---
UID : NF:wudfddi.IWDFDevice3.WriteToHardware
title : IWDFDevice3::WriteToHardware method
author : windows-driver-content
description : The WriteToHardware method is used internally by the framework. Do not use.
old-location : wdf\iwdfdevice3_writetohardware.htm
old-project : wdf
ms.assetid : 55FBE72C-E74E-4116-9602-6D491592350F
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFDevice3::WriteToHardware, WriteToHardware method, wdf.iwdfdevice3_writetohardware, WriteToHardware method, IWDFDevice3 interface, wudfddi/IWDFDevice3::WriteToHardware, umdf.iwdfdevice3_writetohardware, WriteToHardware, IWDFDevice3, IWDFDevice3 interface, WriteToHardware method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : POWER_ACTION, *PPOWER_ACTION
req.product : Windows 10 or later.
---


# WriteToHardware method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WriteToHardware</b> method is used internally by the framework. Do not use.

## Syntax

````
void WriteToHardware(
  [in]           WDF_DEVICE_HWACCESS_TARGET_TYPE Type,
  [in]           WDF_DEVICE_HWACCESS_TARGET_SIZE Size,
  [in]           VOID                            *Address,
  [in]           SIZE_T                          Value,
  [in, optional] VOID                            *Buffer,
  [in, optional] ULONG                           Count
);
````

## Parameters

`Type`



`Size`



`Address`



`Value`



`Buffer`



`Count`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::WriteToHardware method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>