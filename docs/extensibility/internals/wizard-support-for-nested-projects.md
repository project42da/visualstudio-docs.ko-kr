---
title: "중첩된 프로젝트에 대 한 마법사 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "추가 항목 마법사"
  - "중첩된 프로젝트 마법사 지원"
  - "새 프로젝트 마법사"
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 중첩된 프로젝트에 대 한 마법사 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE 중첩된 프로젝트에 대 한 상위 프로젝트를 구현할 수 있는 두 가지 마법사가 실행: 있는  **새 프로젝트** 마법사 및  **항목 추가** 마법사.  
  
 사용자가 시작 하는 경우는  **새 프로젝트** 선택 하 여 마법사  **프로젝트 추가** 클릭 하 고  **새 프로젝트** 파일 메뉴 또는 선택 하 여  **추가** 마우스 오른쪽 단추로 클릭 하 고  **새 프로젝트** IDE의 솔루션 탐색기에서 실행는 **AddProject** 명령 및 부모 프로젝트의 구현에는 **AddProject** 명령을 반환 템플릿 프로젝트 파일 또는 컨텍스트 매개 변수 세트를 가진 마법사 \(.vsz\) 파일 중 하나.  
  
 마찬가지로 부모 프로젝트를 구현 하는  **항목 추가** 마법사.vsz 파일 다른 집합의 컨텍스트 매개 변수를 반환 합니다.  
  
 마법사에 대 한 자세한 내용은 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md), [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md) 및 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [중첩 프로젝트](../../extensibility/internals/nesting-projects.md)