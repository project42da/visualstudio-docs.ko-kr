---
title: "포트 공급자 구현 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 포트 공급자 구현"
  - "포트 공급 업체, 구현"
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 포트 공급자 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

포트 공급자 포트의 요청을 세션 디버그 매니저 \(SDM\)을 제공합니다.  포트 공급자는 DCOM을 사용 하지 않는 컴퓨터에 디버깅 하는 경우 또는 새 장치를 지원 하도록 해야 하는 경우 구현 해야 합니다.  예를 들어, 휴대 전화를 디버깅을 위해 \(아마: IR 또는 셀 연결 으로\) 휴대 전화에 연결 하 여 프로세스 및 전화에서 실행 되는 프로그램을 열거 하는 포트를 제공 하 여 포트 공급 업체를 구현할 수도 있습니다.  
  
 \(원격 디버깅 포함\)는 Windows 기반 컴퓨터에서 프로그램을 디버깅 Visual Studio 고유한 포트 공급자를 구현 하지 않아도 되므로 네이티브 및 CLR \(공용 언어 런타임\) 프로세스에 대 한 포트 공급자를 제공 합니다.  
  
## 단원 내용  
 [구현 하 고 포트 공급자를 등록 하는 중](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 SDM을 포트 포트 공급자와 상호 작용 하는 방법에 대해 설명 합니다.  
  
 [필요한 포트 공급자 인터페이스](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 포트 공급자를 얻으려면 구현 해야 인터페이스에 설명 합니다.  
  
## 관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 디버깅의 주요 아키텍처 개념에 설명 합니다.  
  
## 참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)