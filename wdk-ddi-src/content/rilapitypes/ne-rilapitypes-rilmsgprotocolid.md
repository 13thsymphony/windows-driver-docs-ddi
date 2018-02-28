---
UID: NE:rilapitypes.RILMSGPROTOCOLID
title: RILMSGPROTOCOLID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgprotocolid_2.htm
old-project: netvista
ms.assetid: a4dc4bc4-f636-46be-b99c-12d2bf4a577f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGPROTOCOLID, RILMSGPROTOCOLID enumeration [Network Drivers Starting with Windows Vista], RIL_MSGPROTOCOL_DEPERSONALIZATION, RIL_MSGPROTOCOL_EMAIL, RIL_MSGPROTOCOL_ERMES, RIL_MSGPROTOCOL_GSMSTATION, RIL_MSGPROTOCOL_IMPLICIT, RIL_MSGPROTOCOL_MAX, RIL_MSGPROTOCOL_ME_DOWNLOAD, RIL_MSGPROTOCOL_MSGHANDLING, RIL_MSGPROTOCOL_PAGING, RIL_MSGPROTOCOL_RETURNCALL, RIL_MSGPROTOCOL_RSM_TYPE1, RIL_MSGPROTOCOL_RSM_TYPE2, RIL_MSGPROTOCOL_RSM_TYPE3, RIL_MSGPROTOCOL_RSM_TYPE4, RIL_MSGPROTOCOL_RSM_TYPE5, RIL_MSGPROTOCOL_RSM_TYPE6, RIL_MSGPROTOCOL_RSM_TYPE7, RIL_MSGPROTOCOL_SCSPECIFIC1, RIL_MSGPROTOCOL_SCSPECIFIC2, RIL_MSGPROTOCOL_SCSPECIFIC3, RIL_MSGPROTOCOL_SCSPECIFIC4, RIL_MSGPROTOCOL_SCSPECIFIC5, RIL_MSGPROTOCOL_SCSPECIFIC6, RIL_MSGPROTOCOL_SCSPECIFIC7, RIL_MSGPROTOCOL_SMETOSME, RIL_MSGPROTOCOL_SM_TYPE0, RIL_MSGPROTOCOL_TELEFAX_GROUP3, RIL_MSGPROTOCOL_TELEFAX_GROUP4, RIL_MSGPROTOCOL_TELETEX, RIL_MSGPROTOCOL_TELETEX_CSPDN, RIL_MSGPROTOCOL_TELETEX_ISDN, RIL_MSGPROTOCOL_TELETEX_PSPDN, RIL_MSGPROTOCOL_TELETEX_PSTN, RIL_MSGPROTOCOL_TELEX, RIL_MSGPROTOCOL_UCI, RIL_MSGPROTOCOL_UICC_DOWNLOAD, RIL_MSGPROTOCOL_VIDEOTEX, RIL_MSGPROTOCOL_VOICEPHONE, RIL_MSGPROTOCOL_X400, netvista.rilmsgprotocolid_2, rilapitypes/RILMSGPROTOCOLID, rilapitypes/RIL_MSGPROTOCOL_DEPERSONALIZATION, rilapitypes/RIL_MSGPROTOCOL_EMAIL, rilapitypes/RIL_MSGPROTOCOL_ERMES, rilapitypes/RIL_MSGPROTOCOL_GSMSTATION, rilapitypes/RIL_MSGPROTOCOL_IMPLICIT, rilapitypes/RIL_MSGPROTOCOL_MAX, rilapitypes/RIL_MSGPROTOCOL_ME_DOWNLOAD, rilapitypes/RIL_MSGPROTOCOL_MSGHANDLING, rilapitypes/RIL_MSGPROTOCOL_PAGING, rilapitypes/RIL_MSGPROTOCOL_RETURNCALL, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE1, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE2, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE3, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE4, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE5, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE6, rilapitypes/RIL_MSGPROTOCOL_RSM_TYPE7, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC1, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC2, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC3, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC4, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC5, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC6, rilapitypes/RIL_MSGPROTOCOL_SCSPECIFIC7, rilapitypes/RIL_MSGPROTOCOL_SMETOSME, rilapitypes/RIL_MSGPROTOCOL_SM_TYPE0, rilapitypes/RIL_MSGPROTOCOL_TELEFAX_GROUP3, rilapitypes/RIL_MSGPROTOCOL_TELEFAX_GROUP4, rilapitypes/RIL_MSGPROTOCOL_TELETEX, rilapitypes/RIL_MSGPROTOCOL_TELETEX_CSPDN, rilapitypes/RIL_MSGPROTOCOL_TELETEX_ISDN, rilapitypes/RIL_MSGPROTOCOL_TELETEX_PSPDN, rilapitypes/RIL_MSGPROTOCOL_TELETEX_PSTN, rilapitypes/RIL_MSGPROTOCOL_TELEX, rilapitypes/RIL_MSGPROTOCOL_UCI, rilapitypes/RIL_MSGPROTOCOL_UICC_DOWNLOAD, rilapitypes/RIL_MSGPROTOCOL_VIDEOTEX, rilapitypes/RIL_MSGPROTOCOL_VOICEPHONE, rilapitypes/RIL_MSGPROTOCOL_X400
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILMSGPROTOCOLID
product: Windows
targetos: Windows
req.typenames: RILMSGPROTOCOLID
req.product: Windows 10 or later.
---

# RILMSGPROTOCOLID Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGPROTOCOLID { 
  RIL_MSGPROTOCOL_SMETOSME,
  RIL_MSGPROTOCOL_IMPLICIT,
  RIL_MSGPROTOCOL_TELEX,
  RIL_MSGPROTOCOL_TELEFAX_GROUP3,
  RIL_MSGPROTOCOL_TELEFAX_GROUP4,
  RIL_MSGPROTOCOL_VOICEPHONE,
  RIL_MSGPROTOCOL_ERMES,
  RIL_MSGPROTOCOL_PAGING,
  RIL_MSGPROTOCOL_VIDEOTEX,
  RIL_MSGPROTOCOL_TELETEX,
  RIL_MSGPROTOCOL_TELETEX_PSPDN,
  RIL_MSGPROTOCOL_TELETEX_CSPDN,
  RIL_MSGPROTOCOL_TELETEX_PSTN,
  RIL_MSGPROTOCOL_TELETEX_ISDN,
  RIL_MSGPROTOCOL_UCI,
  RIL_MSGPROTOCOL_MSGHANDLING,
  RIL_MSGPROTOCOL_X400,
  RIL_MSGPROTOCOL_EMAIL,
  RIL_MSGPROTOCOL_SCSPECIFIC1,
  RIL_MSGPROTOCOL_SCSPECIFIC2,
  RIL_MSGPROTOCOL_SCSPECIFIC3,
  RIL_MSGPROTOCOL_SCSPECIFIC4,
  RIL_MSGPROTOCOL_SCSPECIFIC5,
  RIL_MSGPROTOCOL_SCSPECIFIC6,
  RIL_MSGPROTOCOL_SCSPECIFIC7,
  RIL_MSGPROTOCOL_GSMSTATION,
  RIL_MSGPROTOCOL_SM_TYPE0,
  RIL_MSGPROTOCOL_RSM_TYPE1,
  RIL_MSGPROTOCOL_RSM_TYPE2,
  RIL_MSGPROTOCOL_RSM_TYPE3,
  RIL_MSGPROTOCOL_RSM_TYPE4,
  RIL_MSGPROTOCOL_RSM_TYPE5,
  RIL_MSGPROTOCOL_RSM_TYPE6,
  RIL_MSGPROTOCOL_RSM_TYPE7,
  RIL_MSGPROTOCOL_RETURNCALL,
  RIL_MSGPROTOCOL_ME_DOWNLOAD,
  RIL_MSGPROTOCOL_DEPERSONALIZATION,
  RIL_MSGPROTOCOL_UICC_DOWNLOAD,
  RIL_MSGPROTOCOL_MAX
} RILMSGPROTOCOLID;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_DEPERSONALIZATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_EMAIL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_ERMES</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_GSMSTATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_IMPLICIT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_ME_DOWNLOAD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_MSGHANDLING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_PAGING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RETURNCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE4</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE5</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE6</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_RSM_TYPE7</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC4</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC5</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC6</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SCSPECIFIC7</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SM_TYPE0</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_SMETOSME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELEFAX_GROUP3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELEFAX_GROUP4</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELETEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELETEX_CSPDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELETEX_ISDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELETEX_PSPDN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELETEX_PSTN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_TELEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_UCI</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_UICC_DOWNLOAD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_VIDEOTEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_VOICEPHONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGPROTOCOL_X400</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |