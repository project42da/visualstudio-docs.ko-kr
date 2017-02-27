---
title: "레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-언어 서비스 컨텍스트"
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 컨텍스트를 사용 하 여 제공 하는 언어 서비스에 대 한 두 가지는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기: 텍스트 마커 컨텍스트를 제공 하거나 모든 사용자 컨텍스트를 제공 합니다.  여기서 각각의 차이점을 설명 합니다.  
  
 컨텍스트 편집기로 연결 되는 언어 서비스 제공에 대 한 자세한 내용은 [방법: 편집기에 대 한 컨텍스트를 제공 합니다.](../extensibility/how-to-provide-context-for-editors.md).  
  
## 편집기로 텍스트 마커 컨텍스트를 제공 합니다.  
 텍스트 마커를 표시 하는 컴파일러 오류에 대 한 컨텍스트를 제공 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기, 구현에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스입니다.  이 시나리오에서는 커서가 텍스트 마커를 경우에 상황에 맞는 언어 서비스를 제공 합니다.  그러면 키워드를 커서 위치를 제공 하는 편집기를  **동적 도움말** 창에 속성이 없습니다.  
  
## 편집기를 모든 사용자 컨텍스트를 제공 합니다.  
 사용자 언어 서비스를 만들고 사용 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기를 구현 하 여 다음의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 언어 서비스에 대 한 컨텍스트를 제공 하는 인터페이스입니다.  
  
 구현에 대 한 `IVsLanguageContextProvider`, 컨텍스트 모음 업데이트 해야 하는 편집기 컨텍스트 모음 \(컬렉션\)에 연결 되어 있습니다.  때의  **동적 도움말** 창 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> 인터페이스 유휴 시간, 컨텍스트 모음에이 컨텍스트 모음에서 쿼리 편집기의 업데이트.  그런 다음 편집기 편집기를 업데이트 해야 합니다 및 컨텍스트 모음에 대 한 포인터를 전달 하는 언어 서비스 알립니다.  이 호출 하 여 수행 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> 메서드 편집기에서 언어 서비스에.  컨텍스트 모음에 포인터를 사용 하 여 언어 서비스 수 있습니다 지금 추가 하 고 특성 및 키워드를 제거 합니다.  자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>를 참조하십시오.  
  
 두 가지 방법으로 구현 하는 `IVsLanguageContextProvider`:  
  
-   컨텍스트 모음에 키워드를 제공 합니다.  
  
     편집기 컨텍스트 모음을 업데이트 하려면 호출 되 면 적절 한 키워드 및 특성에 전달 하 고 다음 반환할 `S_OK`.  반환 값이 키워드 컨텍스트 모음에 커서 위치를 제공 하는 사용자 컨텍스트 키워드 및 특성을 유지 하지 않고 편집기를 지시 합니다.  
  
-   키워드는 키워드의 커서를 얻을합니다  
  
     편집기 컨텍스트 모음을 업데이트 하려면 호출 되 면 해당 속성에 전달 및 다음 반환할 `E_FAIL`.  이 반환 값 편집기 컨텍스트 모음에서 사용자 특성을 유지 하지만 컨텍스트 모음 키워드의 커서를 업데이트 하도록 지시 합니다.  
  
 다음은 구현 하는 언어 서비스에 대 한 컨텍스트를 제공 하는 어떻게 하는 방법을 보여 줍니다 `IVsLanguageContextProvider`.  
  
 ![LangServiceImplementation2 그래픽](../extensibility/media/vslanguageservice2.png "vsLanguageService2")  
컨텍스트는 언어 서비스에 대 한  
  
 다이어그램에서 볼 수 있듯이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 핵심 텍스트 편집기에 연결 하는 컨텍스트 모음에 있습니다.  이 컨텍스트 모음에 세 가지 별도 하위 컨텍스트로 가방 가리킵니다: 텍스트 표식, 기본 편집기 및 언어 서비스입니다.  언어 서비스 및 텍스트 마커 하위 컨텍스트로 가방 특성 및 키워드의 언어 서비스에 대 한 경우를 포함를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 인터페이스를 구현 및 텍스트 마커 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스가 구현 됩니다.  이러한 인터페이스를 구현 하지 않는 경우 다음 편집기 컨텍스트 키워드 기본 편집기 하위 컨텍스트로 가방에서 커서 위치를 제공 합니다.  
  
## 편집기 및 디자이너에 대 한 상황에 맞는 지침  
 디자이너 및 편집기 편집기 또는 디자이너 창에 대 한 일반적인 키워드를 제공 해야 합니다.  F1 키를 누를 때 디자이너 또는 편집기에 대 한 일반, 하지만, 적절 한 도움말 항목을 표시 합니다 수 있도록이 수행 됩니다.  편집기,이 외에 현재 키워드 커서 위치를 제공 하거나 해야 현재 선택에 기초 하는 주요 항목을 제공 합니다.  이 도움말 항목의 텍스트 또는 UI 요소를 가리키는 때 f1 키를 누르면 선택한 표시 해야 할 수 있습니다.  디자이너 폼의 단추와 같은 디자이너에서 선택 된 항목에 대 한 컨텍스트를 제공 합니다.  편집기 및 디자이너도 연결 해야 하는 언어 서비스에 설명 된 대로 [레거시 언어 서비스 Essentials](../extensibility/internals/legacy-language-service-essentials.md).