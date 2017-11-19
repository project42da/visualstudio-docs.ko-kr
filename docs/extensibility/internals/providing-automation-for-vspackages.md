---
title: "Vspackage에 대 한 자동화를 제공 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, automation [Visual Studio SDK]
- automation [Visual Studio SDK], VSPackages
ms.assetid: 104c4c55-78b8-42f4-b6b0-9a334101aaea
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4d81a96b7eea9f19352ae8a1deeeeb73ba5dc089
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="providing-automation-for-vspackages"></a>Vspackage에 대 한 자동화를 제공합니다.
사용자 Vspackage에 대 한 자동화를 제공 하는 방법에 두 가지가: VSPackage와 관련 된 개체를 구현 하 여 및 표준 자동화 개체를 구현 하 여 합니다. 일반적으로 이러한 함께 사용 됩니다 환경의 자동화 모델을 확장 합니다.  
  
## <a name="vspackage-specific-objects"></a>VSPackage와 관련 된 개체  
 자동화 모델 내의 특정 위치를 사용 하는 VSPackage에 고유한 자동화 개체를 제공 해야 합니다. 예를 들어, 새 프로젝트만 VSPackage를 제공 하는 고유한 개체 필요 합니다. 이러한 개체의 이름은 레지스트리에 입력 되 고 환경에 대 한 호출을 통해 얻은 `DTE` 개체입니다.  
  
 VSPackage와 관련 된 개체를 자동화 소비자 표준 개체의 개체 속성을 통해 제공 되는 개체를 사용 하는 경우 얻을 수 있습니다. 예를 들어 표준 `Window` 개체에는 `Object` 으로 일반적으로 알려진 속성은 `Windows.Object` 속성입니다. 소비자가 호출 하는 경우는 `Window.Object` VSPackage에서 구현 하는 창에 전달 다시 사용자가 디자인의 특정 자동화 개체를 사용 하 여 합니다.  
  
#### <a name="projects"></a>프로젝트  
 Vspackage는 자신의 VSPackage 관련 개체를 통해 새 프로젝트 형식에 대 한 자동화 모델을 확장할 수 있습니다. 프로젝트 고유 구분 하는 VSPackage에 대 한 새 자동화 개체를 제공 하의 주요 목적은 개체는 <xref:Microsoft.VisualStudio.VCProjectEngine.VCProject> 또는 <xref:VSLangProj80.VSProject2> 개체입니다. 나란히 표시 되어야 골라낼 또는 기타 프로젝트 형식 외에도 프로젝트 유형과 반복 하는 방법을 제공 하려는 경우 이러한 구분이 편리한 솔루션에서입니다. 자세한 내용은 참조 [프로젝트 개체 노출](../../extensibility/internals/exposing-project-objects.md)합니다.  
  
#### <a name="events"></a>이벤트  
 환경의 이벤트 아키텍처는 사용자 고유의 VSPackage와 관련 된 개체를 추가할 수 있습니다에 대 한 다른 장소를 제공 합니다. 예를 들어 사용자 고유의 고유한 이벤트 개체를 만들어 프로젝트에 대 한 이벤트 모델은 환경의 확장할 수 있습니다. 사용자 고유의 프로젝트 형식에 새 항목 추가 될 때 사용자 고유의 이벤트를 제공 수 있습니다. 자세한 내용은 참조 [노출 이벤트](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)합니다.  
  
#### <a name="window-objects"></a>창 개체  
 Windows에 전달할 수 다시 VSPackage 관련 자동화 개체를 다시 호출 될 때 환경. 파생 된 개체를 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, <xref:EnvDTE.IExtensibleObject> 또는 `IDispatch` 다시 배치 되어 있는 window 개체를 확장 하는 속성을 전달 하는 합니다. 예를 들어 창 프레임에 컨트롤에 대 한 자동화를 위해이 방법을 사용할 수 있습니다. 이 개체 및 확장 하는 다른 개체의 의미 체계를 디자인 하는 합니다. 자세한 내용은 참조 [하는 방법: Windows 용 자동화 제공](../../extensibility/internals/how-to-provide-automation-for-windows.md)합니다.  
  
#### <a name="options-pages-on-the-tools-menu"></a>도구 메뉴에서 옵션 페이지  
 도구 페이지를 구현 하 고 원하는 옵션을 만들려면 레지스트리에 정보 추가 통해 옵션 자동화 모델 확장 하는 페이지를 만들 수 있습니다. 페이지에는 다른 옵션 페이지와 같은 환경 개체 모델을 통해 호출할 수 있습니다. Vspackage 통해 환경에 추가 하는 기능의 설계 옵션 페이지를 필요한 경우에 자동화 지원을 추가 해야 합니다. 자세한 내용은 참조 [옵션 페이지에 대 한 자동화 지원을](../../extensibility/internals/automation-support-for-options-pages.md)합니다.  
  
## <a name="standard-automation-objects"></a>표준 자동화 개체  
 프로젝트에 대 한 자동화를 확장 하려면 구현 표준 자동화 개체 (에서 파생 된 `IDispatch`) 다른 프로젝트 개체 옆에 있는 대기 모드로 전환 하 고 표준 메서드 및 속성을 구현 합니다. 표준 개체의 예로 같은 솔루션 계층에 삽입 되는 프로젝트 개체 `Projects`, `Project`, `ProjectItem`, 및 `ProjectItems`합니다. 이러한 개체 및 수 있는 다른 조건은 의미 체계에 따라 프로젝트의 모든 새 프로젝트 형식을 구현 해야 합니다.  
  
 즉, 이러한 개체는 반대 활용 VSPackage 관련 프로젝트 개체를 제공합니다. 표준 자동화 개체는 프로젝트는 동일한 개체를 지 원하는 다른 프로젝트와 마찬가지로 일반화 된 방식으로 사용할 수를 허용 합니다. 따라서 추가 기능인 일반에 대해 작성 된 `Project` 및 `ProjectItem` 개체는 모든 종류의 프로젝트에 대해 작동할 수 있습니다. 자세한 내용은 참조 [프로젝트 모델링](../../extensibility/internals/project-modeling.md)합니다.