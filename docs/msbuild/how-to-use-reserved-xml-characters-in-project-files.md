---
title: "방법: 프로젝트 파일에서 예약된 XML 문자 사용 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb747b60c575aa1e49b559d3cf4a73b649808041
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>방법: 프로젝트 파일에서 예약된 XML 문자 사용
프로젝트 파일을 작성할 경우 속성 값이나 작업 매개 변수 값 등에서 예약된 XML 문자를 사용해야 합니다. 그러나 프로젝트 파일을 구문 분석할 수 있도록 일부 예약된 문자를 명명된 엔터티로 바꿔야 합니다.  
  
## <a name="using-reserved-characters"></a>예약된 문자 사용  
 다음 표에서는 프로젝트 파일을 구문 분석할 수 있도록 해당 명명된 엔터티로 대체되어야 하는 예약된 XML 문자를 설명합니다.  
  
|예약된 문자|명명된 엔터티|  
|------------------------|------------------|  
|\<|&amp;lt;|  
|>|&amp;gt;|  
|&|&amp;amp;|  
|"|&amp;quot;|  
|'|&amp;apos;|  
  
#### <a name="to-use-double-quotes-in-a-project-file"></a>프로젝트 파일에서 큰따옴표를 사용하려면  
  
-   큰따옴표를 해당 명명된 엔터티 &amp;quot;로 바꿉니다. 예를 들어 `EXEFile` 항목 목록 주위에 큰따옴표를 배치하려면 다음을 입력합니다.  
  
    ```xml  
    <Message Text="The output file is &quot;@(EXEFile)&quot;."/>  
    ```  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 프로젝트 파일에서 출력된 메시지에서 파일 이름을 강조 표시할 때 큰따옴표가 사용됩니다.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>"HelloWorldCS"</appname>  
    </PropertyGroup>  
    <!-- Specify the inputs -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs" />  
    </ItemGroup>  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input  
        files of type CSFile -->  
        <Csc Sources = "@(CSFile)">  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile"/>  
        </Csc>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is &quot;@(EXEFile)&quot;."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 참조](../msbuild/msbuild-reference.md)    
 [MSBuild](../msbuild/msbuild.md)    
