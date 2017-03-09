---
title: "프로젝트의 기본 네임스페이스 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 도구, 기본 네임스페이스 계산"
ms.assetid: 6d890676-7016-458c-8a6a-95cc0a068612
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# 프로젝트의 기본 네임스페이스 확인
에 대 한 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 경우는 `CustomToolNamespace` 속성은 다음 값을 입력된 파일에서 설정 `CustomToolNamespace` 기본 namespace 매개 변수에 전달 된 값이 됩니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 메서드.  그렇지 않은 경우는 `wszDefaultNamespace` 매개 변수를 전달 합니다 `Generate` 항상 루트 네임 스페이스와 같습니다.  네임 스페이스에 대 한 자세한 내용은 [네임스페이스 키워드](/dotnet/csharp/language-reference/keywords/namespace-keywords).  
  
 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]폴더 기반 네임 스페이스를 사용합니다.  즉, 네임 스페이스는 루트 네임 스페이스를 사용자 지정 도구를 포함 하는 폴더의 이름으로 구성 됩니다.  각 폴더 이름은 올바른 식별자로 변환 되 고 모든 이름을 마침표 구분 합니다.  예를 들어, 입력된 파일 FolderA\\FolderB\\FolderC\\MyInput.txt, 루트 네임 스페이스 cl9는 경우, 다음 계산 된 기본 네임 스페이스 수 있습니다 **CL9.FolderA.FolderB.FolderC**.  
  
 웹 참조 폴더의 계층 구조 체인을 포함 하는 경우이 규칙에 예외가 발생 합니다.  예를 들면 다음과 같습니다.  
  
-   Folderc의 웹 참조 폴더에서의 네임 스페이스 수 있습니다 **CL9.FolderC**.  
  
-   Folderb의 웹 참조 폴더에서의 네임 스페이스 수 있습니다 **CL9.FolderB.FolderC**.  
  
 즉, 네임 스페이스는 다음과 같은 형식을 사용합니다.  
  
```  
rootNamespace.webReferenceFolder.containedFolder.containedFolder ...  
```  
  
## 참고 항목  
 [단일 파일 생성기를 구현합니다.](../extensibility/internals/implementing-single-file-generators.md)   
 [단일 파일 생성기를 등록 하는 중](../extensibility/internals/registering-single-file-generators.md)   
 [비주얼 디자이너에 형식을 노출합니다.](../extensibility/internals/exposing-types-to-visual-designers.md)