---
title: "속성 창 단추 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 창, 단추"
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 속성 창 단추
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

개발 언어 및 제품 종류에 따라 특정 단추가 도구 모음에 기본적으로 표시 되는  **속성이** 창입니다.  모든 경우에는  **항목별**,  **Alphabetized**,  **속성이**, 및  **속성 페이지** 단추가 표시 됩니다.  C\# 및 Visual Basic는  **이벤트** 단추가 표시 됩니다.  특정 Visual c \+ \+ 프로젝트에는  **VC \+ \+ 메시지** 및  **VC 재정의** 단추가 표시 됩니다.  다른 프로젝트 형식에 대 한 추가 단추가 표시 될 수 있습니다.  단추에 대 한 자세한 내용은  **속성** 창을 참조 하십시오 [속성 창](../../ide/reference/properties-window.md).  
  
## 등록 정보 창의 단추 구현  
 클릭 하면는  **항목별** 단추를 Visual Studio 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> 인터페이스 속성을 항목별로 정렬 하려면 포커스를 가진 개체.  <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>구현 되는 `IDispatch` 를 제공 하는 개체는  **속성** 창.  
  
 음수 값을 가진 11 속성을 미리 정의 된 범주입니다.  사용자 지정 범주를 정의할 수 있지만 미리 정의 된 범주를 구분 하기 위한 양수 값 할당 하는 것이 좋습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A> 메서드는 지정 된 속성에 대 한 적절 한 속성 범주 값 반환 합니다.  <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A> 메서드 범주 이름이 들어 있는 문자열을 반환 합니다.  Visual Studio 있는 표준 속성 범주 값을 알고 있기 때문에 사용자 정의 범주 값에 대 한 지원을 제공 해야 합니다.  
  
 클릭 하면 해당  **Alphabetized** 단추를 속성 이름을 사용 하 여 사전순으로 표시 됩니다.  이름으로 검색 한 `IDispatch` 지역화 된 정렬 알고리즘에 따라.  
  
 때의  **속성** 창이 열려 있는  **속성** 단추 자동으로 표시 선택.  환경의 다른 부분에 동일한 단추 표시 및 표시를 클릭할 수는  **속성** 창입니다.  
  
 **속성 페이지** 단추를 사용할 수 없는 경우 `ISpecifyPropertyPages` 선택한 개체에 대해 구현 되어 있지 않습니다.  일반적으로 솔루션 및 프로젝트와 관련 된 디스플레이 구성 종속성 속성 속성 페이지를 하지만 수 수 관련 프로젝트에 있는 항목 \(예를 들어, Visual c \+ \+\).  
  
> [!NOTE]
>  도구 모음 단추를 추가할 수 없습니다는  **속성이** 관리 되지 않는 코드를 사용 하 여 창을.  도구 모음 단추를 추가 하려면에서 파생 된 관리 되는 개체 만들기 <xref:System.Windows.Forms.Design.PropertyTab>.  
  
## 참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)