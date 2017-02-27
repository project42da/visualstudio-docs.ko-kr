---
title: "구성 및 SelectedItem 개체에 대 한 자동화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "자동화 [Visual Studio SDK] SelectedItem 개체"
  - "빌드 자동화 [Visual Studio SDK]"
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 구성 및 SelectedItem 개체에 대 한 자동화
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

빌드 및 선택한 항목에서 프로세스를 자동화할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## 자동화 빌드에 대 한  
 빌드 또는 구성 된 구현할 때 제공 되는 자동화 모델 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>.  자세한 내용은 [빌드 구성 이해](../../ide/understanding-build-configurations.md)을 참조하십시오.  
  
 있는 VSPackage 만들고 구성 옵션을 제어 하려는 자동화 모델을 사용 해야 합니다.  
  
## SelectedItem 자동화  
 에 대 한 구현을 제공 하지 않아도 해당 `SelectedItem` Visual Studio 표준 구현을 포함 되어 있기 때문에 개체.  그러나 구현할 수는 `SelectedItem` 선호 하는 경우 개체입니다.  포함 된 개체를 구현 해야는 `SelectedItem` 인터페이스와 호출에 응답을 반환는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> VSITEMID 메서드로 설정 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [자동화 모델에 영향을 주는](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [빌드 구성 이해](../../ide/understanding-build-configurations.md)