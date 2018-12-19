﻿---
title: JobDefinition.JobManagerLogRolloverIntervalDisplayUnit Property  (Microsoft.Web.Media.TransformManager)
TOCTitle: JobManagerLogRolloverIntervalDisplayUnit Property
ms:assetid: P:Microsoft.Web.Media.TransformManager.JobDefinition.JobManagerLogRolloverIntervalDisplayUnit
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.jobdefinition.jobmanagerlogrolloverintervaldisplayunit(v=VS.90)
ms:contentKeyID: 35521154
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.JobDefinition.set_JobManagerLogRolloverIntervalDisplayUnit
- Microsoft.Web.Media.TransformManager.JobDefinition.get_JobManagerLogRolloverIntervalDisplayUnit
- Microsoft.Web.Media.TransformManager.JobDefinition.JobManagerLogRolloverIntervalDisplayUnit
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.Common.dll
api_name:
- Microsoft.Web.Media.TransformManager.JobDefinition.get_JobManagerLogRolloverIntervalDisplayUnit
- Microsoft.Web.Media.TransformManager.JobDefinition.set_JobManagerLogRolloverIntervalDisplayUnit
- Microsoft.Web.Media.TransformManager.JobDefinition.JobManagerLogRolloverIntervalDisplayUnit
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# JobManagerLogRolloverIntervalDisplayUnit Property

Gets or sets the unit of time that is used with the [JobDefinition..::..JobManagerLogRolloverIntervalMinutes](jobdefinition-jobmanagerlogrolloverintervalminutes-property-microsoft-web-media-transformmanager.md) property to indicate when to create a new log.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.Common (in Microsoft.Web.Media.TransformManager.Common.dll)

## Syntax

``` vb
'Declaration
<DataMemberAttribute> _
PublicPropertyJobManagerLogRolloverIntervalDisplayUnitAsStringGetSet
'Usage
DiminstanceAsJobDefinitionDimvalueAsStringvalue = instance.JobManagerLogRolloverIntervalDisplayUnit

instance.JobManagerLogRolloverIntervalDisplayUnit = value
```

``` csharp
[DataMemberAttribute]
publicstringJobManagerLogRolloverIntervalDisplayUnit { get; set; }
```

``` c++
[DataMemberAttribute]
public:
propertyString^ JobManagerLogRolloverIntervalDisplayUnit {
    String^ get ();
    voidset (String^ value);
}
```

``` fsharp
[<DataMemberAttribute>]
memberJobManagerLogRolloverIntervalDisplayUnit : stringwithget, set
```

``` jscript
function getJobManagerLogRolloverIntervalDisplayUnit () : Stringfunction setJobManagerLogRolloverIntervalDisplayUnit (value : String)
```

#### Property Value

Type: [System. . :: . .String](https://msdn.microsoft.com/en-us/library/s1wwdcbf\(v=vs.90\))  
The unit of time.  

## Remarks

The JobManagerLogRolloverIntervalDisplayUnit property modifies the [JobManagerLogRolloverIntervalMinutes](jobdefinition-jobmanagerlogrolloverintervalminutes-property-microsoft-web-media-transformmanager.md) property. The JobManagerLogRolloverIntervalDisplayUnit property can be set to "days", "hours", or "minutes".

## See Also

#### Reference

[JobDefinition Class](jobdefinition-class-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
