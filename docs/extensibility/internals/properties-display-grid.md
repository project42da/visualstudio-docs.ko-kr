---
title: "눈금 표시 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 [Visual Studio SDK], 표"
ms.assetid: 318e41b0-acf5-4842-b85e-421c9d5927c5
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 눈금 표시 속성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

해당  **속성이** 창 필드 눈금 안에 표시 됩니다.  왼쪽된 열은 속성 이름이 포함 됩니다. 오른쪽 열 속성 값을 포함 합니다.  
  
## 구분선 작업을  
 디자인 타임 및 해당 현재 설정에서 변경할 수 있는 구성 독립적 속성 2 열 목록에 나타납니다.  참고 모든 속성이 표시 될 수 있습니다.  속성을 설정할 수 있습니다 구현 하 여 예를 들어, 같은 숨겨진의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> 방법입니다.  표시 되는 자식 속성을 가진 속성에 특히 숨기기 [자식 속성을 가진 속성 숨기기](../../misc/hiding-properties-that-have-child-properties.md).  
  
 정보를 전달할 수 있는  **속성** IDE 창을 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>Vspackages가 선택할 수 있는 개체를 표시 하는 관련 된 속성을 포함 하는 각 창에 대 한 호출 되는  **속성** 창입니다.  **솔루션 탐색기**의 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 호출 `GetProperty` 를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층 구조에서 확장 개체 가져오기 위해 프로젝트 계층 구조에 있습니다.  
  
 Vspackage를 지원 하지 않는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>, IDE를 사용 하려고 시도 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 에 대 한 값을 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층 구조 항목을 제공 합니다.  
  
 VSPackage 만들 필요 하지 않기 때문에 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> IDE에서 제공 하는 윈도우 패키지는이 구현 하기 때문에 \(예를 들어,  **솔루션 탐색기**\) 생성 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 을 대신 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>IDE에서 호출 하는 세 가지 방법으로 구성 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.CountObjects%2A>개체에 표시 되도록 선택할 수 있습니다를  **속성이** 창입니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A>반환은 `IDispatch` 를 선택 하는 개체는  **속성** 창.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A>반환 되는 개체에 대 한 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> 는 사용자가 선택 해야 합니다.  이 시각적으로 사용자 UI에 표시 된 선택 항목을 업데이트 하 여 Vspackage가 있습니다.  
  
 **속성** 창에서 정보를 추출은 `IDispatch` 속성을 검색 하 고 검색 하기 위해 개체입니다.  속성 브라우저를 사용 하 여 `IDispatch` 개체 속성을 확인 하 여 쿼리 지원 `ITypeInfo`에서 얻을 수 `IDispatch::GetTypeInfo`.  브라우저 고 채우는 데 이러한 값을 사용의  **속성** 창 고 표에 표시 하는 개별 속성의 값을 변경 합니다.  속성 정보는 개체 내에서 유지 됩니다.  
  
 반환 된 개체를 지원 하기 때문에 `IDispatch`, 호출자가 호출 하 여 개체의 이름과 같은 정보를 얻을 수 있습니다 `IDispatch::Invoke` 또는 `ITypeInfo::Invoke` 로 원하는 정보를 나타내는 미리 정의 된 디스패치 식별자 \(DISPID\).  선언 된 Dispid 사용자 정의 식별자와 충돌 하지 않는 확인 하십시오 음수입니다.  
  
 해당  **속성이** 필드에 선택한 개체의 특정 속성의 특성에 따라 서로 다른 창에 표시 됩니다.  이 필드는 편집 상자, 드롭다운 목록 및 사용자 지정 편집기 대화 상자에 대 한 링크가 포함 됩니다.  
  
-   열거 된 목록에 포함 된 값이 검색으로 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> 쿼리를 `IDispatch`.  값이 열거 된 목록에서 가져온 속성 표에서 필드 이름을 두 번 클릭 하거나 해당 값을 클릭 하 고 드롭다운 목록에서 새 값을 선택 하 여 변경할 수 있습니다.  나열된 목록에서 설정을 미리 정의 된 속성을 속성 목록에서 속성 이름을 두 번 클릭 하면 사용할 수 있는 항목을 통해 순환 합니다.  True\/false 같은 두 가지 선택 사항 사용 하 여 미리 정의 된 속성에 대 한 선택 항목 사이 전환 하려면 속성 이름을 두 번 클릭 합니다.  
  
-   경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HasDefaultValue%2A> 입니다 `false`에서 나타내는 값이 변경 되 고 굵은 텍스트로 표시 됩니다.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.CanResetPropertyValue%2A>값을 원래 값으로 다시 설정할 수 있는지 확인 하는 데 사용 됩니다.  따라서 하면 다시 기본값으로 값을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 변경할 수 있는 경우  **다시 설정** 에서 표시 되는 메뉴입니다.  그렇지 않으면 다시 기본값으로 값을 수동으로 변경 해야 합니다.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>또한 현지화 하 고 디자인 타임에 표시 되는 속성의 이름을 숨길 수 있습니다 있지만 런타임 동안 표시 되는 속성 이름이 변경 되지 않습니다.  
  
-   줄임표 \(...\) 단추를 클릭 하면 속성 값을 사용자 \(색 선택 또는 글꼴 목록 등\) 선택할 수 있는 목록을 표시 합니다.  <xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>이러한 값을 제공합니다.  
  
## 참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)