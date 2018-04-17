---
title: 소스 제어 VSPackage 구현 여부를 결정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, about source control packages
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 203144e5b262c093204fe9eafa3a2a5db85eccb3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="determining-whether-to-implement-a-source-control-vspackage"></a>소스 제어 VSPackage 구현 여부를 결정
이 섹션 소스 제어 통합 적절 한 경로 선택 하는 방법에 대 한 솔루션 및 제공 광범위 한 지침을 확장 하기 위한 소스 제어 플러그 인 및 소스 제어 Vspackage의 선택 항목에서는 합니다.  
  
## <a name="small-source-control-solution-with-limited-resources"></a>리소스가 제한 된 소형 원본 제어 솔루션  
 리소스가 제한 되어 원본 제어 패키지를 작성 하는 오버 헤드로 상근 수 없는 경우에 소스 제어 플러그 인 API 기반 플러그 인을 만들 수 있습니다. 소스 제어 패키지와 함께 작업할 수 있습니다 및 소스 제어 플러그 인 및 필요에 따라 패키지 간에 전환할 수 있습니다. 자세한 내용은 참조 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)합니다.  
  
## <a name="large-source-control-solution-with-a-rich-feature-set"></a>풍부한 기능 집합과 대형 소스 제어 솔루션  
 소스 제어 플러그 인 API를 사용 하 여 적절 하 게 캡처되지 않는 풍부한 소스 제어 모델을 제공 하는 원본 제어 솔루션을 구현 하려는 경우 통합 경로로 소스 제어 패키지를 고려할 수 있습니다. 이 적용 됩니다 (소스 제어 플러그 인 통신할 수 있게 해 주는 기본 소스 제어 UI) 소스 제어 어댑터 패키지 아니라 바꾸어야 하는 경우에 특히를 사용자의 사용자 지정 방식으로 소스 컨트롤 이벤트를 처리할 수 있도록 합니다. UI를 제어 하 고 해당 환경을 유지 하려면 만족 스러운 소스에 이미 있는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 원본 제어 패키지 옵션을 사용 하면 작업을 수행할 수 있습니다. 소스 제어 패키지 제네릭이 고와 사용 하기 위해서만 설계 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 유연성 및 소스 제어 논리 및 UI를 통해 다양 한 제어를 제공 하는 원본 제어 솔루션을 구현 하려는 경우에 원본 제어 패키지 통합 라우팅을 할 수도 있습니다. 다음과 같은 작업을 수행할 수 있습니다.  
  
1.  사용자 고유의 소스 제어 VSPackage 등록 (참조 [등록 및 선택](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)).  
  
2.  기본 소스 제어 UI를 사용자 지정 UI를 바꿉니다 (참조 [사용자 지정 사용자 인터페이스](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)).  
  
3.  사용 되 고 솔루션 탐색기 문자 모양 이벤트를 처리할 문자 모양을 지정 (참조 [문자 모양 제어](../../extensibility/internals/glyph-control-source-control-vspackage.md)).  
  
4.  쿼리 편집 및 쿼리를 저장 하는 이벤트를 처리 (참조 [쿼리 편집 쿼리 저장](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)).  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)