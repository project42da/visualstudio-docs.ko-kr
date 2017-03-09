---
title: "Could not bind to dependency &#39;assembly&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cantbinddependency"
ms.assetid: 0f76190d-d57e-4e0e-bec4-532aec978d08
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Could not bind to dependency &#39;assembly&#39;
프로젝트의 참조 중 하나가 발견했지만 올바른 어셈블리가 아닌 어셈블리 참조\(종속성\)를 포함합니다.  이 경우에도 프로젝트가 빌드되지만  런타임 오류가 발생할 수 있습니다.  
  
 이 상황은 다음 세 가지 조건이 모두 참임을 나타냅니다.  
  
-   디스크에 이름이 같은 파일이 두 개 이상 있습니다.  
  
-   파일 중 하나가 어셈블리가 아니지만 다른 파일은 어셈블리입니다.  
  
-   참조 경로가 어셈블리가 아닌 파일이 포함된 디렉터리를 먼저 검색합니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트에서 디렉터리를 검색하여 참조를 찾는 순서를 수정합니다.  자세한 내용은 [NIB: Reference Paths Dialog Box \(Visual Basic\)](http://msdn.microsoft.com/ko-kr/8e549b39-7256-456a-8fd7-089b23facf9c)를 참조하십시오.  
  
## 참고 항목  
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)   
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Assemblies in the Common Language Runtime](http://msdn.microsoft.com/ko-kr/33a0bc6a-6bb3-44c7-ada7-4a046e8c0945)