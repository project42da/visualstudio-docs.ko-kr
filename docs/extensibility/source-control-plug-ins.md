---
title: "소스 제어 플러그 인 | Microsoft Docs"
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
  - "소스 제어 플러그 인, 참조"
ms.assetid: 964980ca-21c5-4706-8535-6ea23e1c9cc9
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 플러그 인
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 SDK 참조 섹션에는 소스 제어 시스템으로 통합 될 수 있도록 전체 인터페이스 사양에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 구문 및 의미 체계는 다양 한 형식의 함수 및 데이터 소스 제어 플러그 인 인터페이스를 구현 해야 하는 지정 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\).  
  
## 단원 내용  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)  
 소스 제어 플러그 인 API를 준수 하기 위해 소스 제어 플러그 인에서 구현 해야 하는 함수를 나열 합니다.  
  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)  
 특정 명령이 실행 되는 동안 정보 IDE를 다시 전달 하는 소스 제어 플러그 인을 사용 하는 함수에 설명 합니다.  
  
 [열거자](../extensibility/enumerators.md)  
 소스 제어 플러그 인에 대해 알고 있어야 하는 소스 제어 플러그 인 API에서 열거자 데이터 형식을 나열 합니다.  
  
 [기능 플래그](../extensibility/capability-flags.md)  
 설명의 `SCC_CAP_xxx` 공급자의 기능을 나타내는 플래그입니다.  
  
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)  
 특정 명령의 컨텍스트에서 사용 되는 플래그를 나열 합니다.  
  
 [오류 코드](../extensibility/error-codes.md)  
 함수에서 반환 하는 일반적인 오류 값을 나열 `SCCTRN`합니다.  
  
 [소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)  
 소스 제어 플러그 인을 찾을 레지스트리를 액세스 하기 위한 키에 설명 합니다.  
  
 [MSSCCPRJ 합니다. SCC 파일](../extensibility/mssccprj-scc-file.md)  
 IDE에 불투명 한 정보가 포함 된 소스 제어 플러그 인 버전 제어에서 솔루션 또는 프로젝트를 찾을 사용 하는 클라이언트 쪽 파일에 설명 합니다.  
  
 [소스 제어 플러그 인을 구현 하기 위한 모범 사례](../extensibility/best-practices-for-implementing-a-source-control-plug-in.md)  
 소스 제어 플러그 인 API를 구현 하는 동안 기억할 중요 한 기술 메모의 컬렉션을 제공 합니다.  
  
 [문자열 길이에 대 한 제한](../extensibility/restrictions-on-string-lengths.md)  
 소스 제어 플러그 인 API의 제한 사항에 다양 한 기능에 사용 되는 문자열의 길이에 대해 설명 합니다.  
  
 [용어](../extensibility/source-control-plug-in-glossary.md)  
 유용한 용어 및 소스 제어 플러그 인 SDK 설명서를 읽기 위해 해당 정의 제공 합니다.  
  
 [방법: 소스 제어 플러그 인에 대 한 호환성 경고 해제](../extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins.md)  
 경고를 해제 하는 방법에 설명 합니다.  
  
## 관련 단원  
 [Source Control Plug\-in Sample](http://msdn.microsoft.com/ko-kr/61de7d2b-71db-451e-8e3e-d41b11c7a4ca)  
 샘플 소스 제어 플러그 인 기능을 제공합니다.  
  
 [소스 제어 플러그 인에 대 한 테스트 가이드](../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 소스 제어 플러그 인에 관련 된 테스트 절차를 설명 합니다.  
  
 [소스 제어 플러그 인 만들기](../extensibility/internals/creating-a-source-control-plug-in.md)  
 사용 하는 동안 소스 제어 기능을 제공 하는 소스 제어 플러그 인을 만드는 방법에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 소스 제어 사용자 인터페이스 \(UI\).  
  
 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)  
 참조 항목의 목록을 표시합니다.