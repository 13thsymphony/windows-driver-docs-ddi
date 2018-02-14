---
UID: NS:hidpi._HIDP_BUTTON_CAPS
title: "_HIDP_BUTTON_CAPS"
author: windows-driver-content
description: The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button usage (or a set of buttons associated with a usage range).
old-location: hid\hidp_button_caps.htm
old-project: hid
ms.assetid: d3d77679-6749-4ef5-a8f2-91639587144a
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_HIDP_BUTTON_CAPS, PHIDP_BUTTON_CAPS, PHIDP_BUTTON_CAPS structure pointer [Human Input Devices], HIDP_BUTTON_CAPS, hidpi/PHIDP_BUTTON_CAPS, HIDP_BUTTON_CAPS structure [Human Input Devices], hid.hidp_button_caps, *PHIDP_BUTTON_CAPS, hidstrct_0fa7f0ef-afc7-482a-bcf0-c8c78c3d18f7.xml, hidpi/HIDP_BUTTON_CAPS"
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
-	HIDP_BUTTON_CAPS
product: Windows
targetos: Windows
req.typenames: HIDP_BUTTON_CAPS, *PHIDP_BUTTON_CAPS
---

# _HIDP_BUTTON_CAPS structure
The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage</a> (or a set of buttons associated with a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage range</a>).

## Syntax
````
typedef struct _HIDP_BUTTON_CAPS {
  USAGE   UsagePage;
  UCHAR   ReportID;
  BOOLEAN IsAlias;
  USHORT  BitField;
  USHORT  LinkCollection;
  USAGE   LinkUsage;
  USAGE   LinkUsagePage;
  BOOLEAN IsRange;
  BOOLEAN IsStringRange;
  BOOLEAN IsDesignatorRange;
  BOOLEAN IsAbsolute;
  ULONG   Reserved[10];
  union {
    struct {
      USAGE  UsageMin;
      USAGE  UsageMax;
      USHORT StringMin;
      USHORT StringMax;
      USHORT DesignatorMin;
      USHORT DesignatorMax;
      USHORT DataIndexMin;
      USHORT DataIndexMax;
    } Range;
    struct {
      USAGE  Usage;
      USAGE  Reserved1;
      USHORT StringIndex;
      USHORT Reserved2;
      USHORT DesignatorIndex;
      USHORT Reserved3;
      USHORT DataIndex;
      USHORT Reserved4;
    } NotRange;
  };
} HIDP_BUTTON_CAPS, *PHIDP_BUTTON_CAPS;
````

## Members


`BitField`

Contains the data fields (one or two bytes) associated with an input, output, or feature main item.

`IsAbsolute`

Specifies, if <b>TRUE</b>, that the button usage or usage range provides absolute data. Otherwise, if <b>IsAbsolute</b> is <b>FALSE</b>, the button data is the change in state from the previous value.

`IsAlias`

Indicates, if <b>TRUE</b>, that a button has a set of <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">aliased usages</a>. Otherwise, if <b>IsAlias</b> is <b>FALSE</b>, the button has only one usage.

`IsDesignatorRange`

Specifies, if <b>TRUE</b>, that the usage or usage range has a set of designators. Otherwise, if <b>IsDesignatorRange</b> is <b>FALSE</b>, the usage or usage range has zero or one designator.

`IsRange`

Specifies, if <b>TRUE</b>, that the structure describes a usage range. Otherwise, if <b>IsRange</b> is <b>FALSE</b>, the structure describes a single usage.

`IsStringRange`

Specifies, if <b>TRUE</b>, that the usage or usage range has a set of string descriptors. Otherwise, if <b>IsStringRange</b> is <b>FALSE</b>, the usage or usage range has zero or one string descriptor.

`LinkCollection`

Specifies the index of the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection array</a> that contains the usage or usage range. If <b>LinkCollection</b> is zero, the usage or usage range is contained in the top-level collection.

`LinkUsage`

Specifies the usage of the link collection that contains the usage or usage range. If <b>LinkCollection</b> is zero, <b>LinkUsage</b> specifies the usage of the top-level collection.

`LinkUsagePage`

Specifies the usage page of the link collection that contains the usage or usage range. If <b>LinkCollection</b> is zero, <b>LinkUsagePage</b> specifies the usage page of the top-level collection.

`ReportID`

Specifies the report ID of the HID report that contains the usage or usage range.

`Reserved`

Reserved for internal system use.

`UsagePage`

Specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> for a usage or usage range.

## Remarks
Clients obtain a <a href="https://msdn.microsoft.com/139324e5-4d46-4d00-9f5a-fd0313fc109a">button capability array</a> by calling <a href="..\hidpi\nf-hidpi-hidp_getbuttoncaps.md">HidP_GetButtonCaps</a> or <a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>. These routines return an array of HIDP_BUTTON_CAPS structures in a caller-allocated buffer. The required buffer length is specified in the <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure returned by <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>. 

For information about the capabilities of HID control values, see <a href="https://msdn.microsoft.com/228fab4f-ff90-43c5-bc68-26b29e8a7dd6">Collection Capability</a> and <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">Value Capability Arrays</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpi.h (include Hidpi.h) |

## See Also

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>



<a href="..\hidpi\nf-hidpi-hidp_getvaluecaps.md">HidP_GetValueCaps</a>



<a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>



<a href="..\hidpi\ns-hidpi-_hidp_value_caps.md">HIDP_VALUE_CAPS</a>



<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>



<a href="..\hidpi\nf-hidpi-hidp_getbuttoncaps.md">HidP_GetButtonCaps</a>



<a href="..\hidpi\nf-hidpi-hidp_getspecificvaluecaps.md">HidP_GetSpecificValueCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_BUTTON_CAPS structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>