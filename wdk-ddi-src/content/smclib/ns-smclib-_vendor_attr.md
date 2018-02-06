---
UID: NS:smclib._VENDOR_ATTR
title: "_VENDOR_ATTR"
author: windows-driver-content
description: The VENDOR_ATTR structure defines the data that is stored in the VendorAttr member of the SMARTCARD_EXTENSION structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number.
old-location: smartcrd\vendor_attr.htm
old-project: smartcrd
ms.assetid: f166ced5-2d63-4e35-af77-78ca80c888d7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: smclib/PVENDOR_ATTR, PVENDOR_ATTR, VENDOR_ATTR, VENDOR_ATTR structure [Smart Card Reader Devices], *PVENDOR_ATTR, scstruct_dfa4be20-d572-46d6-aff7-c4c16d930c7f.xml, smartcrd.vendor_attr, _VENDOR_ATTR, PVENDOR_ATTR structure pointer [Smart Card Reader Devices], smclib/VENDOR_ATTR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	smclib.h
apiname:
-	VENDOR_ATTR
product: Windows
targetos: Windows
req.typenames: VENDOR_ATTR, *PVENDOR_ATTR
req.product: Windows 10 or later.
---

# _VENDOR_ATTR structure
The VENDOR_ATTR structure defines the data that is stored in the <b>VendorAttr</b> member of the <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a> structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number.

## Syntax
````
typedef struct _VENDOR_ATTR {
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } VendorName;
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } IfdType;
  ULONG  UnitNo;
  struct {
    USHORT BuildNumber;
    UCHAR  VersionMinor;
    UCHAR  VersionMajor;
  } IfdVersion;
  struct {
    USHORT Length;
    UCHAR  Buffer[MAXIMUM_ATTR_STRING_LENGTH];
  } IfdSerialNo;
  ULONG  Reserved[25];
} VENDOR_ATTR, *PVENDOR_ATTR;
````

## Members


`IfdSerialNo`

A structure with the following members:

`IfdType`

A structure with the following members:

`IfdVersion`

A structure with the following members:

`Reserved`

Reserved for system use.

`UnitNo`

Contains the zero-based number of this unit. Because you can have more than one reader of this kind installed, <b>UnitNo</b> can distinguish the readers. This member is required.

`VendorName`

A structure with the following members:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smclib.h (include Smclib.h) |