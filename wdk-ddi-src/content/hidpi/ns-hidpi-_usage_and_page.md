---
UID: NS:hidpi._USAGE_AND_PAGE
title: "_USAGE_AND_PAGE"
author: windows-driver-content
description: The USAGE_AND_PAGE structure specifies the usage page and usage ID of a HID control.
old-location: hid\usage_and_page.htm
old-project: hid
ms.assetid: 48716117-c539-4436-a81f-4b05c9a8cb7d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: USAGE_AND_PAGE, PUSAGE_AND_PAGE structure pointer [Human Input Devices], _USAGE_AND_PAGE, hidpi/USAGE_AND_PAGE, hidstrct_cbb3e4f3-5409-406c-9114-d8455e505497.xml, USAGE_AND_PAGE structure [Human Input Devices], *PUSAGE_AND_PAGE, PUSAGE_AND_PAGE, hidpi/PUSAGE_AND_PAGE, hid.usage_and_page
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidpi.h
apiname:
-	USAGE_AND_PAGE
product: Windows
targetos: Windows
req.typenames: "*PUSAGE_AND_PAGE, USAGE_AND_PAGE"
---

# _USAGE_AND_PAGE structure
The USAGE_AND_PAGE structure specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> and <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a> of a HID control.

## Syntax
````
typedef struct _USAGE_AND_PAGE {
  USAGE Usage;
  USAGE UsagePage;
} USAGE_AND_PAGE, *PUSAGE_AND_PAGE;
````

## Members


`Usage`

Specifies a usage ID within the usage page specified by <b>UsagePage</b>.

`UsagePage`

Specifies a usage page.

## Remarks
The<b> HidP_IsSameUsageAndPage</b> macro determines if two <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">extended usages</a>, represented by <b>USAGE_AND_PAGE</b> structures, are equal.


<pre class="syntax">BOOLEAN HidP_IsSameUsageAndPage(
   USAGE_AND_PAGE u1,
   USAGE_AND_PAGE u2
);
</pre>


<i>u1</i>

<b>USAGE_AND_PAGE</b>

Specifies an extended usage

<i>u2</i>

<b>USAGE_AND_PAGE</b>

Specifies an extended usage

<b>Return Value</b>

<b>BOOLEAN</b>

<b>HidP_IsSameUsageAndPage</b> returns one of the following status values:

<b>TRUE</b>

Usage <i>u1</i> is the same as usage <i>u2</i>.

<b>FALSE</b>

Usage <i>u1</i> is different than usage <i>u2</i>.

As defined by the USB HID standard, an extended usage is a 32-bit unsigned value. The high-order 16 bits specify the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a>, and lower-order 16 bits specify the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpi.h (include Hidpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20USAGE_AND_PAGE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>