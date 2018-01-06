---
title: "레거시 언어 Service1 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 304d99c1ddd5fdfddba0c4df88fc4eeeb9dcb7ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-legacy-language-service"></a>레거시 언어 서비스를 구현합니다.
구문 강조, 중괄호 일치 및 IntelliSense 완성 등을 지 원하는 다양 한 기능을 레거시 언어 서비스를 구현 하 관리 패키지 프레임 워크 (MPF)에서 클래스를 사용할 수 있습니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [레거시 언어 서비스 개요](../../extensibility/internals/legacy-language-service-overview.md)  
 MPF에서 지원 되는 언어 서비스 기능의 개요입니다.  
  
 [레거시 언어 서비스를 구현합니다.](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 MPF를 사용 하 여 언어 서비스를 구현 하는 데 필요한 사항에 대해 설명 합니다.  
  
 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 MPF 기반 언어 서비스를 등록 하는 데 필요한 단계를 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [레거시 언어 서비스 파서 및 검사기](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 MPF를 사용 하 여 언어 서비스의 모든 기능을 구현 하는 데 필요한 두 개의 파서를 설명 합니다.  
  
 [연습: 레거시 언어 서비스 만들기](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Vspackage에서는 MPF 언어 서비스를 구현 하는 데 필요한 기본 단계를 제공 합니다.  
  
 [연습: 설치된 코드 조각 목록 가져오기(레거시 구현)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 설치 된 코드 조각의 목록을 검색 하는의 기술을 보여 줍니다.  
  
 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)  
 항목의 링크를 실행 되어야 하는 MPF를 사용 하 여 언어 서비스의 모든 기능을 구현 하려면 세부 정보를 제공 합니다.