---
UID : NF:wdfverifier.WdfVerifierDbgBreakPoint
title : WdfVerifierDbgBreakPoint function
author : windows-driver-content
description : The WdfVerifierDbgBreakPoint function breaks into a kernel debugger, if a debugger is running.
old-location : wdf\wdfverifierdbgbreakpoint.htm
old-project : wdf
ms.assetid : 55b8a6de-f20b-4d2d-8235-4837bc4a0d7d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfverifier/WdfVerifierDbgBreakPoint, wdf.wdfverifierdbgbreakpoint, WdfVerifierDbgBreakPoint, kmdf.wdfverifierdbgbreakpoint, WdfVerifierDbgBreakPoint function, DFDebugRef_e59a7661-75d0-49ac-bac3-a5845cb78226.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfverifier.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_USB_REQUEST_COMPLETION_PARAMS, WDF_USB_REQUEST_COMPLETION_PARAMS"
req.product : Windows 10 or later.
---


# WdfVerifierDbgBreakPoint function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger, if a debugger is running.

## Syntax

````
VOID WdfVerifierDbgBreakPoint(void);
````

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:
<ul>
<li><b>DbgBreakOnError</b> is set to a non-zero value in the registry.</li>
<li><b>VerifierOn</b> is set to a non-zero value and <b>DbgBreakOnError</b> is not set.
								</li>
<li>Driver Verifier is enabled, the  driver was built with framework version 1.9 or later, and neither <b>VerifierOn</b> nor <b>DbgBreakOnError</b> is set.</li>
</ul>For more information about registry entries that you can use to debug your driver, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/registry-values-for-debugging-kmdf-drivers">Registry Entries for Debugging Framework-Based Drivers</a>.

For more information about debugging your driver, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/debugging-driver-installation">Debugging a KMDF Driver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfverifier.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfverifier\nf-wdfverifier-wdfverifierkebugcheck.md">WdfVerifierKeBugCheck</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfVerifierDbgBreakPoint function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>