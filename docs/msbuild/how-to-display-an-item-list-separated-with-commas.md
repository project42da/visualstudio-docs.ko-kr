---
title: "방법: 항목 목록을 쉼표로 구분하여 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 항목 컬렉션 형식 지정"
  - "MSBuild, 세미콜론으로 항목 구분"
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 항목 목록을 쉼표로 구분하여 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)]\([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]\)에서 항목 목록으로 작업할 때 해당 항목 목록의 내용을 읽기 쉽게 표시하는 것이 유용한 경우가 있습니다.  또는 특수 구분 문자열로 구분된 항목 목록을 사용하는 작업이 있을 수 있습니다.  두 가지 경우 모두 항목 목록에 대해 구분 문자열을 지정할 수 있습니다.  
  
## 쉼표로 목록의 항목 구분  
 기본적으로 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 세미콜론을 사용하여 목록의 항목을 구분합니다.  예를 들어, 다음 값을 가진 `Message` 요소를 고려합니다.  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 `@(TXTFile)` 항목 목록에 App1.txt, App2.txt 및 App3.txt가 있는 경우 메시지는 다음과 같습니다.  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 기본 동작을 변경하려는 경우 자체 구분 기호를 지정할 수 있습니다.  항목 목록 구분 기호를 지정하는 구문은 다음과 같습니다.  
  
 `@(ItemListName, '<separator>')`  
  
 구분 기호는 단일 문자이거나 문자열일 수 있으며 작은따옴표로 묶여 있어야 합니다.  
  
#### 항목 사이에 쉼표와 공백을 삽입하려면  
  
-   다음과 비슷한 항목 표기법을 사용합니다.  
  
     `@(TXTFile, ', ')`  
  
## 예제  
 이 예제에서 [Exec](../msbuild/exec-task.md) 작업은 findstr 도구를 실행하여 Phrases.txt 파일에서 지정된 텍스트 문자열을 찾습니다.  findstr 명령에서 리터럴 검색 문자열은 **\/c:** 스위치로 표시되므로, `@(Phrase)` 항목 목록의 항목 사이에 항목 구분 기호 `/c:`가 삽입됩니다.  
  
 이 예제에 대해 동일한 기능을 수행하는 명령줄 명령은 다음과 같습니다.  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```  
<Project DefaultTargets = "Find"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <Phrase Include="hello"/>  
        <Phrase Include="world"/>  
        <Phrase Include="msbuild"/>  
    </ItemGroup>  
  
    <Target Name = "Find">  
        <!-- Find some strings in a file -->  
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [항목](../msbuild/msbuild-items.md)