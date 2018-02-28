---
UID: NS:smclib._SCARD_CARD_CAPABILITIES
title: "_SCARD_CARD_CAPABILITIES"
author: windows-driver-content
description: The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used.
old-location: smartcrd\scard_card_capabilities.htm
old-project: smartcrd
ms.assetid: 8cc223be-a692-4141-81f6-4cca9e2fccf1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PSCARD_CARD_CAPABILITIES, PSCARD_CARD_CAPABILITIES, PSCARD_CARD_CAPABILITIES structure pointer [Smart Card Reader Devices], SCARD_CARD_CAPABILITIES, SCARD_CARD_CAPABILITIES structure [Smart Card Reader Devices], _SCARD_CARD_CAPABILITIES, scstruct_b60c574d-a6db-4d15-a974-dc15ba375b5b.xml, smartcrd.scard_card_capabilities, smclib/PSCARD_CARD_CAPABILITIES, smclib/SCARD_CARD_CAPABILITIES"
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
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	smclib.h
api_name:
-	SCARD_CARD_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: SCARD_CARD_CAPABILITIES, *PSCARD_CARD_CAPABILITIES
req.product: Windows 10 or later.
---

# _SCARD_CARD_CAPABILITIES structure
The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used.

## Syntax
````
typedef struct _SCARD_CARD_CAPABILITIES {
  BOOLEAN                InversConvention;
  ULONG                  etu;
  struct {
     Buffer[64];
     Length;
  } ATR;
  struct {
    UCHAR Buffer[16];
    UCHAR Length;
  } HistoricalChars;
  PCLOCK_RATE_CONVERSION ClockRateConversion;
  PBIT_RATE_ADJUSTMENT   BitRateAdjustment;
  UCHAR                  Fl;
  UCHAR                  Dl;
  UCHAR                  II;
  UCHAR                  P;
  UCHAR                  N;
  ULONG                  GT;
  struct {
    ULONG Supported;
    ULONG Selected;
  } Protocol;
  struct {
    UCHAR WI;
    ULONG WT;
  } T0;
  struct {
    UCHAR IFSC;
    UCHAR CWI;
    UCHAR BWI;
    UCHAR EDC;
    ULONG CWT;
    ULONG BWT;
    ULONG BGT;
  } T1;
  PTS_DATA               PtsData;
  UCHAR                  Reserved[100 - sizeof(PTS_DATA)];
} SCARD_CARD_CAPABILITIES, *PSCARD_CARD_CAPABILITIES;
````

## Members


`ATR`

A structure with the following members:



#### Buffer

A pointer to the buffer that receives the answer-to-reset (ATR) information that the smart card provides to the smart card reader after a warm or cold reset. 



#### Length

Contains the length, in bytes, of the ATR.

`BitRateAdjustment`

Contains the bit rate adjustment table. Using the bit rate adjustment factor, D1, as an index into this array yields the maximum bit rate that is allowed. t rate. For more information about the bit rate adjustment factor, see the <i>ISO 7816-3 specification</i>.  (This resource may not be available in some languages 

and countries.)

`ClockRateConversion`

Contains the clock conversion rate table. Using the clock rate conversion factor, F1, as an index in this array yields the maximum frequency that is allowed. For more information about clock conversion rate, see the <i>ISO 7816-3 specification</i>. (This resource may not be available in some languages 

and countries.)

`Dl`

Contains the bit rate adjustment. When the smart card is reset, the smart card driver library uses this value to calculate a new data bit rate.

`etu`

Contains the elementary time unit (ETU). The ETU indicates the space of transmission time occupied by a single bit of data.

`Fl`

Contains the clock rate conversion. This factor is used as an index into a table of maximum operating frequencies. When the smart card is reset, the smart card driver library uses this value to calculate a new clock frequency.

`GT`

Contains the guard time, in units of microseconds (including the extra guard time), which is the minimum delay between two consecutive characters.

`HistoricalChars`

A structure with the following members:
      
     



#### Buffer

Contains the historical characters. Historical characters designate general information, such as the smart card manufacturer, the chip inserted in the smart card, the masked ROM in the chip, and the life cycle of the smart card. For more information about historical characters, see the <i>ISO 7816-3 Specification</i> and part 4 of the <i>ISO 7816 Specification</i>. (This resource may not be available in some languages 

and countries.)



#### Length

Indicates the length, in bytes, of the historical character information.

`II`

Contains the maximum programming current.

`InversConvention`

Contains a flag to indicate that the current smart card uses the inverse convention.

`N`

Contains the extra guard time in units of the ETU. The ETU indicates the space of transmission time occupied by a single bit of data. The guard time is the minimum space of transmission time that separates two consecutive characters.

`P`

Contains the programming voltage in units of 0.1 volts.

`Protocol`

A structure with the following members:
      
     



#### Supported

Contains a bitmask of the supported protocols. 



#### Selected

Contains the protocol that is selected.

`PtsData`

Contains a PTS_DATA structure that holds all the information that is required to perform a protocol type selection (PTS) request for the inserted smart card.art card.

`Reserved`

Reserved.

`T0`

A structure with the following members:
      
     



#### WI

Contains the work-waiting integer for the T=0 protocol. 



#### WT

Contains the work-waiting time, in microseconds, for the T=0 protocol, which is the maximum delay allowed between two consecutive characters.

`T1`

A structure with the following members:
      
     



#### IFSC

Contains the size, in bytes, of the card's information field.



#### CWI

Contains the character-waiting integer. 



#### BWI

Contains the block-waiting integer. 



#### EDC

Contains the error detection code. 



#### CWT

Contains the character-waiting time, in microseconds, for the T=1 protocol, which is the maximum delay that is allowed between two consecutive characters.s. 



#### BWT

Contains the block-waiting time, in microseconds, for the T=1 protocol. This is the maximum delay between the end of a block and the start of the next block that is sent in the opposite direction. 



#### BGT

Contains the block-guarding time, in microseconds, for the T=1 protocol. This is the minimum delay between the end of a block and the start of the next block that is sent in the opposite direction.

## Remarks
The SCARD_CARD_CAPABILITIES structure describes the capabilities of the inserted smart card. If the reader driver uses the smart card driver library, <b>ATR</b> is the only member that the reader driver should populate. The driver library will automatically update all other fields when it receives an <a href="..\winsmcrd\ni-winsmcrd-ioctl_smartcard_set_protocol.md">IOCTL_SMARTCARD_SET_PROTOCOL</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smclib.h (include Smclib.h) |