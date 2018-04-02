---
UID: NS:scsi.RT_PARAMETER_DATA
title: RT_PARAMETER_DATA
author: windows-driver-content
description: The RT_PARAMETER_DATA structure contains the parameter data for the report timestamp command.
old-location: storage\rt_parameter_data.htm
old-project: storage
ms.assetid: EB23D502-87E4-48B1-B1DC-0B215AB361C8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRT_PARAMETER_DATA, PRT_PARAMETER_DATA, PRT_PARAMETER_DATA structure pointer [Storage Devices], RT_PARAMETER_DATA, RT_PARAMETER_DATA structure [Storage Devices], scsi/PRT_PARAMETER_DATA, scsi/RT_PARAMETER_DATA, storage.rt_parameter_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	scsi.h
api_name:
-	RT_PARAMETER_DATA
product:
- Windows
targetos: Windows
req.typenames: RT_PARAMETER_DATA, *PRT_PARAMETER_DATA
req.product: Windows 10 or later.
---

# RT_PARAMETER_DATA structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>RT_PARAMETER_DATA</b> structure contains the parameter data for the report timestamp command.

## Syntax
```
typedef struct RT_PARAMETER_DATA {
  UCHAR      ParameterDataLength[2];
  UCHAR  : 3 Origin;
  UCHAR  : 5 Reserved1;
  UCHAR      Reserved2;
  UCHAR      Timestamp[6];
  UCHAR      Reserved3[2];
} *PRT_PARAMETER_DATA, RT_PARAMETER_DATA;
```

## Members


`ParameterDataLength`

Indicates the number of bytes that follow in the parameter data.

`Origin`

Indicates the most recent event that initialized the returned device clock.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Device clock initialized to zero at power on or as the result of a hard reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Reserved for future use.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Device clock initialized by the SET TIMESTAMP command.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3</dt>
</dl>
</td>
<td width="60%">
Device clock initialized by an unknown method.

</td>
</tr>
<tr>
<td width="40%"><a id=""></a><dl>
<dt><b></b></dt>
<dt>4 to 7</dt>
</dl>
</td>
<td width="60%">
Reserved for future use.

</td>
</tr>
</table>

`Reserved1`

Reserved for future use.

`Reserved2`

Reserved for future use.

`Timestamp`

Contains the current value of a device clock.

`Reserved3`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1709 and later versions of Windows. Available in Windows 10, version 1709 and later versions of Windows. |
| **Header** | scsi.h (include Minitape.h, Storport.h) |

## See Also

<a href="https://msdn.microsoft.com/C50F45EC-433C-421D-BD02-4C86CB44D5A4">ST_PARAMETER_DATA</a>