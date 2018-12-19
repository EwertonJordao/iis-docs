﻿---
title: HttpCookie.Uri Property
TOCTitle: Uri Property
ms:assetid: de54d836-935a-4a25-a465-0810ab9d3119
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ822847(v=VS.90)
ms:contentKeyID: 50079601
ms.date: 11/19/2012
mtps_version: v=VS.90
dev_langs:
- csharp
- c++
- jscript
---

# HttpCookie.Uri Property

**Applies to:** Windows Store apps only

Gets the URI of the http cookie.

## Syntax

``` csharp
public Uri Uri { get; set; }
```

``` c++
public:
virtual property Uri^ Uri {
Uri^ get () sealed;
void set (Uri^ value) sealed;
}
```

``` jscript
final function get Uri () : Uri
final function set Uri (value : Uri)
```

## Property Value

The URI.

## Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Minimum supported client</strong></p></td>
<td><p>Windows 8</p></td>
</tr>
<tr class="even">
<td><p><strong>Minimum supported server</strong></p></td>
<td><p>Not Supported</p></td>
</tr>
<tr class="odd">
<td><p><strong>Metadata</strong></p></td>
<td><p>Microsoft.Media.AdaptiveStreaming.winmd</p></td>
</tr>
</tbody>
</table>
