---
title: 프로젝트 형식 아키텍처 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e6ef7fe6fbf4a8899606dca35c10745e68e3cbfa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="project-types-architecture"></a>프로젝트 형식 아키텍처
이 섹션에서는 프로젝트 형식에서의 아키텍처에 대 한 자세한 정보 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md)  
 프로젝트 형식을 사용할 수 있는 서비스 및 구현 해야 하는 인터페이스를 나열 합니다.  
  
 [프로젝트 모델 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)  
 프로젝트 형식 둘 다 구현 해야 하며 필요에 따라 추가 기능을 제공 하기 위해 구현할 수 인터페이스에 설명 합니다.  
  
 [프로젝트 형식을 만들어야 하는 경우](../../extensibility/internals/when-to-create-project-types.md)  
 때 프로젝트를 만들어야 결정 하면 입력 하 고 다른 사용 가능 시기 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 같은 목표를 달성 하는 Vspackage 및 편집기 등의 확장성 기능입니다.  
  
 [계층 구조 및 선택](../../extensibility/internals/hierarchies-and-selection.md)  
 설명 방법을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 계층 및 선택 항목 컨텍스트를 사용 하 여 일관 되 고 간소화 된 사용자 환경을 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)  
 프로젝트 하위 형식 통해 하의 프로젝트 시스템의 동작을 사용자 지정할 수는 방법에 대해 설명 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]합니다.  
  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 기본 빌딩 블록으로 프로젝트에 대 한 개요를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE). 프로젝트 빌드 및 코드 컴파일를 제어 하는 방법을 설명 하는 추가 항목 링크가 제공 됩니다.