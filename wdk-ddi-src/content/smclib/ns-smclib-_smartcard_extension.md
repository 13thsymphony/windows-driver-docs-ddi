---
UID : NS:smclib._SMARTCARD_EXTENSION
title : _SMARTCARD_EXTENSION
author : windows-driver-content
description : The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures.
old-location : smartcrd\smartcard_extension.htm
old-project : smartcrd
ms.assetid : 057d82a8-ce5d-416f-b753-297dcbac27b8
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : "*PSMARTCARD_EXTENSION, SMARTCARD_EXTENSION structure [Smart Card Reader Devices], PSMARTCARD_EXTENSION structure pointer [Smart Card Reader Devices], smartcrd.smartcard_extension, smclib/SMARTCARD_EXTENSION, PSMARTCARD_EXTENSION, _SMARTCARD_EXTENSION, SMARTCARD_EXTENSION, scstruct_399a1231-e161-450e-b5e2-6fc6035c865f.xml, smclib/PSMARTCARD_EXTENSION"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : smclib.h
req.include-header : Smclib.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSMARTCARD_EXTENSION, SMARTCARD_EXTENSION"
req.product : Windows 10 or later.
---

# _SMARTCARD_EXTENSION structure
The <b>SMARTCARD_EXTENSION</b> structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures.

## Syntax
````
typedef struct _SMARTCARD_EXTENSION {
  ULONG                     Version;
  VENDOR_ATTR               VendorAttr;
  NTSTATUS                  (*ReaderFunction[16])(PSMARTCARD_EXTENSION);
  SCARD_CARD_CAPABILITIES   CardCapabilities;
  ULONG                     LastError;
  struct {
    PULONG Information;
    PUCHAR RequestBuffer;
    ULONG  RequestBufferLength;
    PUCHAR ReplyBuffer;
    ULONG  ReplyBufferLength;
  } IoRequest;
  ULONG                     MajorIoControlCode;
  ULONG                     MinorIoControlCode;
  POS_DEP_DATA              OsData;
  SCARD_READER_CAPABILITIES ReaderCapabilities;
  PREADER_EXTENSION         ReaderExtension;
  SMARTCARD_REPLY           SmartcardReply;
  SMARTCARD_REQUEST         SmartcardRequest;
  T0_DATA                   T0;
  T1_DATA                   T1;
  ULONG                     Reserved[25];
} SMARTCARD_EXTENSION, *PSMARTCARD_EXTENSION;
````

## Members


`CardCapabilities`

Contains capabilities of the inserted smart card.

`IoRequest`

A structure with the following members:

`LastError`

Not used.

`MajorIoControlCode`

Contains the major I/O control code.

`MinorIoControlCode`

Contains the minor I/O control code.

`OsData`

Contains information that is specific to the operating system and the driver type.

`PerfInfo`



`ReaderCapabilities`

Contains the capabilities of the keyboard reader.

`ReaderExtension`

Contains data that is specifc to the smart card reader.

`ReaderFunction`

A pointer to an array of callback functions for readers.

`Reserved`

Reserved for system use.

`SmartcardReply`

Contains data that comes from the reader.

`SmartcardRequest`

Contains the current command and the data that is sent to the smart card.

`T0`

Contains the data for use with the T=0 protocol.

`T1`

Contains the data that is used with the T=1 protocol.

`VendorAttr`

Contains information that identifies the reader driver, such as the vendor name, unit number, and serial number.

`Version`

Indicates the version of this structure.

## Remarks
This structure is passed to all callback functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | smclib.h (include Smclib.h) |