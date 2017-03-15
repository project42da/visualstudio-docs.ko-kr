---
title: "Cannot find custom tool &#39;custom tool&#39; on this system | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannot_instantiate_generator1"
ms.assetid: 51fe9bec-b8bc-4a4c-94aa-15a1f7cc8b6b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Cannot find custom tool &#39;custom tool&#39; on this system
프로젝트 시스템에서 사용자 지정 도구를 만들 수 없습니다.  사용자 지정 도구를 인스턴스화할 수 없기 때문에 요청된 사용자 지정 도구가 실행되지 않습니다.  사용자 지정 도구가 제대로 설치되고 등록되었는지 확인하십시오.  
  
 이 오류는 특정 파일의 `CustomTool` 속성에 잘못된 사용자 지정 도구 이름을 지정하면 발생합니다.  프로젝트 파일\(.vbproj\/.csproj\)을 편집할 때 `CustomTool` 속성 값을 잘못된 값으로 변경했을 수도 있습니다.  또는 사용자 지정 도구가 있는 다른 시스템에서 개발한 프로젝트를 사용자 지정 도구가 설치되지 않은 시스템에서 사용했을 수 있습니다.  `CustomTool` 속성에 대한 자세한 내용은 [File Properties](http://msdn.microsoft.com/ko-kr/013c4aed-08d6-4dce-a124-ca807ca08959)을 참조하십시오.  
  
 사용자 지정 도구에 대해 [CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)가 실패할 때도 이 오류가 발생할 수 있습니다.  예를 들어, 사용자 지정 도구가 등록되지 않았거나 필요한 DLL이 없을 경우가 이에 해당합니다.  
  
## 참고 항목  
 [CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)