---
UID: NS:hidpddi._HIDP_COLLECTION_DESC
title: "_HIDP_COLLECTION_DESC"
author: windows-driver-content
description: Contains the information of a top-level-collection. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_collection_desc.htm
old-project: hid
ms.assetid: 4B044635-1088-4CED-87C7-4385E565A54A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PHIDP_COLLECTION_DESC structure pointer [Human Input Devices], hidpddi/PHIDP_COLLECTION_DESC, hidpddi/HIDP_COLLECTION_DESC, _HIDP_COLLECTION_DESC, PHIDP_COLLECTION_DESC, *PHIDP_COLLECTION_DESC, hid.hidp_collection_desc, HIDP_COLLECTION_DESC, HIDP_COLLECTION_DESC structure [Human Input Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hidpddi.h
apiname:
-	HIDP_COLLECTION_DESC
product: Windows
targetos: Windows
req.typenames: HIDP_COLLECTION_DESC, *PHIDP_COLLECTION_DESC
---

# _HIDP_COLLECTION_DESC structure
Contains the information of a top-level-collection. This structure is used in the <a href="..\hidpddi\nf-hidpddi-hidp_getcollectiondescription.md">HidP_GetCollectionDescription</a> call.

## Syntax
````
typedef struct _HIDP_COLLECTION_DESC {
  USAGE                             UsagePage;
  USAGE                             Usage;
  UCHAR                             CollectionNumber;
  UCHAR                             Reserved[15];
  USHORT                            InputLength;
  USHORT                            OutputLength;
  USHORT                            FeatureLength;
  USHORT                            PreparsedDataLength;
  PHIDP_PREPARSED_DATA              PreparsedData;
} HIDP_COLLECTION_DESC, *PHIDP_COLLECTION_DESC;
````

## Members


`CollectionNumber`

The index of the collection in the array of  <b>HIDP_COLLECTION_DESC</b> structure. This is a 1-based value.

`FeatureLength`

The maximum length of a feature report of this collection.

`InputLength`

The maximum length of an input report of this collection.

`OutputLength`

The maximum length of an output report of this collection.

`PreparsedData`

A pointer to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a> structure that contains a top-level collection's preparsed data.

`PreparsedDataLength`

The length of the preparsed data pointed to by <i>PreparsedData</i>.

`Reserved`

Reserved for internal system use. Must be 0.

`Usage`

Indicates a usage ID.

`UsagePage`

Specifies the usage page of the usage ID specified by <b>Usage</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpddi.h (include Hidpddi.h) |

## See Also

<a href="..\hidpddi\nf-hidpddi-hidp_getcollectiondescription.md">HidP_GetCollectionDescription</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_COLLECTION_DESC structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>