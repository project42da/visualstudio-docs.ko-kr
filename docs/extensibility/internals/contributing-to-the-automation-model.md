---
title: "자동화 모델에 기여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bb69380913f188031c97b46530ea2659fc05fe30
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="contributing-to-the-automation-model"></a>Contributing to the Automation Model
Visual Studio 환경 사용자 지정에 대 한 자동화 인터페이스의 집합을 제공 합니다. 자동화 모델은 최종 사용자가 Visual Studio 추가 기능 및 확장을 만들 수 있는 개체 모델입니다.  
  
 또한 적절 한, VSPackage 개발자, 자동화 모델에 기여 하는 추가 기능을 만들고 일반적으로 방식으로 일관 된 사용자 모델에서 VSPackage를 사용 하 여 VSPackage의 최종 사용자가 사용 하면이 통해 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 발생 하는 최종 사용자가 일관 되 게 하려면 다음과 수를 VSPackage에 대 한 자동화 모델에 대 한 아이디어를 뒤에 오도록 VSPackage를 디자인할 때 일련의 지침을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [자동화 모델 개요](../../extensibility/internals/automation-model-overview.md)  
 일반적인 환경의 주요 측면을 제어 하는 개체 등의 관련된 그룹으로 자동화 모델을 정의 합니다. 이 개체 집합이 자동화 모델의 다이어그램에 나와 있습니다.  
  
 [VSPackage에 대한 자동화 제공](../../extensibility/internals/providing-automation-for-vspackages.md)  
 VSPackage에 대 한 자동화를 제공 하는 두 가지 주요 방법에 설명 합니다.  
  
 [프로젝트 개체 노출](../../extensibility/internals/exposing-project-objects.md)  
 VSPackage와 관련 된 개체를 만들기 위한 단계별 지침을 제공 합니다.  
  
 [프로젝트 모델링](../../extensibility/internals/project-modeling.md)  
 새 프로젝트 형식에 대 한 자동화를 만드는 데 필요한 표준 프로젝트 개체를 설명 하 고 프로젝트 자동화 뒤에 오는 경로 보여 줍니다. 이 항목에는 또한 선언 및 구현 클래스에 대 한 목록을 제공합니다.  
  
 [이벤트를 노출](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)  
 자동화 모델에 대 한 이벤트를 만들기 위한 단계별 지침을 제공 합니다.  
  
 [옵션 페이지의 자동화 지원](../../extensibility/internals/automation-support-for-options-pages.md)  
 VSPackage의 속성을 지 원하는 사용자 지정에 대 한 자동화 개체를 반환 하는 방법에 설명 **옵션** 대화 상자에는 **도구** 확장 하 여 메뉴는 `DTE.Properties` 개체입니다.  
  
 [코드에 대한 자동화 제공](../../extensibility/internals/providing-automation-for-code.md)  
 코드에 대 한 자동화 모델을 만드는 필요 하지 않음을 설명 합니다. 그러나 코드 모델에 대 한 유용한 정보를 제공 하는이 항목에는 링크가 제공 됩니다.  
  
 [방법: Windows에 대한 자동화 제공](../../extensibility/internals/how-to-provide-automation-for-windows.md)  
 자동화를 제공 하는 것이 좋습니다는 창에서 자동화 개체를 사용할 수 있도록 하 고 환경에서는 미리 만들어진 자동화 개체를 제공 하지 않습니다 때마다에 대해 설명 합니다. 도구 창과 문서 창에 대 한 자동화를 설명합니다.  
  
 [자동화 모델 사용](../../extensibility/internals/using-the-automation-model.md)  
 자동화 소비자를 얻는 방법을 초기 프로젝트 자동화 개체를 보여 주는 두 코드 예제를 제공 합니다.  
  
 [ 및 SelectedItem 개체 자동화](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)  
 구성 옵션에 대 한 자동화 및 선택한 항목에 대 한 자동화에 대 한 정보를 제공합니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>  
 VSPackage DTE 자동화 개체 모델에 참여 하는 방법을 보여 주는 코드 샘플을 제공 합니다. 매개 변수, 반환 값 및 선택한 설명 부분을 나열합니다.  
  
## <a name="related-sections"></a>관련 단원