---
UID: NF:hidpi.HidP_MaxDataListLength
title: HidP_MaxDataListLength function
author: windows-driver-content
description: The HidP_MaxDataListLength routine returns the maximum number of HIDP_DATA structures that HidP_GetData can return for a specified type of HID report and a specified top-level collection.
old-location: hid\hidp_maxdatalistlength.htm
old-project: hid
ms.assetid: 525a44a5-4271-4079-917e-48eb679cb96d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidpi/HidP_MaxDataListLength, hid.hidp_maxdatalistlength, HidP_MaxDataListLength, hidfunc_2c103c6f-6177-47b3-9d52-9e15c97d758d.xml, HidP_MaxDataListLength routine [Human Input Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_MaxDataListLength
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---


# HidP_MaxDataListLength function
The <b>HidP_MaxDataListLength</b> routine returns the maximum number of <a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a> structures that <a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a> can return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

## Syntax

````
ULONG __stdcall HidP_MaxDataListLength(
  _In_ HIDP_REPORT_TYPE     ReportType,
  _In_ PHIDP_PREPARSED_DATA PreparsedData
);
````

## Parameters

`ReportType`

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the report type.

`PreparsedData`

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## Return Value

If successful, <b>HidP_MaxDataListLength</b> returns the maximum number of <a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a> structures that <a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a> might return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. Otherwise, the routine returns zero, which indicates that either the report type or the preparsed data is not valid.

## Remarks

User-mode applications or kernel-mode drivers call <b>HidP_MaxDataListLength</b> to determine the maximum number of  <a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a> structures that <b>HidP_GetData</b> can return.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | hidpi.h (include Hidpi.h) |
| **Library** | Hidparse.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\hidpi\nf-hidpi-hidp_setdata.md">HidP_SetData</a>



<a href="..\hidpi\ns-hidpi-_hidp_data.md">HIDP_DATA</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>



<a href="..\hidpi\nf-hidpi-hidp_getdata.md">HidP_GetData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_MaxDataListLength routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>