---
UID: NF:wdfchildlist.WDF_CHILD_RETRIEVE_INFO_INIT
title: WDF_CHILD_RETRIEVE_INFO_INIT function
author: windows-driver-content
description: The WDF_CHILD_RETRIEVE_INFO_INIT function initializes a WDF_CHILD_RETRIEVE_INFO structure.
old-location: wdf\wdf_child_retrieve_info_init.htm
old-project: wdf
ms.assetid: e41a656c-c507-45ca-a232-6926ace3c9d9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_f647d2ee-4714-49b9-9ba4-18488fd66628.xml, WDF_CHILD_RETRIEVE_INFO_INIT, WDF_CHILD_RETRIEVE_INFO_INIT function, kmdf.wdf_child_retrieve_info_init, wdf.wdf_child_retrieve_info_init, wdfchildlist/WDF_CHILD_RETRIEVE_INFO_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfchildlist.h
api_name:
-	WDF_CHILD_RETRIEVE_INFO_INIT
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---


# WDF_CHILD_RETRIEVE_INFO_INIT function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_RETRIEVE_INFO_INIT</b> function initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure.

## Syntax

````
VOID WDF_CHILD_RETRIEVE_INFO_INIT(
  _Out_ PWDF_CHILD_RETRIEVE_INFO                     Info,
  _In_  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
);
````

## Parameters

`Info`

A pointer to a driver-supplied <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure.

`IdentificationDescription`

A pointer to a driver-supplied <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_RETRIEVE_INFO_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>