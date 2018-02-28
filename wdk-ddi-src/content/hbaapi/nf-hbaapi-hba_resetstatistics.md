---
UID: NF:hbaapi.HBA_ResetStatistics
title: HBA_ResetStatistics function
author: windows-driver-content
description: The HBA_ResetStatistics routine resets the statistics counters for the indicated port and HBA.
old-location: storage\hba_resetstatistics.htm
old-project: storage
ms.assetid: 4e889905-9c5e-446c-8d0e-09e445f7c1a4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HBA_ResetStatistics, HBA_ResetStatistics routine [Storage Devices], fibreHBA_rtns_37577fde-9a33-4fd7-8e80-abbd7458b4ef.xml, hbaapi/HBA_ResetStatistics, storage.hba_resetstatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_ResetStatistics
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_ResetStatistics function
The <b>HBA_ResetStatistics</b> routine resets the statistics counters for the indicated port and HBA.

## Syntax

````
void HBA_API HBA_ResetStatistics(
  _In_ HBA_HANDLE HbaHandle,
  _In_ HBA_UINT32 PortIndex
);
````

## Parameters

`Handle`

TBD

`PortIndex`

Indicates for which port on the HBA the statistics counters should be reset.


## Return Value

None

## Remarks

The <b>HBA_ResetStatistics</b> routine serves similar purpose to the <b>ResetStatistics</b> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562501">MSFC_FibrePortHBAMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562501">MSFC_FibrePortHBAMethods WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_ResetStatistics routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>