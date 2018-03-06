---
UID: NF:wdfdevice.WdfDeviceGetHardwareRegisterMappedAddress
title: WdfDeviceGetHardwareRegisterMappedAddress function
author: windows-driver-content
description: A driver calls WdfDeviceGetHardwareRegisterMappedAddress to get the user-mode mapped address of the memory resource it mapped previously using WdfDeviceMapIoSpace.
old-location: wdf\wdfdevicegethardwareregistermappedaddress.htm
old-project: wdf
ms.assetid: 4D172D39-0D28-4950-B428-330D5B4D0654
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceGetHardwareRegisterMappedAddress, WdfDeviceGetHardwareRegisterMappedAddress function, wdf.wdfdevicegethardwareregistermappedaddress, wdfdevice/WdfDeviceGetHardwareRegisterMappedAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDeviceGetHardwareRegisterMappedAddress
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetHardwareRegisterMappedAddress function
<p class="CCE_Message">[Applies to UMDF only]

A driver calls <b>WdfDeviceGetHardwareRegisterMappedAddress</b> to get the user-mode mapped address of the memory resource it mapped previously using <a href="..\wdfdevice\nf-wdfdevice-wdfdevicemapiospace.md">WdfDeviceMapIoSpace</a>.

## Syntax

````
PVOID WdfDeviceGetHardwareRegisterMappedAddress(
  _In_ WDFDEVICE Device,
  _In_ PVOID     PseudoBaseAddress
);
````

## Parameters

`Device`

A handle to a framework device object.

`PseudoBaseAddress`

The address of a location that receives a pointer to the pseudo base address.


## Return Value

User-mode base address of the resources mapped earlier using <a href="..\wdfdevice\nf-wdfdevice-wdfdevicemapiospace.md">WdfDeviceMapIoSpace</a>.

## Remarks

This function is the UMDF version 2 equivalent of <a href="https://msdn.microsoft.com/94852404-301F-4C09-81D2-CEDEECFCD6BD">IWDFDevice3::GetHardwareRegisterMappedAddress</a>.

After the driver calls <b>WdfDeviceGetHardwareRegisterMappedAddress</b>, it can access the user-mode address directly to read and write to the register.


<div class="alert"><b>Note</b>  This is not the recommended approach for accessing registers because it prevents UMDF from doing any validation on the access.</div>
<div> </div>


If you do use <b>WdfDeviceGetHardwareRegisterMappedAddress</b>, you must set the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>.  For more information about UMDF  INF directives, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | WUDFx02000.lib |
| **DLL** | WUDFx02000.dll |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicemapiospace.md">WdfDeviceMapIoSpace</a>



<a href="https://msdn.microsoft.com/94852404-301F-4C09-81D2-CEDEECFCD6BD">IWDFDevice3::GetHardwareRegisterMappedAddress</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetHardwareRegisterMappedAddress function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>