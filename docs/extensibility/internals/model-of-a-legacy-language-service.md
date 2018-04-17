---
title: 레거시 언어 서비스의 모델 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, model
ms.assetid: d8ae1c0c-ee3d-4937-a581-ee78d0499793
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 943f0f013045e3082af3069ed4d45aaed1096869
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="model-of-a-legacy-language-service"></a>레거시 언어 서비스의 모델
언어 서비스는 요소와는 특정 언어에 대 한 기능을 정의 하 고 해당 언어에 관련 정보 편집기를 제공 하는 데 사용 됩니다. 예를 들어 편집기 구문 색 지정을 지원 하기 위해 요소 및 언어의 키워드를 알고 있어야 합니다.  
  
 언어 서비스는 편집기와 편집기를 포함 하는 보기에서 관리 하는 텍스트 버퍼와 밀접 하 게 작동 합니다. Microsoft IntelliSense **요약 정보** 옵션은 예는 언어 서비스에서 제공 되는 기능입니다.  
  
## <a name="a-minimal-language-service"></a>최소한의 언어 서비스  
 가장 기본적인 언어 서비스는 다음 두 항목을 포함 되어 있습니다.  
  
-   *언어 서비스* 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스입니다. 언어 서비스에 이름, 파일 이름 확장명, 코드 창 관리자 및 색 지정 기를 포함 하 여 언어에 대 한 정보가 있습니다.  
  
-   *색 지정 기* 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스입니다.  
  
 다음 개념도 기본 언어 서비스의 모델을 보여 줍니다.  
  
 ![언어 서비스 모델 그래픽](../../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
기본 언어 서비스 모델  
  
 문서 창 호스트는 *문서 보기* 이 경우의 편집기는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다. 텍스트 버퍼와 문서 보기는 편집기에 의해 소유 됩니다. 이러한 개체를 작업할 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 라는 특수 한 문서 창을 통해는 *코드 창*합니다. 코드 창에 포함 되어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 만들어져 IDE에 의해 제어 되는 개체입니다.  
  
 편집기는 해당 확장명과 연결 된 언어 서비스를 찾는 하 고 전달 하 여 코드 창을 호출 하 여 지정 된 확장명을 가진 파일 로드 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> 메서드. 언어 서비스 반환은 *코드 창 관리자*를 구현 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 인터페이스입니다.  
  
 다음 표에서 모델의 개체에 대 한 개요를 제공합니다.  
  
|구성 요소|Object|함수|  
|---------------|------------|--------------|  
|텍스트 버퍼|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>|유니코드 읽기/쓰기 텍스트 스트림입니다. 다른 인코딩을 사용 하는 텍스트에 대 한 것 같습니다.|  
|코드 창|<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>|하나 이상의 텍스트 뷰를 포함 하는 문서 창입니다. 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 코드 창 (MDI) 다중 문서 인터페이스 모드로 MDI 자식입니다.|  
|텍스트 보기|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>|사용자가 이동 하 고 키보드 및 마우스를 사용 하 여 텍스트를 볼 수 있는 창입니다. 텍스트 보기는 사용자에 게 편집기로 나타납니다. 일반 편집기 창과 출력 창에서 직접 실행 창에서 텍스트 뷰를 사용할 수 있습니다. 또한 코드 창 내에서 하나 이상의 텍스트 보기를 구성할 수 있습니다.|  
|텍스트 관리자|관리는 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> 가져와야 하에서 서비스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> 포인터|앞에서 설명한 모든 구성 요소에서 공유 하는 일반적인 정보를 유지 관리 하는 구성 요소입니다.|  
|언어 서비스|구현에 따라 다릅니다. 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>|편집기 구문 강조 표시, 문 완성, 중괄호 일치 등 언어 관련 정보를 제공 하는 개체입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 편집기의 문서 데이터 및 문서 보기](../../extensibility/document-data-and-document-view-in-custom-editors.md)