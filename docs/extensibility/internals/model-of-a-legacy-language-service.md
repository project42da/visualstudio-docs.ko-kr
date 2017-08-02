---
title: "레거시 언어 서비스의 모델 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스, 모델"
ms.assetid: d8ae1c0c-ee3d-4937-a581-ee78d0499793
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 레거시 언어 서비스의 모델
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

언어 서비스 요소 및 특정 언어에 대 한 기능을 정의 하 고 편집기를 해당 언어에 대 한 정보를 제공 하는 데 사용 됩니다.  예를 들어, 편집기 구문 색을 지원 하기 위해 요소와 언어의 키워드를 알고 있어야 합니다.  
  
 언어 서비스 관리 편집기 및 편집기를 포함 하는 보기에서 텍스트 버퍼를 밀접 하 게 작동 합니다.  Microsoft IntelliSense  **요약 정보** 옵션 언어 서비스에서 제공 하는 기능의 예입니다.  
  
## 최소한의 언어 서비스  
 가장 기본적인 언어 서비스는 다음 두 개체를 포함 되어 있습니다.  
  
-   *언어 서비스*  구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스입니다.  언어 서비스 이름, 파일 확장명, 코드 창 관리자 및 colorizer 포함 하는 언어에 대 한 정보가 있습니다.  
  
-   *Colorizer*  구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스입니다.  
  
 다음 개념도 모델의 기본적인 언어 서비스를 보여 줍니다.  
  
 ![언어 서비스 모델 그래픽](~/docs/extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
기본 언어 서비스 모델  
  
 문서 창의 호스트는  *문서 보기*  편집기를이 경우에는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.  편집기에서 문서 보기 및 텍스트 버퍼의 소유입니다.  이러한 개체 작업 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 라고 하는 특수 문서 창을  *코드 창*.  코드 창에 포함 되어 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 작성 및 IDE에서 제어 하는 개체입니다.  
  
 지정 된 확장명이 있는 파일을 로드 하면 편집기 확장명과 연결 된 언어 서비스를 정하고, 코드 창을 호출 하 여 전달 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> 메서드.  언어 서비스 반환은  *코드 창 관리자*, 어떤 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> 인터페이스입니다.  
  
 다음 표에서 개체 모델에서의 개요를 제공합니다.  
  
|구성 요소|개체|Function|  
|-----------|--------|--------------|  
|텍스트 버퍼|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>|유니코드 읽기 텍스트 스트림입니다.  다른 인코딩을 사용 하는 텍스트에 대 한 수 있습니다.|  
|코드 창|<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>|하나 이상의 텍스트 뷰는 문서 창입니다.  때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 다중 문서 인터페이스 \(MDI\) 모드에서 코드 창이 MDI 자식입니다.|  
|텍스트 보기|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>|이동 하는 키보드와 마우스를 사용 하 여 텍스트를 볼 수 있는 창입니다.  편집자와 사용자에 게 텍스트 보기에 나타납니다.  일반 편집기 창, 출력 창 및 직접 실행 창에서 텍스트 뷰를 사용할 수 있습니다.  또한 코드 창 내에서 하나 이상의 텍스트 보기를 구성할 수 있습니다.|  
|텍스트 관리자|관리 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> 를 얻을에서 서비스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> 포인터|앞에서 설명한 모든 구성 요소에서 공유 하는 일반적인 정보를 유지 관리 하는 구성 요소입니다.|  
|언어 서비스|구현에 따라 다릅니다. 구현<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>|편집기 구문 강조 표시, 문 완성 및 중괄호 일치 하는 언어 관련 정보를 제공 하는 개체입니다.|  
  
## 참고 항목  
 [문서 데이터와 사용자 지정 편집기에서 문서 보기](../../extensibility/document-data-and-document-view-in-custom-editors.md)