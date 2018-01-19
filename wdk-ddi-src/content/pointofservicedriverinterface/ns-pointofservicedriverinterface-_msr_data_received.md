---
UID : NS:pointofservicedriverinterface._MSR_DATA_RECEIVED
title : _MSR_DATA_RECEIVED
author : windows-driver-content
description : This structure contains the data read from a swiped magnetic stripe card.
old-location : pos\msr_data_received.htm
old-project : pos
ms.assetid : f103724c-25c4-4dec-a7a3-9713440ca833
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MSR_DATA_RECEIVED, MSR_DATA_RECEIVED, *PMSR_DATA_RECEIVED
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pointofservicedriverinterface.h
req.include-header : PointOfServiceDriverInterface.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MSR_DATA_RECEIVED
req.alt-loc : PointOfServiceDriverInterface.h
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
req.typenames : MSR_DATA_RECEIVED, *PMSR_DATA_RECEIVED
---

# _MSR_DATA_RECEIVED structure
This structure contains the data read from a swiped magnetic stripe card.

## Syntax
````
typedef struct _MSR_DATA_RECEIVED {
  MsrCardType   CardType;
  unsigned char Track1EncryptedDataLength;
  unsigned char Track2EncryptedDataLength;
  unsigned char Track3EncryptedDataLength;
  unsigned char Track4EncryptedDataLength;
  unsigned char Track1EncryptedData[MSR_TRACK_SIZE];
  unsigned char Track2EncryptedData[MSR_TRACK_SIZE];
  unsigned char Track3EncryptedData[MSR_TRACK_SIZE];
  unsigned char Track4EncryptedData[MSR_TRACK_SIZE];
  unsigned char Track1MaskedDataLength;
  unsigned char Track2MaskedDataLength;
  unsigned char Track3MaskedDataLength;
  unsigned char Track4MaskedDataLength;
  unsigned char Track1MaskedData[MSR_TRACK_SIZE];
  unsigned char Track2MaskedData[MSR_TRACK_SIZE];
  unsigned char Track3MaskedData[MSR_TRACK_SIZE];
  unsigned char Track4MaskedData[MSR_TRACK_SIZE];
  unsigned char Track1DiscretionaryDataLength;
  unsigned char Track2DiscretionaryDataLength;
  unsigned char Track1DiscretionaryData[MSR_TRACK_SIZE];
  unsigned char Track2DiscretionaryData[MSR_TRACK_SIZE];
  unsigned char CardAuthenicationDataLength;
  unsigned char CardAuthenticationDataAbsoluteLength;
  unsigned char CardAuthenicationData[MSR_CARD_AUTHENTICATION_DATA_SIZE];
  unsigned char AdditionalSecurityInformationLength;
  unsigned char AdditionalSecurityInformation[MSR_ADDITIONAL_SECURITY_INFORMATION_SIZE];
} MSR_DATA_RECEIVED, *PMSR_DATA_RECEIVED;
````

## Members

        
            `AdditionalSecurityInformation`

            Additional security information read from the swiped card.
        
            `AdditionalSecurityInformationLength`

            The amount of additional security information, in bytes, stored in <b>AdditionalSecurityInformation[MSR_ADDITIONAL_SECURITY_INFORMATION_SIZE]</b>.
        
            `CardAuthenicationData`

            Authentication data read from the swiped card.
        
            `CardAuthenicationDataLength`

            The amount of encrypted card authentication data, in bytes, that is stored in <b>CardAuthenicationData[MSR_CARD_AUTHENTICATION_DATA_SIZE]</b>. May include padding.
        
            `CardAuthenticationDataAbsoluteLength`

            The amount of card authentication data, in bytes, before encryption. This value may be used to remove padding on decryption.
        
            `CardType`

            Type of card that was swiped.
        
            `Track1DiscretionaryData`

            The amount of discretionary  track 1 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.
        
            `Track1DiscretionaryDataLength`

            The amount of discretionary track 1 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.
        
            `Track1EncryptedData`

            The encrypted data read from track 1 of the swiped card.
        
            `Track1EncryptedDataLength`

            The amount of encrypted track 1 data, in bytes, that is stored in <b>Track1EncryptedData[MSR_TRACK_SIZE].</b>
        
            `Track1MaskedData`

            The masked data read from track 1 of the swiped card.
        
            `Track1MaskedDataLength`

            The amount of masked track 1 data, in bytes, that is stored in <b>Track1MaskedData[MSR_TRACK_SIZE]</b>.
        
            `Track2DiscretionaryData`

            The amount of discretionary track 2 data, in bytes, that is stored in <b>Track1DiscretionaryData[MSR_TRACK_SIZE]</b>.
        
            `Track2DiscretionaryDataLength`

            The amount of discretionary track 2 data, in bytes, that is stored in <b>Track2DiscretionaryData[MSR_TRACK_SIZE]</b>.
        
            `Track2EncryptedData`

            The encrypted data read from track 2 of the swiped card.
        
            `Track2EncryptedDataLength`

            The amount of encrypted track 2 data, in bytes, that is stored in <b>Track2EncryptedData[MSR_TRACK_SIZE].</b>
        
            `Track2MaskedData`

            The masked data read from track 2 of the swiped card.
        
            `Track2MaskedDataLength`

            The amount of masked track 2 data, in bytes, that is stored in <b>Track2MaskedData[MSR_TRACK_SIZE]</b>.
        
            `Track3EncryptedData`

            The encrypted data read from track 3 of the swiped card.
        
            `Track3EncryptedDataLength`

            The amount of encrypted track 3 data, in bytes, that is stored in <b>Track3EncryptedData[MSR_TRACK_SIZE].</b>
        
            `Track3MaskedData`

            The masked data read from track 3 of the swiped card.
        
            `Track3MaskedDataLength`

            The amount of masked track 3 data, in bytes, that is stored in <b>Track3MaskedData[MSR_TRACK_SIZE]</b>.
        
            `Track4EncryptedData`

            The encrypted data read from track 4 of the swiped card.
        
            `Track4EncryptedDataLength`

            The amount of encrypted track 4 data, in bytes, that is stored in <b>Track4EncryptedData[MSR_TRACK_SIZE].</b>
        
            `Track4MaskedData`

            The masked data read from track 4 of the swiped card.
        
            `Track4MaskedDataLength`

            The amount of masked track 4 data, in bytes, that is stored in <b>Track4MaskedData[MSR_TRACK_SIZE]</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |