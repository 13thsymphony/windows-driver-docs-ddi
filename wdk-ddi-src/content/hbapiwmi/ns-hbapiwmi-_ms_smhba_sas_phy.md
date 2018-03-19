---
UID: NS:hbapiwmi._MS_SMHBA_SAS_PHY
title: "_MS_SMHBA_SAS_PHY"
author: windows-driver-content
description: The MS_SMHBA_SAS_PHY structure is used to report the SAS physical port information.
old-location: storage\ms_smhba_sas_phy.htm
old-project: storage
ms.assetid: 9bbf2f63-4479-47ee-a014-78b13deccb4c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMS_SMHBA_SAS_PHY, MS_SMHBA_SAS_PHY, MS_SMHBA_SAS_PHY structure [Storage Devices], PMS_SMHBA_SAS_PHY, PMS_SMHBA_SAS_PHY structure pointer [Storage Devices], _MS_SMHBA_SAS_PHY, hbapiwmi/MS_SMHBA_SAS_PHY, hbapiwmi/PMS_SMHBA_SAS_PHY, storage.ms_smhba_sas_phy, structs-Fibre_2ff7917d-a369-4cc9-ab8e-c774f63761a7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	MS_SMHBA_SAS_PHY
product: Windows
targetos: Windows
req.typenames: MS_SMHBA_SAS_PHY, *PMS_SMHBA_SAS_PHY
---

# _MS_SMHBA_SAS_PHY structure
The MS_SMHBA_SAS_PHY structure is used to report the SAS physical port information.

## Syntax
````
typedef struct _MS_SMHBA_SAS_PHY {
  UCHAR PhyIdentifier;
  ULONG NegotiatedLinkRate;
  ULONG ProgrammedMinLinkRate;
  ULONG HardwareMinLinkRate;
  ULONG ProgrammedMaxLinkRate;
  ULONG HardwareMaxLinkRate;
  UCHAR domainPortWWN[8];
} MS_SMHBA_SAS_PHY, *PMS_SMHBA_SAS_PHY;
````

## Members


`PhyIdentifier`

The port whose physical configuration and link information is being returned. It is unique within the context of the SAS device that contains the physical port.

`NegotiatedLinkRate`

The state or the transmission speed that is negotiated by the physical port for the physical link.

`ProgrammedMinLinkRate`

The minimum physical link rate that is set by the physical port control mechanism.

`HardwareMinLinkRate`

The minimum physical link rate that is supported by the physical port.

`ProgrammedMaxLinkRate`

The maximum physical link rate that is set by the physical port control mechanism.

`HardwareMaxLinkRate`

The maximum physical link rate that is supported by the physical port.

`domainPortWWN`

The Port_Identifier that has the smallest value of any Port_Identifier of an expander SMP.

## Remarks
Link rates are defined in hpaapi.h as HBA_SASSPEED_1_5GBIT and HBA_SASSPEED_3GBIT.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |