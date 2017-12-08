---
UID: NS.SMCLIB._SCARD_CARD_CAPABILITIES
title: _SCARD_CARD_CAPABILITIES
author: windows-driver-content
description: The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used.
old-location: smartcrd\scard_card_capabilities.htm
old-project: smartcrd
ms.assetid: 8cc223be-a692-4141-81f6-4cca9e2fccf1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SCARD_CARD_CAPABILITIES, SCARD_CARD_CAPABILITIES, *PSCARD_CARD_CAPABILITIES
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
req.alt-api: SCARD_CARD_CAPABILITIES
req.alt-loc: smclib.h
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
req.product: Windows 10 or later.
---

# _SCARD_CARD_CAPABILITIES structure



## -description
The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used. 


## -syntax

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


## -struct-fields

### -field InversConvention

Contains a flag to indicate that the current smart card uses the inverse convention. 

### -field etu

Contains the elementary time unit (ETU). The ETU indicates the space of transmission time occupied by a single bit of data.  

### -field ATR


      A structure with the following members:

### -field Buffer

A pointer to the buffer that receives the answer-to-reset (ATR) information that the smart card provides to the smart card reader after a warm or cold reset. 

### -field Length

Contains the length, in bytes, of the ATR. 
</dd>
</dl>

### -field HistoricalChars


      A structure with the following members:
      
     

### -field Buffer

Contains the historical characters. Historical characters designate general information, such as the smart card manufacturer, the chip inserted in the smart card, the masked ROM in the chip, and the life cycle of the smart card. For more information about historical characters, see the <i>ISO 7816-3 Specification</i> and part 4 of the <i>ISO 7816 Specification</i>. (This resource may not be available in some languages 

and countries.)

### -field Length

Indicates the length, in bytes, of the historical character information. 
</dd>
</dl>

### -field ClockRateConversion

Contains the clock conversion rate table. Using the clock rate conversion factor, F1, as an index in this array yields the maximum frequency that is allowed. For more information about clock conversion rate, see the <i>ISO 7816-3 specification</i>. (This resource may not be available in some languages 

and countries.)

### -field BitRateAdjustment

Contains the bit rate adjustment table. Using the bit rate adjustment factor, D1, as an index into this array yields the maximum bit rate that is allowed. t rate. For more information about the bit rate adjustment factor, see the <i>ISO 7816-3 specification</i>.  (This resource may not be available in some languages 

and countries.)

### -field Fl

Contains the clock rate conversion. This factor is used as an index into a table of maximum operating frequencies. When the smart card is reset, the smart card driver library uses this value to calculate a new clock frequency. 

### -field Dl

Contains the bit rate adjustment. When the smart card is reset, the smart card driver library uses this value to calculate a new data bit rate. 

### -field II

Contains the maximum programming current. 

### -field P

Contains the programming voltage in units of 0.1 volts. 

### -field N

Contains the extra guard time in units of the ETU. The ETU indicates the space of transmission time occupied by a single bit of data. The guard time is the minimum space of transmission time that separates two consecutive characters.

### -field GT

Contains the guard time, in units of microseconds (including the extra guard time), which is the minimum delay between two consecutive characters.

### -field Protocol


      A structure with the following members:
      
     

### -field Supported

Contains a bitmask of the supported protocols. 

### -field Selected

Contains the protocol that is selected. 
</dd>
</dl>

### -field T0


      A structure with the following members:
      
     

### -field WI

Contains the work-waiting integer for the T=0 protocol. 

### -field WT

Contains the work-waiting time, in microseconds, for the T=0 protocol, which is the maximum delay allowed between two consecutive characters. 
</dd>
</dl>

### -field T1


      A structure with the following members:
      
     

### -field IFSC

Contains the size, in bytes, of the card's information field.

### -field CWI

Contains the character-waiting integer. 

### -field BWI

Contains the block-waiting integer. 

### -field EDC

Contains the error detection code. 

### -field CWT

Contains the character-waiting time, in microseconds, for the T=1 protocol, which is the maximum delay that is allowed between two consecutive characters.s. 

### -field BWT

Contains the block-waiting time, in microseconds, for the T=1 protocol. This is the maximum delay between the end of a block and the start of the next block that is sent in the opposite direction. 

### -field BGT

Contains the block-guarding time, in microseconds, for the T=1 protocol. This is the minimum delay between the end of a block and the start of the next block that is sent in the opposite direction. 
</dd>
</dl>

### -field PtsData

Contains a PTS_DATA structure that holds all the information that is required to perform a protocol type selection (PTS) request for the inserted smart card.art card.

### -field Reserved

Reserved.

## -remarks
The SCARD_CARD_CAPABILITIES structure describes the capabilities of the inserted smart card. If the reader driver uses the smart card driver library, <b>ATR</b> is the only member that the reader driver should populate. The driver library will automatically update all other fields when it receives an <a href="..\winsmcrd\ni-winsmcrd-ioctl_smartcard_set_protocol.md">IOCTL_SMARTCARD_SET_PROTOCOL</a> request. 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Smclib.h (include Smclib.h)</dt>
</dl>
</td>
</tr>
</table>