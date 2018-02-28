---
title: "속성 창 단추 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 950b9f0a7b0f38689042877a42499e23253e6486
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-buttons"></a>속성 창 단추
개발 언어와 제품 종류에 따라 특정 단추에 대 한 도구 모음에서 기본적으로 표시 되는 **속성** 창. 모든 경우에는 **항목별**, **Alphabetized**, **속성**, 및 **속성 페이지** 단추가 표시 됩니다. Visual C# 및 Visual Basic의 경우에 **이벤트** 단추가 표시 됩니다. 특정 Visual c + + 프로젝트에는 **VC + + 메시지** 및 **VC 재정의** 단추가 표시 됩니다. 다른 프로젝트 형식에 대 한 추가 단추가 표시 될 수 있습니다. 단추에 대 한 자세한 내용은 **속성** 창 참조 [속성 창](../../ide/reference/properties-window.md)합니다.  
  
## <a name="implementation-of-properties-window-buttons"></a>속성 창 단추의 구현  
 클릭는 **항목별** 단추를 Visual Studio 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> 범주별로 정렬 하려면 해당 속성 포커스가 있는 개체의 인터페이스입니다. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>구현 되는 `IDispatch` 에 제공 되는 개체는 **속성** 창.  
  
 음수 값이 들어 있는 미리 정의 된 속성 범주 11 가지가 있습니다. 사용자 지정 범주를 정의할 수 있지만 할당 하는 해당 양수 값 미리 정의 된 범주와 구별 하는 것이 좋습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A> 메서드는 지정된 된 속성에 대 한 적절 한 속성 범주 값을 반환 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A> 메서드 범주 이름을 포함 하는 문자열을 반환 합니다. Visual Studio 표준 속성 범주 값을 알고 있으므로 사용자 지정 범주 값에 대 한 지원을 제공 해야 합니다.  
  
 클릭는 **Alphabetized** 단추, 속성이 이름별 사전순으로 표시 됩니다. 이름으로 검색 되 `IDispatch` 지역화 된 정렬 알고리즘에 따라 합니다.  
  
 때는 **속성** 창이 열릴는 **속성** 단추는 자동으로 표시 된 선택 된 상태로 합니다. 환경의 다른 부분으로 동일한 단추 표시 되 고 표시 하도록 클릭할 수는 **속성** 창.  
  
 **속성 페이지** 단추를 사용할 수 없는 경우 `ISpecifyPropertyPages` 선택한 개체에 대해 구현 되지 않았습니다. 속성 페이지는 일반적으로 솔루션 및 프로젝트를 연결 표시 구성에 종속 된 속성 이지만 될 수도 있습니다 (예를 들어, Visual c + +)에서 프로젝트 항목에 연결 된입니다.  
  
> [!NOTE]
>  도구 모음 단추를 추가할 수 없습니다는 **속성** 비관리 코드를 사용 하 여 창. 관리 되는 개체에서 파생 되는 도구 모음 단추를 추가 하려면 만들어야 <xref:System.Windows.Forms.Design.PropertyTab>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)