---
UID: NS.ata._IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO
title: IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\identify_device_data_log_page_zoned_device_info.htm
old-project: storage
ms.assetid: 2F0B6C1F-54CC-47CF-B0D0-A53FAB80AF91
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO, IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO, *PIDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ata.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO
req.alt-loc: Ata.h
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

# IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>
</p>


## -syntax

````
typedef struct _IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO {
  IDENTIFY_DEVICE_DATA_LOG_PAGE_HEADER Header;
  struct {
    ULONGLONG URSWRZ  :1;
    ULONGLONG Reserved  :62;
    ULONGLONG Valid  :1;
  } ZonedDeviceCapabilities;
  struct {
    ULONGLONG Reserved  :63;
    ULONGLONG Valid  :1;
  } ZonedDeviceSettings;
  struct {
    ULONGLONG Number  :32;
    ULONGLONG Reserved  :31;
    ULONGLONG Valid  :1;
  } OptimalNumberOfOpenSequentialWritePreferredZones;
  struct {
    ULONGLONG Number  :32;
    ULONGLONG Reserved  :31;
    ULONGLONG Valid  :1;
  } OptimalNumberOfNonSequentiallyWrittenSequentialWritePreferredZones;
  struct {
    ULONGLONG Number  :32;
    ULONGLONG Reserved  :31;
    ULONGLONG Valid  :1;
  } MaxNumberOfOpenSequentialWriteRequiredZones;
  struct {
    ULONGLONG ZacMinorVersion  :16;
    ULONGLONG Reserved0  :47;
    ULONGLONG Valid  :1;
  } Version;
  UCHAR                                Reserved[456];
} IDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO, *PIDENTIFY_DEVICE_DATA_LOG_PAGE_ZONED_DEVICE_INFO;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>ZonedDeviceCapabilities</b>

<dd>
<dl>

### -field <b>URSWRZ</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>ZonedDeviceSettings</b>

<dd>
<dl>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>OptimalNumberOfOpenSequentialWritePreferredZones</b>

<dd>
<dl>

### -field <b>Number</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>OptimalNumberOfNonSequentiallyWrittenSequentialWritePreferredZones</b>

<dd>
<dl>

### -field <b>Number</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>MaxNumberOfOpenSequentialWriteRequiredZones</b>

<dd>
<dl>

### -field <b>Number</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>Version</b>

<dd>
<dl>

### -field <b>ZacMinorVersion</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Reserved0</b>

<dd>
<p>N/A</p>
</dd>

### -field <b>Valid</b>

<dd>
<p>N/A</p>
</dd>
</dl>
</dd>

### -field <b>Reserved</b>

<dd>
<p>N/A</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ata.h</dt>
</dl>
</td>
</tr>
</table>