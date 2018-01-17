---
UID: NF:ntddk.PsGetParentSilo
title: PsGetParentSilo function
author: windows-driver-content
description: Retrieves the most immediate parent silo in the hierarchy for a given job object.
old-location: kernel\psgetparentsilo.htm
old-project: kernel
ms.assetid: 57fa5563-3a02-449a-a934-85c75f450500
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsGetParentSilo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsGetParentSilo
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# PsGetParentSilo function



## -description
Retrieves the most immediate parent silo in the hierarchy
    for a given job object.
			
            



## -syntax

````
PESILO  PsGetParentSilo(
  _In_opt_ PEJOB Job
);
````


## -parameters

### -param Job [in, optional]

A pointer to an <b>EJOB</b> structure that represents the job object. 


## -returns
A pointer to the parent silo of the job. his value may be
    PSP_HOST_SILO, because all silos descend from the host.


## -remarks
