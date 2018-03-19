---
UID: NC:minitape.TAPE_VERIFY_INQUIRY_ROUTINE
title: TAPE_VERIFY_INQUIRY_ROUTINE
author: windows-driver-content
description: TAPE_VERIFY_INQUIRY_ROUTINE determines whether the tape miniclass driver recognizes and supports a given device. This routine is required.
old-location: storage\tapeminiverifyinquiry.htm
old-project: storage
ms.assetid: ed216b13-546a-4d0c-82db-79c175912556
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "(*TAPE_VERIFY_INQUIRY_ROUTINE), (*TAPE_VERIFY_INQUIRY_ROUTINE) routine [Storage Devices], TAPE_VERIFY_INQUIRY_ROUTINE, minitape/(*TAPE_VERIFY_INQUIRY_ROUTINE), storage.tapeminiverifyinquiry, tapemini_d8a92eee-8b82-4fac-b568-fbe40c906ec1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: minitape.h
req.include-header: Minitape.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	minitape.h
api_name:
-	(*TAPE_VERIFY_INQUIRY_ROUTINE)
product: Windows
targetos: Windows
req.typenames: PROCESSOR_NUMBER, *PPROCESSOR_NUMBER
---


# TAPE_VERIFY_INQUIRY_ROUTINE callback function
<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> determines whether the tape miniclass driver recognizes and supports a given device. This routine is required.

## Syntax

```
TAPE_VERIFY_INQUIRY_ROUTINE TapeVerifyInquiryRoutine;

BOOLEAN TapeVerifyInquiryRoutine(
  PINQUIRYDATA InquiryData,
  PMODE_CAPABILITIES_PAGE ModeCapabilitiesPage
)
{...}
```

## Parameters

`InquiryData`

Pointer to SCSI inquiry data for the device.

`ModeCapabilitiesPage`

Pointer to a MODE_CAPABILITIES_PAGE structure that contains low-level information about the device. The format of this structure is defined by the QIC 157 standard and is subject to change. The pointer is <b>NULL</b> if the tape device does not support a mode capabilities page.


## Return Value

<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> returns <b>TRUE</b> if the miniclass driver supports the device.

## Remarks

<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> examines the <i>InquiryData</i>, particularly the <b>VendorId</b> and <b>ProductId</b> members, to determine whether the tape miniclass driver supports the tape device. <i>TAPE_VERIFY_INQUIRY_ROUTINE</i> uses <a href="..\minitape\nf-minitape-tapeclasscomparememory.md">TapeClassCompareMemory</a> to compare ID strings against values the tape miniclass driver supports.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | minitape.h (include Minitape.h) |

## See Also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="..\minitape\nf-minitape-tapeclasscomparememory.md">TapeClassCompareMemory</a>