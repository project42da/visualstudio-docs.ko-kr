---
title: 레거시 API를 사용 하 여 보기 설정을 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
caps.latest.revision: 18
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dc68bf5f8a0e61b80200cd5454b78bcdda78cdfe
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="changing-view-settings-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 보기 설정 변경
가상 공간, 자동 줄 바꿈 및 선택 영역 여백을 등의 핵심 편집기 기능에 대 한 설정을 통해 사용자가 변경할 수 있습니다는 **옵션** 대화 상자. 하지만 이러한 설정을 변경할 수 이기도 프로그래밍 방식으로 합니다.  
  
## <a name="changing-settings-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 설정 변경  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 인터페이스 텍스트 편집기 속성 집합을 노출 합니다. 텍스트 보기 텍스트 보기에 대 한 프로그래밍 방식으로 변경 된 설정의 그룹을 나타내는 (GUID_EditPropCategory_View_MasterSettings) 속성의 범주를 포함 합니다. 이러한 방식으로 뷰 설정 변경 된 후에 변경할 수 없는 **옵션** 가 초기화 될 때까지 대화 상자.  
  
 다음은 핵심 편집기의 인스턴스에 대 한 보기 설정을 변경 하기 위한 일반적인 프로세스입니다.  
  
1.  호출 `QueryInterface` 에 (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>)에 대 한는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 인터페이스입니다.  
  
2.  호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> 메서드를 GUID_EditPropCategory_View_MasterSettings에 대 한 값을 지정 하는 `rguidCategory` 매개 변수입니다.  
  
     이 작업에 대 한 포인터를 반환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 보기에 대 한 강제 속성 집합을 포함 하는 인터페이스입니다. 이 그룹의 모든 설정 영구적으로 강제 합니다. 설정이이 그룹에 없는 경우에 지정 된 옵션을 따를 것은 **옵션** 대화 상자 또는 사용자의 명령이 있습니다.  
  
3.  호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> 에 적절 한 설정 값을 지정 하는 메서드를는 `idprop` 매개 변수입니다.  
  
     예를 들어, 자동 줄 바꿈 하려면 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> VSEDITPROPID_ViewLangOpt_WordWrap, 값을 지정 하 고 `vt` 에 대 한는 `idprop` 매개 변수입니다. 이 호출에서 `vt` VT_BOOL 형식의 변형 및 `vt.boolVal` 가 VARIANT_TRUE입니다.  
  
## <a name="resetting-changed-view-settings"></a>변경 된 보기 설정을 다시 설정  
 핵심 편집기의 인스턴스에 대 한 설정 변경 된 모든 보기를 다시 설정 하려면 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> 메서드에 적절 한 설정 값을 지정 하 고는 `idprop` 매개 변수입니다.  
  
 예를 들어, 자동 줄 바꿈 자유롭게 부동 소수점 수 있도록 있습니다 것에서 제거 된 속성 범주를 호출 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> VSEDITPROPID_ViewLangOpt_WordWrap에 대 한 값을 지정 하 고는 `idprop` 매개 변수입니다.  
  
 코어 편집기에 대 한 모든 변경 된 설정을 한 번에 제거 하려면 VSEDITPROPID_ViewComposite_AllCodeWindowDefaults, v t에 대 한 값을 지정 된 `idprop` 매개 변수입니다. 이 호출에서 vt VT_BOOL 유형의 VARIANT 이며 vt.boolVal가 VARIANT_TRUE입니다.  
  
## <a name="see-also"></a>참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)   
 [레거시 API를 사용 하 여 텍스트 보기에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)