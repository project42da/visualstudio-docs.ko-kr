---
title: 속성 표를 표시 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- properties [Visual Studio SDK], grid
ms.assetid: 318e41b0-acf5-4842-b85e-421c9d5927c5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 279450126cfcc7edba9398632e20bfb75e312b89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-display-grid"></a>눈금 속성 표시
**속성** grid 필드 창에 표시 됩니다. 왼쪽된 열에 속성 이름이; 오른쪽 열 속성 값을 포함합니다.  
  
## <a name="working-with-the-grid"></a>그리드와 작업  
 두 개의 열 목록에는 디자인 타임 및의 현재 설정은 변경할 수 있는 구성 독립적 속성이 표시 됩니다. 참고 모든 속성을 표시할 수 있습니다. 속성을 설정할 수를 구현 하 여 예를 들어 숨김으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> 메서드. 자식 속성을 가진 숨기기 속성에 특히:  
  
1.  설정의 `pfDisplay` 매개 변수에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> 를 `FALSE`합니다.  
  
2.  설정의 `pfHide` 매개 변수에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> 를 `TRUE`합니다.  
  
 에 정보는 **속성** 창, IDE 사용 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 각 창에 표시할 관련된 속성을 사용 하 여 선택할 수 있는 개체를 포함 하는 Vspackage에 의해 호출 됩니다는 **속성** 창. **솔루션 탐색기**의 구현의 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 호출 `GetProperty` 를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층의 항목 개체를 프로젝트 계층 구조에 있습니다.  
  
 VSPackage를 지원 하지 않는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>, IDE를 사용 하려고 시도 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 에 대 한 값을 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층 항목 또는 항목을 제공 합니다.  
  
 VSPackage를 만드는 필요 하지 않는 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> IDE에서 제공 하는 창을 구현 하므로 패키지 하는 것 (예를 들어 **솔루션 탐색기**) 생성 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 을 대신 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> IDE에 의해 호출 되는 세 가지 방법으로 구성 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.CountObjects%2A> 에 표시할 선택한 개체의 개수가 **속성** 창.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> 반환 된 `IDispatch` 에 표시할 선택 된 개체는 **속성** 창.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> 반환 된 개체에 대해 가능 하 게 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> 사용자가 선택할 수 있습니다. 이렇게 하면 UI에 사용자에 게 표시 하 여 선택 영역을 시각적으로 업데이트 하기 위해 VSPackage가 있습니다.  
  
 **속성** 창에서 정보를 추출 된 `IDispatch` 탐색 속성을 검색 하는 개체입니다. 속성 브라우저를 사용 하 여 `IDispatch` 속성 개체를 요청 하 여 지 원하는 쿼리 `ITypeInfo`에서 얻을 수 있는 `IDispatch::GetTypeInfo`합니다. 브라우저 다음을 사용 하 여 이러한 값은 **속성** 창과 표에 표시 된 개별 속성에 대 한 값으로 변경 합니다. 속성 정보는 개체 자체 내에서 유지 됩니다.  
  
 반환 된 개체를 지원 하기 때문에 `IDispatch`, 호출자가 호출 하 여 개체의 이름과 같은 정보를 얻을 수 `IDispatch::Invoke` 또는 `ITypeInfo::Invoke` 원하는 정보를 나타내는 미리 정의 된 디스패치 식별자 (DISPID)를 사용 합니다. 선언 된 Dispid는 사용자 정의 되는 식별자와 충돌 하지 않는 경우에 음수입니다.  
  
 **속성** 다양 한 유형의 선택한 개체의 특정 속성의 특성에 따라 필드 창에 표시 됩니다. 이러한 필드는 편집 상자, 드롭 다운 목록 및 링크 사용자 지정 편집기 대화 상자에 포함 됩니다.  
  
-   열거 된 목록에 포함 된 값을 검색 한 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> 쿼리를 통해 `IDispatch`합니다. 필드 이름을 두 번 클릭 하거나 값을 클릭 하 고 드롭다운 목록에서 새 값을 선택 하 여 열거 목록을에서 얻은 값을 속성 표에서 변경할 수 있습니다. 속성의 설정을 열거 된 목록에서 미리 정의 되어 있는 경우 사용 가능한 선택 항목을 순환 속성 목록에 속성 이름을 두 번 클릭 합니다. True/false 같은 두 개의 선택 된 미리 정의 된 속성에 대 한 선택 항목 사이 전환 하려면 속성 이름을 두 번 클릭 합니다.  
  
-   경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HasDefaultValue%2A> 은 `false`를 나타내는 값이 변경, 값 굵은 텍스트로 표시 됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.CanResetPropertyValue%2A> 값을 원래 값으로 다시 설정할 경우를 결정 하는 데 사용 됩니다. 따라서 변경할 수 있는 경우 다시 기본값으로 값을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 **재설정** 표시 되는 메뉴에서 합니다. 그렇지 않으면 다시 기본값으로 값을 수동으로 변경 해야 할 수도 있습니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 또한 필드를 지역화 하 고 디자인 타임에 표시 되는 속성의 이름을 숨길 수 있습니다 하지만 런타임 시 표시 되는 속성 이름이 영향을 주지 않습니다.  
  
-   줄임표 (...) 단추를 클릭 하면 속성 값 (예: 색 선택 또는 글꼴 목록) 선택할 수 있는 사용자의 목록이 표시 됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder> 이러한 값을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)