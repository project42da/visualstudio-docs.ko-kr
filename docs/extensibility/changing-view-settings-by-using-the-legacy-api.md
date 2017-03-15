---
title: "레거시 API를 사용 하 여 보기 설정 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-보기 설정 변경"
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# 레거시 API를 사용 하 여 보기 설정 변경
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코어 편집기 기능, 자동 줄 바꿈, 선택 영역 여백 및 가상 공간에 대 한 설정으로 사용자가 변경할 수 있는  **옵션** 대화 상자.  그러나 또한 이러한 설정을 변경할 수 있습니다 프로그래밍.  
  
## 레거시 API를 사용 하 여 설정 변경  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 인터페이스는 텍스트 편집기 속성 집합을 노출 합니다.  텍스트 뷰 텍스트 보기를 프로그래밍 방식으로 변경 된 설정의 그룹을 나타내는 속성 \(GUID\_EditPropCategory\_View\_MasterSettings\)의 범주를 포함 되어 있습니다.  이 방법으로 보기 설정을 변경한 후에에서 변경할 수 없습니다의  **옵션** 대화 상자 재설정 합니다.  
  
 다음 인스턴스 코어 편집기의 보기 설정을 변경 하는 일반적인 과정입니다.  
  
1.  호출 `QueryInterface` 에 있는 \(<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>\)에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 인터페이스.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> 메서드를 guid\_editpropcategory\_view\_mastersettings에 대 한 값을 지정 하는 `rguidCategory` 매개 변수.  
  
     이 작업에 대 한 포인터를 반환의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 보기에 대 한 강제 속성 집합을 포함 하는 인터페이스입니다.  이 그룹의 모든 설정은 영구적으로 강제로 됩니다.  설정을이 그룹에 속하지 않은 경우에 지정 된 옵션에 따라 수 있는  **옵션** 대화 상자 또는 사용자의 명령.  
  
3.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> 메서드를 적절 한 설정 값을 지정 하는 `idprop` 매개 변수.  
  
     예를 들어, 단어 잘림 방지 하려면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> , vseditpropid\_viewlangopt\_wordwrap의 값을 지정 하 고 `vt` 에 있는 `idprop` 매개 변수.  이 호출에서 `vt` VT\_BOOL 형식의 VARIANT입니다 및 `vt.boolVal` VARIANT\_TRUE입니다.  
  
## 변경 된 뷰 설정 다시 설정  
 코어 편집기의 인스턴스를 설정 된 변경 된 보기를 다시 설정 하기 위해 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> 메서드에 적절 한 설정 값을 지정 하는 `idprop` 매개 변수.  
  
 예를 들어, 자유롭게 배치에 자동 줄 바꿈을 허용 하려면 하면이 속성 범주를 호출 하 여 제거 될 수 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> 및 vseditpropid\_viewlangopt\_wordwrap에 대 한 값을 지정 하는 `idprop` 매개 변수.  
  
 코어 편집기에 대 한 모든 변경 된 설정을 한 번에 제거 하려면 값을 VSEDITPROPID\_ViewComposite\_AllCodeWindowDefaults, v t에 대 한 지정은 `idprop` 매개 변수.  이 호출은 vt VT\_BOOL 형식의 VARIANT 이며 vt.boolVal VARIANT\_TRUE입니다.  
  
## 참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)   
 [텍스트 보기에 액세스 하는 레거시 API를 사용 하 여](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)