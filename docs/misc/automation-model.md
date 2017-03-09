---
title: "자동화 모델 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "자동화[Visual Studio SDK], 자동화 모델"
ms.assetid: 48ddc192-96ff-46dc-a1fe-df4eb5c62c84
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# 자동화 모델
자동화 모델은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 확장하기 위한 VSPackage의 대안을 제공합니다. 이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 확장성 모델로 알려진 자동화 모델은 IDE\(통합 개발 환경\)를 구동하는 기본 루틴에 액세스하고 사용자 지정, 조정 및 자동화할 수 있게 하는 프로그래밍 인터페이스입니다.  
  
## VSPackage 및 자동화  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK 설명서에서는 자동화 모델보다 더 많은 개발 잠재력을 제공하는 VSPackage에 중점을 둡니다. 예를 들어 자동화 모델의 개체에 대한 코드를 작성하여 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 등의 언어를 사용자 지정할 수 있습니다. 그러나 자동화 모델을 사용하여 IDE에 새로운 언어를 추가할 수 없습니다. 환경에 새 언어를 추가하려면 VSPackage를 개발해야 합니다.  
  
 자동화 모델과 VSPackage 모델이 함께 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 확장성에 대한 두 가지 접근 방식을 구성합니다. 확장성은 IDE의 기능을 향상시키고 확장하는 기능입니다. 자동차는 기존 환경에서 작업을 자동화하고 프로그래밍 방식으로 IDE를 구동하는 사용자가 만든 코드 및 도구를 가리킵니다. 반면, VSPackage를 사용하면 IDE에 새 기능을 추가할 수 있습니다. VSPackage는 공동으로 만들 수 있는 개체입니다. 즉, 클래스 팩터리를 포함하며 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스를 구현하여 IDE에서 사용할 수 있게 합니다.  
  
 추가 기능 및 마법사는 자동화 모델을 사용하여 해당 자동화 인터페이스를 통해 IDE의 기능을 제어하거나 확장합니다. 일반적으로 많은 추가 기능이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 포함되어 있습니다. 추가 기능을 사용하여 도구 모음과 메뉴에 새 명령을 통합하거나, 도구 창을 추가하거나, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 정기적으로 수행하는 특정 작업을 자동화할 수 있습니다.  
  
 VSPackage 개발자는 자동화 모델에 기여해야 합니다. 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 새 언어를 추가하는 경우 언어에서 기존 모델을 확장하는 강력한 코드 모델을 제공해야 합니다. 자세한 내용은 [자동화 모델에 영향을 주는](../extensibility/internals/contributing-to-the-automation-model.md)을 참조하세요.  
  
## 참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)   
 [자동화 모델에 영향을 주는](../extensibility/internals/contributing-to-the-automation-model.md)