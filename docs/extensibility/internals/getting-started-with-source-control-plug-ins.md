---
title: "소스 제어 플러그 인 시작 | Microsoft Docs"
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
  - "소스 제어 플러그 인을 시작 하기"
  - "시작, 시작된 소스 제어 플러그 인"
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 플러그 인 시작
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인을 만들려면 소스 제어 플러그 인 API에 정의 된 함수를 구현 하는 DLL을 만든 다음 DLL을 등록 하 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 코드 버전 제어를 사용 하기 위해 사용할 수 있도록 합니다.  
  
 세 가지 버전의 소스 제어 플러그 인 API \(버전 1.1, 1.2, 1.3\) 소스 제어 플러그 인을 사용할 수 있습니다.  여기에 문서화 소스 제어 플러그 인 API 버전 1.3입니다.  소스 제어 플러그 인을 완벽 하 게 호환 되도록 설계 된 버전 1.1 및 1.2를 지원 합니다.  [소스 제어 플러그 인 API 버전 1.3의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) 섹션에서 최신 버전의 소스 제어 플러그 인 API 지원의 새로운 기능에 자세히 설명 합니다.  
  
## 단원 내용  
 [방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 소스 컨트롤 DLL에 연결 하는 데 필요한 레지스트리 항목을 만드는 방법에 설명 합니다.  
  
 [소스 제어 플러그 인 API 버전 1.3의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 소스 제어 플러그 인 API 버전 1.3에에서 대 한 변경 내용을 간단히 소개 합니다.  
  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 소스 제어 플러그 인 API 버전 1.2에에서 대 한 변경 내용을 간단히 소개 합니다.  
  
## 관련 단원  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)  
 소스 제어 플러그 인 API의 모든 요소에 대 한 전체 목록을 제공합니다.  
  
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 소스 제어 플러그 인 SDK를 정의 하 고 포함 된 리소스에 설명 합니다.