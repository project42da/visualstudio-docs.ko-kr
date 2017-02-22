---
title: "기호 공급자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기호 처리기"
  - "디버깅 기호 처리기 [디버깅 SDK]"
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 기호 공급자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

식 평가기 구현은 변수와 식을 계산 하는 언어 컴파일러에 의해 생성 되는 기호화 된 디버그 정보를 액세스 해야 합니다.  이 기호 처리기 라고도 기호 공급자 \(SP\)의 인터페이스를 사용 하 여 수행 됩니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Sp 기호 프로그램 데이터베이스 \(PDB\) 파일 형식을 사용 하 여 네이티브 코드 뿐만 아니라 관리 되는 코드를 제공 합니다.  없는 경우 강력한 사용자 정의 형식으로 저장 된 기호를 사용 하려면 프로그램에 대 한 필요,이 제공한 Sps를 사용 하는 것이 좋습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## 구현 참고 사항  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 엔진을 기대 하는 공용 언어 런타임 \(CLR\) 인터페이스를 사용 하 여 Sp와 대화할 수 있습니다.  따라서 Visual Studio 디버깅 엔진으로 작업을 수행 하는 SP CLR를 지원 해야 합니다.  모든 CLR 디버깅 인터페이스 목록을 모두 참가 하는 debugref.doc에서 찾을 수 있습니다에 [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)].  
  
 사용자 SP 사용자 지정 디버그 엔진에만 작업을 수행 하는 경우 디버그 엔진을 필요에 따라 적절 하 게 SP를 구현할 수 있습니다.  
  
## 참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)