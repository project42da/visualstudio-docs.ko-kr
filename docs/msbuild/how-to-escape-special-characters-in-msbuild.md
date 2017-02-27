---
title: "방법: MSBuild의 이스케이프 특수 문자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "특수 문자를 이스케이프"
  - "문자 이스케이프"
  - "이스케이프 문자"
  - "MSBuild 특수 문자 이스케이프"
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>방법: MSBuild의 이스케이프 특수 문자
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일에서 특정 문자는 특수한 의미로 사용됩니다. 이러한 문자의 예로는 세미콜론(;) 및 별표(*)를 들 수 있습니다. 이러한 특수 문자의 전체 목록을 보려면 [MSBuild 특수 문자](../msbuild/msbuild-special-characters.md)를 참조하세요.  
  
 프로젝트 파일에서 이러한 특수 문자를 리터럴로 사용하려면 %*xx* 구문을 사용하여 해당 문자를 지정해야 합니다. 여기서 *xx*는 문자의 ASCII&16;진수 값을 나타냅니다.  
  
## <a name="msbuild-special-characters"></a>MSBuild 특수 문자  
 항목 목록의 `Include` 특성에서 특수 문자가 사용되는 하나의 예가 있습니다. 예를 들어 다음 항목 목록은 두 개의 항목, `MyFile.cs` 및 `MyClass.cs`를 선언합니다.  
  
```xml  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 이름에 세미콜론이 포함된 항목을 선언하려면 %*xx* 구문을 사용하여 세미콜론을 이스케이프하고 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]가 두 개의 개별 항목을 선언하지 않게 해야 합니다. 예를 들어 다음 항목은 세미콜론을 이스케이프하고 `MyFile.cs;MyClass.cs`라는 하나의 항목을 선언합니다.  
  
```xml  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>MSBuild 특수 문자를 리터럴 문자로 사용하려면  
  
-   특수 문자 대신 %*xx* 표기법을 사용할 수 있습니다. 여기서 *xx*는 ASCII 문자의&16;진수 값을 나타냅니다. 예를 들어 별표(*)를 리터럴 문자로 사용하려면 `%2A` 값을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [MSBuild](../msbuild/msbuild.md)
 [항목](../msbuild/msbuild-items.md)


<!--HONumber=Feb17_HO4-->


