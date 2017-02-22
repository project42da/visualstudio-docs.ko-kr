---
title: "방법: 도메인별 언어의 네임스페이스 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 네임스페이스"
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: 19
caps.handback.revision: 19
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 방법: 도메인별 언어의 네임스페이스 변경
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도메인 관련 언어의 네임 스페이스를 변경할 수 있습니다.  변경 해야 합니다의  **DSL 탐색기**, Dsl 패키지 프로젝트의 속성 및 어셈블리 정보입니다.  
  
### 도메인 관련 언어의 네임 스페이스를 변경 하려면  
  
1.  **DSL 탐색기**를 클릭 하는  **Dsl** 노드.  
  
2.  에  **속성** 창에서 변경의  **네임 스페이스** 속성입니다.  
  
3.  솔루션을 저장 및 서식 파일을 변환 합니다.  
  
4.  에 있는  **프로젝트** 메뉴를 클릭  **Dsl 속성**.  
  
     프로젝트 속성이 나타납니다.  
  
5.  **응용 프로그램** 탭을 클릭합니다.  
  
6.  변경의  **기본 네임 스페이스** 속성에는 새 네임 스페이스 이름입니다.  
  
7.  어셈블리의 이름을 변경 하려면 변경의  **어셈블리 이름 속성입니다.**  
  
8.  어셈블리 이름을 변경 하면 Dslpackage\\package.tt를 열고이 줄을 업데이트 합니다.  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. 모든 사용자 지정 코드를 작성 한 경우 코드 파일에서 네임 스페이스 및 클래스 참조를 변경 해야 합니다.  
  
10. Visual Studio 실험 인스턴스를 다시 설정 합니다.  
  
    1.  삭제 **\\Users\\***{이름}***\\AppData\\Local\\Microsoft\\VisualStudio\\\*Exp**  
  
    2.  Windows  **시작** 메뉴를 선택  **모든 프로그램**,  **Microsoft Visual Studio 2010 SDK**,  **도구**,  **실험 인스턴스 다시**.  
  
11. 에 있는  **빌드** 메뉴를 선택  **솔루션 다시 빌드**.  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)