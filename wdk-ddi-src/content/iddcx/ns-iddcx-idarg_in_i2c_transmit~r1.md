---
UID: NS.IDDCX.IDARG_IN_I2C_TRANSMIT~R1
title: IDARG_IN_I2C_TRANSMIT
author: windows-driver-content
description: Gives information about the I2C data being transmitted by the OS.
old-location: display\idarg_in_i2c_transmit.htm
old-project: display
ms.assetid: 1422f1fc-9653-4e6b-a7dd-c224ce7b9ca0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_IN_I2C_TRANSMIT,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_I2C_TRANSMIT
req.alt-loc: iddcx.h
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
---

# IDARG_IN_I2C_TRANSMIT structure



## -description

                 Gives information about the I2C data being transmitted by the OS.
             



## -syntax

````
typedef struct IDARG_IN_I2C_TRANSMIT {
  UINT                                     SevenBitI2CAddress;
  UINT                                     DataSizeInBytes;
  _Field_size_full_(DataSizeInBytes) PVOID pData;
} IDARG_IN_I2C_TRANSMIT, *IDARG_IN_I2C_TRANSMIT;
````


## -struct-fields

### -field SevenBitI2CAddress


                     [in] The address of the I2C device to which data will be transmitted
                 


### -field DataSizeInBytes


                     [in] The size, in bytes, of the buffer pointed to by <b>pData</b>. This parameter must be between 1 and 64, inclusively.
                 


### -field pData


                     [in] A pointer to a buffer that holds the data to be transmitted.
                 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>